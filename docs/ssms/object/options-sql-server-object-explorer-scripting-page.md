---
title: "Параметры (обозреватель объектов SQL Server — страница &quot;Скрипты&quot;) | Документация Майкрософт"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.ObjectExplorerScripting
- VS.ToolsOptionsPages.Sql_Server_Object_Explorer.ObjectExplorerScripting
ms.assetid: 6105aec9-1b72-4cb2-bd24-fc35f6d95240
caps.latest.revision: 5
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: d5353c0732833516e95cc734a2d7bbe0f1258554
ms.contentlocale: ru-ru
ms.lasthandoff: 04/11/2017

---
# <a name="options-sql-server-object-explorer---scripting-page"></a>Параметры (обозреватель объектов SQL Server — страница "Скрипты")
Эта страница используется для задания параметров скриптов, применяемых к следующим командам контекстных меню объектов в **обозревателе объектов**:  
  
-   Команды **Правка** для пользовательских таблиц и представлений.  
  
-   Команды **Сформировать скрипт <object> как** для объектов, созданных пользователем.  
  
-   Команда **Изменить** для объектов, созданных пользователем.  
  
-   На этой странице также задаются параметры скриптов по умолчанию для **мастера формирования скриптов SQL Server**.  
  
## <a name="remarks"></a>Замечания  
Результаты выполнения команд **Правка** и **Изменить** могут отличаться от результатов команды **Сформировать скрипт <object> как** при том же значении параметра. Команды **Правка** и **Изменить** предназначены для изменения объектов в текущей базе данных во время сеанса работы редактора запросов. Команда **Сформировать скрипт <object> как** предназначена для формирования скрипта, который можно использовать позже для создания объектов.  
  
## <a name="options"></a>Параметры  
Укажите параметры создания скриптов, выбрав нужные настройки из числа доступных в окне списка, расположенном справа от каждого параметра.  
  
