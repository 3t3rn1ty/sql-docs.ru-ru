---
title: STNumPoints (тип данных geometry) | Документы Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- STNumPoints_TSQL
- STNumPoints (geometry Data Type)
dev_langs:
- TSQL
helpviewer_keywords:
- STNumPoints (geometry Data Type)
ms.assetid: a19520fc-7f91-4a2c-856f-4d8b99a7e496
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: f135ce5a68cade2180a837562deae0129dc6cbab
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2018
ms.locfileid: "47683702"
---
# <a name="stnumpoints-geometry-data-type"></a>STNumPoints (тип данных geometry)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

  Возвращает суммарное количество точек в каждой из фигур в экземпляре **geometry**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
.STNumPoints ( )  
```  
  
## <a name="return-types"></a>Типы возвращаемых данных  
 Тип возвращаемых данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **int**  
  
 Тип возвращаемых данных CLR: **SqlInt32**  
  
## <a name="remarks"></a>Remarks  
 Этот метод подсчитывает число точек в описании экземпляра **geometry**. Повторяющиеся точки учитываются. Если этот экземпляр принадлежит к типу **collection**, то метод возвращает сумму точек в каждом из его элементов.  
  
## <a name="examples"></a>Примеры  
 В следующем примере создается экземпляр `LineString` и вызывается метод `STNumPoints()`, определяющий число точек, использованных в его описании.  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('LINESTRING(0 0, 2 2, 1 0)', 0);  
SELECT @g.STNumPoints();  
```  
  
## <a name="see-also"></a>См. также:  
 [Методы OGC в экземплярах Geometry](../../t-sql/spatial-geometry/ogc-methods-on-geometry-instances.md)  
  
  
