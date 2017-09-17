---
title: "Организация пулов соединений диспетчер драйверов | Документы Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connection pooling [ODBC]
- pooled connections [ODBC]
- connecting to driver [ODBC], connection pooling
- connecting to data source [ODBC], connection pooling
ms.assetid: ee95ffdb-5aa1-49a3-beb2-7695b27c3df9
caps.latest.revision: 32
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: b589f7aa0e110767b7dca9be7aa82edee486b058
ms.contentlocale: ru-ru
ms.lasthandoff: 09/09/2017

---
# <a name="driver-manager-connection-pooling"></a>Организация пулов соединений диспетчер драйверов
Организация пулов соединений позволяет приложению использовать соединение из пула подключений, которые не нужно заново установить для каждого использования. После создания соединения и помещаются в пул, приложение может повторно использовать соединения без выполнения полного процесса.  
  
 Использование подключения в пуле может привести к значительный прирост производительности, поскольку приложения можно сохранить нагрузку, участвующих в соединении. Это может быть особенно существенным для приложений среднего уровня, которые подключаются по сети или приложений, которые многократно подключаться и отключаться, таких как веб-приложений.  
  
 Помимо прироста производительности архитектура организации пулов соединений включает среду и его связанные соединения для использования в нескольких компонентах в одном процессе. Это означает, что автономные компоненты, в том же процессе могут взаимодействовать друг с другом без сведений о друг с другом. Соединения в пуле соединений, можно использовать несколько раз в нескольких компонентах.  
  
> [!NOTE]  
>  Организация пулов соединений может использоваться приложением ODBC, обнаружены ODBC 2. *x* поведение, при условии, что приложение может вызвать *SQLSetEnvAttr*. При использовании пула подключений, приложение не может выполняться инструкции SQL, изменяющие базу данных или контексте базы данных, например \< *базы данных**имя*>, который изменяет каталог, используемый источником данных.  
  
 Драйвер ODBC должен быть полностью поточно ориентированного и подключений не должны быть сходство потоков для поддержки создания пулов соединений. Это означает, что драйвер может обрабатывать это вызов любого потока в любое время и возможность подключения в одном потоке, чтобы использовать соединение в другом потоке и для отключения на третий поток.  
  
 Пул соединений поддерживается диспетчером драйверов. Соединения выбираются из пула, когда приложение вызывает **SQLConnect** или **SQLDriverConnect** и возвращаются в пул, когда приложение вызывает **SQLDisconnect**. Размер пула растет динамически, исходя из выделения запрошенного ресурса. Уменьшается на время ожидания простоя в основе: Если подключение не используется в течение заданного времени (он не использовался в соединении), он удаляется из пула. Размер пула ограничивается только объемом доступной памяти и ограничений на сервере.  
  
 Диспетчера драйверов определяет, следует ли использовать определенное соединение в пуле в соответствии с аргументы, передаваемые в **SQLConnect** или **SQLDriverConnect**, но атрибуты соединения в соответствии с Задайте после подключения был выделен.  
  
 Если диспетчер драйверов организация пулов соединений, ее нужно уметь определить, работает ли по-прежнему соединения перед передачей ожидания соединения. В противном случае диспетчер драйверов на отслеживает передачу ожидания исчезновения подключения к приложению всякий раз, когда происходит сбой временного сетевого. В ODBC 3 был определен новый атрибут соединения*.x*: SQL_ATTR_CONNECTION_DEAD. Это атрибут подключения только для чтения, которое возвращает значение SQL_CD_TRUE или SQL_CD_FALSE. Значение SQL_CD_TRUE означает, что подключение потеряно, пока значение SQL_CD_FALSE означает, что соединение все еще выполняется. (Драйверы, соответствующие более ранних версий ODBC может также поддерживать этот атрибут).  
  
 Драйвер эффективно должен реализовывать этот параметр или он будет нарушать производительности пула подключений. В частности вызов для получения этот атрибут подключения не должна вызывать кругового пути к серверу. Вместо этого драйвер вернет только последнего известного состояния соединения. Соединение является исчезновения в том случае, если сбой последнего обращения к серверу и не исчезновения успешности последней туда и обратно.  
  
## <a name="remarks"></a>Замечания  
 Если подключение было утрачено (послано SQL_ATTR_CONNECTION_DEAD), диспетчер драйверов ODBC приведет к удалению этого соединения путем вызова SQLDisconnect в драйвере. Новые запросы на соединение не может найти пригодные соединения в пуле. В конечном итоге диспетчера драйверов может создать новое подключение, при условии, что пул пуст.  
  
 Чтобы использовать пул подключений, приложение выполняет следующие действия:  
  
