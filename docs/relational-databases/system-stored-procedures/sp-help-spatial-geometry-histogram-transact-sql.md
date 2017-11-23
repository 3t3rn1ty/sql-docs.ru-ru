---
title: "sp_help_spatial_geometry_histogram (Transact-SQL) | Документы Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_help_spatial_geometry_histogram
- sp_help_spatial_geometry_histogram_TSQL
dev_langs: TSQL
helpviewer_keywords: sp_help_spatial_geometry_histogram
ms.assetid: 036aaf61-df3e-40f7-aa4e-62983c5a37bd
caps.latest.revision: "17"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 6ed8a457ce9fb7038a561ab2814cdf0e3f6991c2
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="sphelpspatialgeometryhistogram-transact-sql"></a>sp_help_spatial_geometry_histogram (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Упрощает задание значений параметров ограничивающего прямоугольника и сетки для пространственного индекса.  
  
||  
|-|  
|**Область применения**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (с[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] до [текущей версии](http://go.microsoft.com/fwlink/p/?LinkId=299658)).|  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_help_spatial_geometry_histogram [ @tabname =] 'tabname'   
     [ , [ @colname = ] 'columnname' ]   
     [ , [ @resolution = ] 'resolution' ]  
     [ , [ @xmin = ] 'minx' ]   
     [ , [ @ymin = ] 'miny' ]   
     [ ,.[ @xmax = ] 'maxx' ]  
     [ , [ @ymax = ] 'maxy' ]  
     [ , [ @sample = ] 'sample' ]  
```  
  
## <a name="arguments"></a>Аргументы  
 [  **@tabname =**] **"***tabname***"**  
 Полное или неполное имя определенной таблицы, для которой был указан пространственный индекс.  
  
 Кавычки требуются, только если определяется уточненная таблица. Если предоставлено полное имя таблицы, включая имя базы данных, в качестве последнего должно использоваться имя текущей базы данных. *tabname* — **sysname**, не имеет значения по умолчанию.  
  
 [  **@colname =** ] **"***colname***"**  
 Имя указанного пространственного столбца. *colname* — **sysname**, не имеет значения по умолчанию.  
  
 [  **@resolution =** ] **"***разрешение***"**  
 Разрешение ограничивающего прямоугольника. Допустимые значения: от 10 до 5000. *разрешение* — **tinyint**, не имеет значения по умолчанию.  
  
 [  **@xmin =** ] **"***xmin***"**  
 Минимальная координата по оси X для ограничивающего прямоугольника. *xMin* — **float**, не имеет значения по умолчанию.  
  
 [  **@ymin =** ] **"***ymin***"**  
 Минимальная координата по оси Y для ограничивающего прямоугольника. *yMin* — **float**, не имеет значения по умолчанию.  
  
 [  **@xmax =** ] **"***xmax***"**  
 Максимальная координата по оси X для ограничивающего прямоугольника. *xMax* — **float**, не имеет значения по умолчанию.  
  
 [  **@ymax =** ] **"***ymax***"**  
 Максимальная координата по оси Y для ограничивающего прямоугольника. *yMax* — **float**, не имеет значения по умолчанию.  
  
 [  **@sample =** ] **"***пример***"**  
 Используемая область таблицы (в процентах). Допустимые значения: от 0 до 100. *Образец* — **float**. По умолчанию установлено значение 100.  
  
## <a name="property-valuereturn-value"></a>Значение свойства/возвращаемое значение  
 Возвращает табличное значение. В следующей сетке описывается содержимое столбцов таблицы.  
  
|Имя столбца|Тип данных|Description|  
|-----------------|---------------|-----------------|  
|**cellid**|**int**|Представляет собой уникальный идентификатор каждой ячейки, перечисление начинается с 1.|  
|**ячейки**|**geometry**|Прямоугольный многоугольник, представляющий каждую ячейку. Форма ячеек идентична форме ячеек, используемой при пространственном индексировании.|  
|**row_count**|**bigint**|Указывает количество пространственных объектов, которые ограничивают или содержат ячейку.|  
  
## <a name="permissions"></a>Permissions  
 Пользователь должен быть членом **открытый** роли. Необходимо разрешение READ ACCESS на сервере и объекте.  
  
## <a name="remarks"></a>Замечания  
 В пространственной таблице среды SSMS отображается графическое представление результатов. Можно повторно отправить запрос результатов с использованием пространственного окна для определения приблизительного количества элементов результатов. Объекты в таблице могут занимать более одной ячейки, поэтому сумма количества ячеек может быть больше числа фактических объектов.  
  
 В результирующий набор, в котором указано число объектов, находящихся за пределами ограничивающего прямоугольника или касающихся его, можно добавить дополнительную строку. **Cellid** этой строки равен 0 и **ячейки** этой строки содержит **LineString** , представляющий ограничивающий прямоугольник. Эта строка представляет все пространство за пределами ограничивающего прямоугольника.  
  
## <a name="examples"></a>Примеры  
 В следующем примере создается образец таблицы и затем вызывает метод **sp_help_spatial_geometry_histogram** в таблице.  
  
 `USE AdventureWorksDW2012`  
  
 `GO`  
  
 `-- Set database compatibility for circular arc segments`  
  
 `ALTER DATABASE AdventureWorksDW2012`  
  
 `SET COMPATIBILITY_LEVEL = 110;`  
  
 `GO`  
  
 `-- Create table to execute sp_help_spatial_geometry_histogram on`  
  
 `CREATE TABLE TownSites`  
  
 `(`  
  
 `Location geometry NULL,`  
  
 `SiteName nvarchar(50) NULL`  
  
 `)`  
  
 `GO`  
  
 `-- Insert site data into table`  
  
 `DECLARE @g geometry;`  
  
 `SET @g = geometry::Parse('POINT(0 0)');`  
  
 `INSERT INTO TownSites(Location, SiteName)`  
  
 `SELECT @g, N'Booth Map';`  
  
 `SET @g = geometry::Parse('POLYGON((1 1, 1 2, 2 2, 2 1, 1 1))');`  
  
 `INSERT INTO TownSites(Location, SiteName)`  
  
 `SELECT @g, N'Town Hall';`  
  
 `SET @g = geometry::Parse('CURVEPOLYGON(COMPOUNDCURVE(CIRCULARSTRING(-1 0, 0 -1, 1 0),(1 0, 1 2, -1 0)))');`  
  
 `INSERT INTO TownSites(Location, SiteName)`  
  
 `SELECT @g, N'Main Park';`  
  
 `SET @g = geometry::Parse('CIRCULARSTRING(1 5, 2 2, 5 1)');`  
  
 `INSERT INTO TownSites(Location, SiteName)`  
  
 `SELECT @g, N'Main Road';`  
  
 `-- Call proc to see data within bounding box`  
  
 `EXEC sp_help_spatial_geometry_histogram @tabname = TownSites, @colname = Location, @resolution = 64, @xmin = -2, @ymin = -2, @xmax = 3, @ymax = 3, @sample = 100;`  
  
 `GO`  
  
 `DROP TABLE TownSites;`  
  
 `GO`  
  
## <a name="see-also"></a>См. также:  
 [Пространственный индекс хранимых процедур &#40; Transact-SQL &#41;](http://msdn.microsoft.com/library/1be0f34e-3d5a-4a1f-9299-bd482362ec7a)  
  
  