### <a name="general-scripting-options"></a>Общие параметры скрипта  
**Разделить отдельные инструкции**  
Разделяет отдельные инструкции [!INCLUDE[tsql](../../includes/tsql_md.md)] с помощью пакетного разделителя. Чтобы изменить пакетный разделитель по умолчанию для **редактора запросов**, выберите **Сервис**/**Параметры**/**Выполнение запроса**/**SQL Server**/**Общие**/**Разделитель пакетов**. Значение по умолчанию — False. Дополнительные сведения см. в разделе [GO (Transact-SQL)](http://msdn.microsoft.com/en-us/b2ca6791-3a07-4209-ba8e-2248a92dd738).  
  
**Включить описательные заголовки**  
Добавляет к скрипту описательные комментарии, разделяя его на разделы для каждого объекта. Значение по умолчанию — True. Дополнительные сведения см. в разделе [/*...*/ (Comment) (Transact-SQL)](http://msdn.microsoft.com/en-us/4d9ab1b2-4bbb-4c16-beb1-cafc1af7417c).  
  
**Включить параметры vardecimal**  
Включает параметры хранения vardecimal. Значение по умолчанию — False. Дополнительные сведения см. в разделе [sp_db_vardecimal_storage_format (Transact-SQL)](http://msdn.microsoft.com/en-us/9920b2f7-b802-4003-913c-978c17ae4542).  
  
**Создать скрипт для отслеживания изменений**  
Включает в скрипт сведения об отслеживании изменений.  
  
**Скрипт для версии сервера**  
Создает скрипт, который можно выполнять на выбранной версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]. Новые функции [!INCLUDE[ssCurrent](../../includes/sscurrent_md.md)] нельзя внести в скрипты для более ранних версий. Некоторые скрипты, созданные для [!INCLUDE[ssCurrent](../../includes/sscurrent_md.md)] , нельзя выполнять на серверах, где выполняется более ранняя версия [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)], или в базе данных с более ранним значением [уровня совместимости баз данных](http://msdn.microsoft.com/en-us/ca5fd220-d5ea-4182-8950-55d4101a86f6).  
  
**Внести в скрипт полнотекстовые каталоги**  
Включает скрипт для полнотекстовых каталогов. Значение по умолчанию — False. Дополнительные сведения см. в разделе [CREATE FULLTEXT CATALOG (Transact-SQL)](http://msdn.microsoft.com/en-us/d7a8bd93-e2d7-4a40-82ef-39069e65523b).  
  
**Внести в скрипт инструкцию USE <database>**  
Добавляет в скрипт инструкцию USE DATABASE для создания объектов базы данных в контексте текущей базы данных в **обозревателе объектов** . Если предполагается выполнение скрипта в другой базе данных, присвойте этому параметру значение False, чтобы не включать инструкцию USE DATABASE. Значение по умолчанию — True. Дополнительные сведения см. в разделе [USE (Transact-SQL)](http://msdn.microsoft.com/en-us/c05acac8-c063-4770-8e36-d7f71d500b10).  
  
### <a name="object-scripting-options"></a>Параметры скрипта объекта  
**Сформировать скрипт для зависимых объектов**  
Формирует скрипт для дополнительных объектов, необходимых при выполнении скрипта для выбранного объекта. Значение по умолчанию — False.  
  
**Включить предложение IF NOT EXISTS**  
Включает инструкцию для проверки отсутствия каждого объекта в базе данных перед попыткой создания этого объекта. Значение по умолчанию — False. Дополнительные сведения см. в разделах [IF...ELSE (Transact-SQL)](http://msdn.microsoft.com/en-us/676c881f-dee1-417a-bc51-55da62398e81) и [EXISTS (Transact-SQL)](http://msdn.microsoft.com/en-us/b6510a65-ac38-4296-a3d5-640db0c27631).  
  
**Имена объектов квалификаторов схемы**  
Квалифицирует имена объектов по схеме объектов. Значение по умолчанию — False. Дополнительные сведения см. в разделе [Создание схемы базы данных](http://msdn.microsoft.com/en-us/ed2a5522-f4d2-4111-95a4-d3e1e5081739).  
  
**Внести в скрипт расширенные свойства**  
Включает в скрипт расширенные свойства, если они имеются у объекта. Значение по умолчанию — False. Дополнительные сведения см. в разделе [sp_addextendedproperty (Transact-SQL)](http://msdn.microsoft.com/en-us/565483ea-875b-4133-b327-d0006d2d7b4c).  
  
**Владелец скрипта**  
Включает владельца в созданный скрипт. Значение по умолчанию — False.  
  
**Внести в скрипт разрешения**  
Включает в скрипт разрешения для объектов базы данных. Значение по умолчанию — True. Дополнительные сведения см. в разделе [Разрешения](http://msdn.microsoft.com/en-us/f28e3dea-24e6-4a81-877b-02ec4c7e36b9).  
  
### <a name="tableview-options"></a>Параметры таблицы или представления  
Следующие параметры применяются только к скриптам таблиц и представлений.  
  
**Преобразовать определяемые пользователем типы данных в базовые типы**  
Преобразует определяемые пользователем типы данных в базовые типы, из которых они были созданы. Используйте значение True, если в базе данных, в которой будет выполняться скрипт, отсутствуют определяемые пользователем типы данных базы данных-источника. Используйте значение False для сохранения определяемых пользователем типов данных. Значение по умолчанию — False. Дополнительные сведения см. в разделе [CREATE TYPE (Transact-SQL)](http://msdn.microsoft.com/en-us/2202236b-e09f-40a1-bbc7-b8cff7488905).  
  
**Создать команды SET ANSI PADDING**  
Добавляет инструкцию SET ANSI_PADDING до и после каждой инструкции CREATE TABLE. Значение по умолчанию — True. Дополнительные сведения см. в разделе [SET ANSI_PADDING (Transact-SQL)](http://msdn.microsoft.com/en-us/92bd29a3-9beb-410e-b7e0-7bc1dc1ae6d0).  
  
**Включить сортировку**  
Включить параметры сортировки в определение столбца. Значение по умолчанию — True. Дополнительные сведения см. в статье [Collation and Unicode Support](http://msdn.microsoft.com/en-us/92d34f48-fa2b-47c5-89d3-a4c39b0f39eb).  
  
**Включить свойство IDENTITY**  
Включает определения для начального значения свойства IDENTITY и шага приращения значения свойства IDENTITY. Значение по умолчанию — True. Дополнительные сведения см. в разделе [IDENTITY (Property) (Transact-SQL)](http://msdn.microsoft.com/en-us/8429134f-c821-4033-a07c-f782a48d501c).  
  
**Ссылки на внешние ключи квалификаторов схемы**  
Добавляет имя схемы к ссылкам на таблицы для ограничений FOREIGN KEY. Значение по умолчанию — True.  
  
**Внести в скрипт связанные значения по умолчанию и правила**  
Включает вызовы хранимых процедур привязки **sp_bindefault** и **sp_bindrule** . Значение по умолчанию — True. Дополнительные сведения см. в разделах [sp_bindefault (Transact-SQL)](http://msdn.microsoft.com/en-us/3da70c10-68d0-4c16-94a5-9e84c4a520f6) и [sp_bindrule (Transact-SQL)](http://msdn.microsoft.com/en-us/2606073e-c52f-498d-a923-5026b9d97e67).  
  
**Внести в скрипт ограничения CHECK**  
Добавляет в скрипт [ограничения CHECK](http://msdn.microsoft.com/en-us/637098af-2567-48f8-90f4-b41df059833e) . Значение по умолчанию — True.  
  
**Внести в скрипт значения по умолчанию**  
Включает в скрипт значения по умолчанию для столбца. Значение по умолчанию — False. Дополнительные сведения см. в статье [CREATE DEFAULT (Transact-SQL)](http://msdn.microsoft.com/en-us/08475db4-7d90-486a-814c-01a99d783d41).  
  
**Внести в скрипт файловые группы**  
Указывает файловую группу в предложении ON для определений таблиц. Значение по умолчанию — False. Дополнительные сведения см. в статье [CREATE TABLE (Transact-SQL)](http://msdn.microsoft.com/en-us/1e068443-b9ea-486a-804f-ce7b6e048e8b).  
  
**Внести в скрипт внешние ключи**  
Включает в скрипт [ограничения FOREIGN KEY](http://msdn.microsoft.com/en-us/31fbcc9f-2dc5-4bf9-aa50-ed70ec7b5bcd) . Значение по умолчанию — False.  
  
**Внести в скрипт полнотекстовые индексы**  
Включает в скрипт полнотекстовые индексы. Значение по умолчанию — False. Дополнительные сведения см. в статье [CREATE FULLTEXT INDEX (Transact-SQL)](http://msdn.microsoft.com/en-us/8b80390f-5f8b-4e66-9bcc-cabd653c19fd).  
  
**Внести в скрипт индексы**  
Включает в скрипт кластеризованные, некластеризованные индексы и XML-индексы. Значение по умолчанию — True. Дополнительные сведения см. в статье [CREATE INDEX (Transact-SQL)](http://msdn.microsoft.com/en-us/d2297805-412b-47b5-aeeb-53388349a5b9).  
  
**Внести в скрипт схемы секционирования**  
Включить в скрипт схемы секционирования таблиц. Значение по умолчанию — False. Дополнительные сведения см. в статье [CREATE PARTITION SCHEME (Transact-SQL)](http://msdn.microsoft.com/en-us/5b21c53a-b4f4-4988-89a2-801f512126e4).  
  
**Внести в скрипт первичные ключи**  
Включает в скрипт [ограничения первичных и внешних ключей](http://msdn.microsoft.com/en-us/31fbcc9f-2dc5-4bf9-aa50-ed70ec7b5bcd) . Значение по умолчанию — True.  
  
**Внести в скрипт команды сбора статистики**  
Включает в скрипт определяемые пользователем команды сбора статистики. Значение по умолчанию — False. Дополнительные сведения см. в разделе [CREATE STATISTICS (Transact-SQL)](http://msdn.microsoft.com/en-us/b23e2f6b-076c-4e6d-9281-764bdb616ad2).  
  
**Внести в скрипт триггеры**  
Включает в скрипт триггеры. Значение по умолчанию — False. Дополнительные сведения см. в разделе [CREATE TRIGGER (Transact-SQL)](http://msdn.microsoft.com/en-us/edeced03-decd-44c3-8c74-2c02f801d3e7).  
  
**Внести в скрипт уникальные ключи**  
Включает в скрипт [ограничения уникальности и ограничения проверки](http://msdn.microsoft.com/en-us/637098af-2567-48f8-90f4-b41df059833e) . Значение по умолчанию — False.  
  
**Внести в скрипт столбцы просмотра**  
Объявляет столбцы представления в заголовках представлений. Значение по умолчанию — False. Дополнительные сведения см. в статье [CREATE VIEW (Transact-SQL)](http://msdn.microsoft.com/en-us/aecc2f73-2ab5-4db9-b1e6-2f9e3c601fb9).  
  
**ScriptDriIncludeSystemNames**  
Включает созданные системой имена ограничений для обеспечения декларативной ссылочной целостности. Значение по умолчанию — False. Дополнительные сведения см. в статье [REFERENTIAL_CONSTRAINTS (Transact-SQL)](http://msdn.microsoft.com/en-us/5d358f18-0a85-4b55-af4b-98d5f4cd1020).  
  
## <a name="see-also"></a>См. также:  
[Формирование скриптов (среда SQL Server Management Studio)](http://msdn.microsoft.com/en-us/9711c617-3c68-4e5a-aea3-befc64d51524)  
  