1.  Включает пулов соединений путем вызова **SQLSetEnvAttr** для задания атрибута среды SQL_ATTR_CONNECTION_POOLING SQL_CP_ONE_PER_DRIVER или SQL_CP_ONE_PER_HENV. Необходимо выполнить этот вызов, прежде чем приложение выделяет общей среды для какое подключение пулов которого необходимо включить. Дескриптор среды в вызове **SQLSetEnvAttr** должен иметь значение null, что делает SQL_ATTR_CONNECTION_POOLING атрибут уровня процесса. Если атрибут имеет значение SQL_CP_ONE_PER_DRIVER, для каждого из драйверов поддерживается пул одного соединения. Если приложение работает с большое число драйверов и несколько сред, это может быть эффективнее, так как может потребоваться меньшее число сравнений. Если задано значение SQL_CP_ONE_PER_HENV пула одно подключение к поддерживается для каждой среды. Если приложение работает с многих средах и несколько драйверов, это может быть эффективнее, так как может потребоваться меньшее число сравнений. Пул подключений отключен, задав значение SQL_CP_OFF SQL_ATTR_CONNECTION_POOLING.  
  
2.  Выделяет среде путем вызова **SQLAllocHandle** с *HandleType* аргумент значение SQL_HANDLE_ENV. Среды, выделенной с помощью этого вызова будут неявное общей среде, потому что включен пул соединений. Среды для использования не определен, но до **SQLAllocHandle** с *HandleType* SQL_HANDLE_DBC, называется этой среды.  
  
3.  Выделяет соединения путем вызова **SQLAllocHandle** с *InputHandle* имеющим значение SQL_HANDLE_DBC и *InputHandle* присвоено дескриптор среды для организация пулов соединений. Диспетчер драйверов пытается найти существующую среду, соответствующий атрибуты среды, установленный приложением. Если среда не существует, он будет создан, с числом ссылок (поддерживается диспетчером драйверов) 1. При обнаружении соответствующей общей среды, среда возвращается в приложение и его количество ссылок увеличивается. (Фактическое соединение для использования не определяется диспетчером драйверов до **SQLConnect** или **SQLDriverConnect** называется.)  
  
4.  Вызовы **SQLConnect** или **SQLDriverConnect** для подключения. Диспетчер драйверов использует параметры соединения в вызове **SQLConnect** (или ключевых слов соединения в вызове **SQLDriverConnect**) и задать атрибуты соединения после выделения соединения Определите, какие соединения в пуле должен использоваться.  
  
    > [!NOTE]  
    >  Сопоставления запрошенное подключение для подключения в пуле определяется атрибут SQL_ATTR_CP_MATCH среды. Дополнительные сведения см. в разделе [SQLSetEnvAttr](../../../odbc/reference/syntax/sqlsetenvattr-function.md).  
  
     Приложения ODBC, с помощью пула соединений должен вызывать [CoInitializeEx](http://go.microsoft.com/fwlink/?LinkID=116307) во время инициализации приложения и [CoUninitialize](http://go.microsoft.com/fwlink/?LinkId=116310) при закрытии приложения.  
  
5.  Вызовы **SQLDisconnect** завершении с соединением. Соединение возвращается в пул соединений и становится доступным для повторного использования.  
  
 Подробное обсуждение в разделе [пула в Microsoft Data Access Components](http://go.microsoft.com/fwlink/?LinkId=120776).  
  
## <a name="connection-pooling-considerations"></a>Рекомендации по организации пулов соединений  
 Выполнить какие-либо из следующих действий, с помощью команды SQL (а не через API-интерфейса ODBC) могут повлиять на состояние соединения и привести к непредвиденным проблемам при активном пулов соединений:  
  
-   При открытии соединения и изменение базы данных по умолчанию.  
  
-   Для изменения любых настраиваемых параметров (включая SET ROWCOUNT, ANSI_NULL, IMPLICIT_TRANSACTIONS, инструкции SHOWPLAN, СТАТИСТИКИ, TEXTSIZE и DATEFORMAT) с помощью инструкции SET.  
  
-   Создание временных таблиц и хранимых процедур.  
  
 Если любое из этих действий выполняется за пределами ODBC API, следующий пользователь, который использует соединение автоматически наследуют предыдущие параметры, таблицы или процедуры.  
  
> [!NOTE]  
>  Некоторые параметры должны присутствовать в состояние соединения не ожидается. Всегда следует задать для состояния подключения в приложении и убедитесь, что приложение удаляет все неиспользуемые пула параметры подключений.  
  
## <a name="driver-aware-connection-pooling"></a>Организация пулов соединений с учетом драйвера  
 Начиная с Windows 8, драйвер ODBC можно использовать соединения в пуле более эффективно. Дополнительные сведения см. в разделе [Driver-Aware Connection Pooling](../../../odbc/reference/develop-app/driver-aware-connection-pooling.md).  
  
## <a name="see-also"></a>См. также:  
 [Подключение к данным источника или драйвер](../../../odbc/reference/develop-app/connecting-to-a-data-source-or-driver.md)   
 [Разработка драйвера ODBC](../../../odbc/reference/develop-driver/developing-an-odbc-driver.md)   
 [Создание пулов в компонентах доступа к данным MDAC](http://go.microsoft.com/fwlink/?LinkId=120776)