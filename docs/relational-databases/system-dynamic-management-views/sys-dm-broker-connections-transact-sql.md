---
title: "sys.dm_broker_connections (Transact-SQL) | Документы Microsoft"
ms.custom: 
ms.date: 01/08/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.dm_broker_connections
- dm_broker_connections
- sys.dm_broker_connections_TSQL
- dm_broker_connections_TSQL
dev_langs: TSQL
helpviewer_keywords: sys.dm_broker_connections dynamic management view
ms.assetid: d9e20433-67fe-4fcc-80e3-b94335b2daef
caps.latest.revision: "45"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: a01c8eae3b8bfdd2543fdcc1b162debceda54a3c
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmbrokerconnections-transact-sql"></a>sys.dm_broker_connections (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Возвращает по одной строке для каждого сетевого подключения компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)]. В следующей таблице содержатся дополнительные сведения:  
  
|Имя столбца|Тип данных|Description|  
|-----------------|---------------|-----------------|  
|**connection_id**|**uniqueidentifier**|Идентификатор соединения. Допускает значение NULL.|  
|**transport_stream_id**|**uniqueidentifier**|Идентификатор [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] подключения сетевой интерфейс (SNI), используемый для этого подключения по протоколу TCP/IP. Допускает значение NULL.|  
|**состояние**|**smallint**|Текущее состояние соединения. Допускает значение NULL. Возможные значения:<br /><br /> 1 = NEW<br /><br /> 2 = CONNECTING<br /><br /> 3 = CONNECTED<br /><br /> 4 = LOGGED_IN<br /><br /> 5 = ЗАКРЫТ|  
|**state_desc**|**nvarchar(60)**|Текущее состояние соединения. Допускает значение NULL. Возможные значения:<br /><br /> NEW<br /><br /> CONNECTING<br /><br /> CONNECTED<br /><br /> LOGGED_IN<br /><br /> CLOSED|  
|**connect_time**|**datetime**|Дата и время открытия соединения. Допускает значение NULL.|  
|**login_time**|**datetime**|Дата и время успешного входа для соединения. Допускает значение NULL.|  
|**authentication_method**|**nvarchar(128)**|Имя метода проверки подлинности Windows (например, NTLM или KERBEROS). Значение берется из Windows. Допускает значение NULL.|  
|**principal_name**|**nvarchar(128)**|Имя входа, у которого были проверены разрешения на соединение. В случае проверки подлинности Windows это значение равно имени удаленного пользователя. Для проверки подлинности сертификата это владелец сертификата. Допускает значение NULL.|  
|**remote_user_name**|**nvarchar(128)**|Имя равноправного пользователя из другой базы данных, использованное службой проверки подлинности Windows. Допускает значение NULL.|  
|**last_activity_time**|**datetime**|Дата и время последней отправки или приема данных через это соединение. Допускает значение NULL.|  
|**is_accept**|**bit**|Указывает, исходит ли соединение с удаленной стороны. Допускает значение NULL.<br /><br /> 1 = соединение является запросом, принятым от удаленного экземпляра.<br /><br /> 0 = соединение было инициировано локальным экземпляром.|  
|**login_state**|**smallint**|Состояние процесса входа в систему для данного соединения. Возможные значения:<br /><br /> 0 = INITIAL<br /><br /> 1 = WAIT LOGIN NEGOTIATE<br /><br /> 2 = ONE ISC<br /><br /> 3 = ONE ASC<br /><br /> 4 = TWO ISC<br /><br /> 5 = TWO ASC<br /><br /> 6 = WAIT ISC Confirm<br /><br /> 7 = WAIT ASC Confirm<br /><br /> 8 = WAIT REJECT<br /><br /> 9 = WAIT PRE-MASTER SECRET<br /><br /> 10 = WAIT VALIDATION<br /><br /> 11 = WAIT ARBITRATION<br /><br /> 12 = ЧЕРЕЗ ИНТЕРНЕТ<br /><br /> 13 = ERROR|  
|**login_state_desc**|**nvarchar(60)**|Текущее состояние входа в систему с удаленного компьютера. Возможные значения:<br /><br /> Инициализируется подтверждение соединения.<br /><br /> Подтверждение соединения ожидает сообщения согласования входа.<br /><br /> Подтверждение соединения инициализировало и отправило контекст безопасности для проверки подлинности.<br /><br /> Подтверждение соединения получило и приняло контекст безопасности для проверки подлинности.<br /><br /> Подтверждение соединения инициализировало и отправило контекст безопасности для проверки подлинности. Существует дополнительный механизм для проверки подлинности сторон.<br /><br /> Подтверждение соединения получило и отправило принятый контекст безопасности для проверки подлинности. Существует дополнительный механизм для проверки подлинности сторон.<br /><br /> Подтверждение соединения ожидает сообщения инициализации подтверждения контекста безопасности.<br /><br /> Подтверждение соединения ожидает сообщения принятия подтверждения контекста безопасности.<br /><br /> Подтверждение соединения ожидает сообщения отклонения SSPI для ошибки проверки подлинности.<br /><br /> Подтверждение соединения ожидает сообщения предварительного главного секретного кода.<br /><br /> Подтверждение соединения ожидает сообщения проверки.<br /><br /> Подтверждение соединения ожидает сообщения разрешения конфликта.<br /><br /> Подтверждение соединения завершено и готово к обмену сообщениями.<br /><br /> Ошибка соединения.|  
|**peer_certificate_id**|**int**|Идентификатор локального объекта сертификата, который используется удаленным экземпляром для проверки подлинности. Владелец этого сертификата должен иметь разрешение CONNECT для конечной точки компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)]. Допускает значение NULL.|  
|**encryption_algorithm**|**smallint**|Алгоритм шифрования, применяемый для данного соединения. Допускает значение NULL. Возможные значения:<br /><br /> **Значение &#124; Описание &#124; Соответствующий параметр DDL**<br /><br /> 0 &#124; Нет &#124; Отключено<br /><br /> 1 &#124; ТОЛЬКО ПОДПИСИ<br /><br /> 2 &#124; AES, RC4 &#124; Требуется &#124; Требуется алгоритм RC4}<br /><br /> 3 &#124; AES &#124; Требуется алгоритм AES<br /><br /> **Примечание:** алгоритм RC4 поддерживается только для обеспечения обратной совместимости. Когда база данных имеет уровень совместимости 90 или 100, новые материалы могут шифроваться только с помощью алгоритмов RC4 или RC4_128. (Не рекомендуется.) Используйте вместо этого более новые алгоритмы, например AES. В [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] и более поздних версиях материалы, зашифрованные с помощью алгоритмов RC4 или RC4_128, могут быть расшифрованы на любом уровне совместимости.|  
|**encryption_algorithm_desc**|**nvarchar(60)**|Текстовое представление алгоритма шифрования. Допускает значение NULL. Возможные значения:<br /><br /> **Описание &#124; Соответствующий параметр DDL**<br /><br /> Нет &#124; Отключено<br /><br /> RC4 &#124; {Требуется &#124; Требуется алгоритм RC4}<br /><br /> AES &#124; Требуется алгоритм AES<br /><br /> NONE, RC4 &#124; {Поддерживается &#124; Поддерживается алгоритм RC4}<br /><br /> NONE, AES &#124; Поддерживается алгоритм RC4<br /><br /> RC4, AES &#124; Требуется алгоритм RC4 AES<br /><br /> AES, RC4 &#124; Требуется алгоритм AES RC4<br /><br /> NONE, RC4, AES &#124; Поддерживается алгоритм RC4 AES<br /><br /> NONE, AES, RC4 &#124;  Поддерживается алгоритм AES RC4|  
|**receives_posted**|**smallint**|Количество асинхронных сетевых операций приема, которые не завершены в данном соединении. Допускает значение NULL.|  
|**is_receive_flow_controlled**|**bit**|Показывает наличие сетевых операций приема, отсроченных элементами управления потоком из-за того, что сеть занята. Допускает значение NULL.<br /><br /> 1 = True|  
|**sends_posted**|**smallint**|Количество запрошенных, но незавершенных сетевых операций отправки для данного соединения. Допускает значение NULL.|  
|**is_send_flow_controlled**|**bit**|Показывает наличие операций отправки, отсроченных элементами управления потоком из-за того, что сеть занята. Допускает значение NULL.<br /><br /> 1 = True|  
|**total_bytes_sent**|**bigint**|Суммарное число байтов, переданных данным соединением. Допускает значение NULL.|  
|**total_bytes_received**|**bigint**|Суммарное число байтов, полученных данным соединением. Допускает значение NULL.|  
|**total_fragments_sent**|**bigint**|Суммарное число фрагментов сообщений компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)], переданных данным соединением. Допускает значение NULL.|  
|**total_fragments_received**|**bigint**|Суммарное число фрагментов сообщений компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)], полученных данным соединением. Допускает значение NULL.|  
|**total_sends**|**bigint**|Суммарное число сетевых запросов на передачу, сформированных данным соединением. Допускает значение NULL.|  
|**total_receives**|**bigint**|Суммарное число сетевых запросов на прием, сформированных данным соединением. Допускает значение NULL.|  
|**peer_arbitration_id**|**uniqueidentifier**|Внутренний идентификатор для конечной точки. Допускает значение NULL.|  
  
## <a name="permissions"></a>Permissions  
 необходимо разрешение VIEW SERVER STATE на сервере.  
  
## <a name="physical-joins"></a>Физические соединения  
 ![Соединения для sys.dm_broker_connections](../../relational-databases/system-dynamic-management-views/media/join-dm-broker-connections-1.gif "соединения для sys.dm_broker_connections")  
  
## <a name="relationship-cardinalities"></a>Количество элементов связей  
  
|От|Чтобы|Связь|  
|----------|--------|------------------|  
|**dm_broker_connections.connection_id**|**dm_exec_connections.connection_id**|Один к одному|  
  
## <a name="see-also"></a>См. также:  
 [Динамические административные представления и функции (Transact-SQL)](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [Динамические административные представления, связанные с компонентом Service Broker (Transact-SQL)](../../relational-databases/system-dynamic-management-views/service-broker-related-dynamic-management-views-transact-sql.md)  
  
  
