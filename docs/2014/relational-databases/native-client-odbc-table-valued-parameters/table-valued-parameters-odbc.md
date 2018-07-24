---
title: Возвращающие табличные значения параметров (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC)
- ODBC, table-valued parameters
ms.assetid: ef06cd13-18e2-4c65-8ede-c3955d820e54
caps.latest.revision: 28
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: ce0cd9e87d4bd594fb2c2be4a01e9f2cf8ef4a27
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2018
ms.locfileid: "37421793"
---
# <a name="table-valued-parameters-odbc"></a>Возвращающие табличное значение параметры (ODBC)
  Поддержка в ODBC возвращающих табличное значение параметров позволяет клиентским приложениям с большей эффективностью передавать параметризованные данные на сервер за счет передачи нескольких строк в ходе одного вызова.  
  
 Сведения о возвращающих табличные значения параметров на сервере, см. в разделе [параметров, возвращающих &#40;СУБД&#41;](../tables/use-table-valued-parameters-database-engine.md).  
  
 В ODBC существует два способа передачи на сервер возвращающих табличное значение параметров.  
  
-   Все данные возвращающего табличное значение параметра может быть в памяти во время вызова SQLExecDirect или SQLExecute. Эти данные хранятся в массивах, если в табличном значении имеется несколько строк.  
  
-   Приложение может указать данные времени выполнения для возвращающих табличные значения параметра при вызове SQLExecDirect или SQLExecute. В этом случае строки данных для табличного значения могут быть представлены в пакетах или по одному, чтобы снизить требования, предъявляемые к памяти.  
  
 В первом случае хранимые процедуры могут инкапсулировать дополнительные объемы бизнес-логики. К примеру, если элементы заказа передаются в виде возвращающего табличное значение параметра, одна хранимая процедура может инкапсулировать целую транзакцию по приему заказов. Этот параметр очень эффективен, поскольку предполагает только одно обращение к серверу. Существует и другая возможность: использовать одни процедуры для обработки заголовка заказа, а другие – для элементов заказа, но в этом случае потребуется дополнительный код и более сложный контракт между клиентом и сервером.  
  
 Второй метод представляет собой эффективный механизм для выполнения массовых операций с очень большими объемами данных. Это дает приложению возможность осуществлять потоковую передачу строк данных на сервер без предварительной буферизации их в памяти.  
  
 При создании этой табличной переменной можно формировать ограничения и первичные ключи. Ограничения дают хорошую гарантию того, что данные таблицы соответствуют определенным требованиям.  
  
## <a name="in-this-section"></a>в этом разделе  
 [Сценарии использования возвращающих табличное значение параметров ODBC](uses-of-odbc-table-valued-parameters.md)  
 Описывает основные пользовательские сценарии для возвращающих табличное значение параметров и ODBC.  
  
 [Тип ODBC SQL для параметров, возвращающих табличное значение](odbc-sql-type-for-table-valued-parameters.md)  
 Описывает тип SQL_SS_TABLE. Это новый тип ODBC SQL, поддерживающий возвращающие табличное значение параметры.  
  
 [Поля дескрипторов возвращающего табличное значение параметра](table-valued-parameter-descriptor-fields.md)  
 Описывает поля дескриптора, которые поддерживают возвращающие табличное значение параметры.  
  
 [Поля дескриптора для столбцов, содержащих параметры, возвращающие табличные значения](descriptor-fields-for-table-valued-parameter-constituent-columns.md)  
 Описывает поля дескриптора, имеющие смысл для возвращающих табличное значение параметров.  
  
 [Поля диагностических записей для возвращающих табличные значения параметров](table-valued-parameter-diagnostic-record-fields.md)  
 Описывает два диагностических поля, добавленных к диагностическим записям для поддержки параметров, возвращающих табличное значение.  
  
 [Атрибуты инструкции, влияющие на возвращающие табличное значение параметры](statement-attributes-that-affect-table-valued-parameters.md)  
 Описывает новое поле заголовка дескриптора, активирующее столбцы с возвращающими табличное значение параметрами, к которым будет осуществляться обращение.  
  
 [Привязка и передача данных возвращающих табличное значение параметров и значений столбцов](binding-and-data-transfer-of-table-valued-parameters-and-column-values.md)  
 Описывает привязку параметров и разъясняет, как передавать серверу возвращающий табличное значение параметр.  
  
 [Метаданные возвращающего табличное значение параметра для подготовленных инструкций](table-valued-parameter-metadata-for-prepared-statements.md)  
 Описывает, как приложение может получить метаданные для заготовленного вызова процедуры.  
  
 [Дополнительные метаданные возвращающего табличное значение параметра](additional-table-valued-parameter-metadata.md)  
 В этой статье описывается использование SQLColumns, SQLProcedureColumns и SQLTables для получения метаданных для возвращающих табличные значения параметра.  
  
 [Ошибки и предупреждения преобразования данных возвращающих табличное значение параметров и другие](table-valued-parameter-data-conversion-and-other-errors-and-warnings.md)  
 Описывает, как обрабатывать ошибки в значениях столбцов с возвращающими табличное значение параметрами.  
  
 [Совместимость версий](cross-version-compatibility.md)  
 Описывает конфликты, которые могут возникать при использовании возвращающих табличное значение параметров клиентом или сервером версии более ранней, чем [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].  
  
 [Сводка по API-интерфейсам возвращающих табличное значение параметров ODBC](odbc-table-valued-parameter-api-summary.md)  
 Приводит перечень функций ODBC, которые поддерживают возвращающие табличное значение параметры.  
  
 [Примеры программирования с использованием возвращающих табличное значение параметров ODBC](../../database-engine/dev-guide/odbc-table-valued-parameter-programming-examples.md)  
 Описывает, как следует выполнять типичные задачи.  
  
## <a name="see-also"></a>См. также  
 [Собственный клиент SQL Server &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md)   
 [Возвращающие табличные значения параметров &#40;собственный клиент SQL Server&#41;](../native-client/features/table-valued-parameters-sql-server-native-client.md)  
  
  