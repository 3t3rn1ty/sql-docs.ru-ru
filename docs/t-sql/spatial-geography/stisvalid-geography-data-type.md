---
title: STIsValid (тип данных geography) | Документы Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- STIsValid method (geography)
ms.assetid: 1bfe787f-ddf0-4fc7-af6a-570a58faab23
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: cceede70a5458abe72d6659312d897d7b68bb086
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2018
ms.locfileid: "47774982"
---
# <a name="stisvalid-geography-data-type"></a>STIsValid (тип данных geography)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

  Возвращает значение true, если экземпляр **geography** корректен и распознается как допустимый географический объект на основе типа открытого геопространственного консорциума (OGC). Возвращает значение false, если экземпляр **geography** имеет неправильный формат. Этот метод является точным.  
  
 Этот метод типа данных geography поддерживает экземпляры **FullGlobe** или пространственные экземпляры, размер которых больше полушария.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
.STIsValid ( )  
```  
  
## <a name="return-types"></a>Типы возвращаемых данных  
 Тип возвращаемых данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **bit**  
  
 Тип возвращаемых данных CLR: **SqlBoolean**  
  
## <a name="remarks"></a>Remarks  
 Тип OGC экземпляра **geography** можно определить с помощью метода [STGeometryType()](../../t-sql/spatial-geography/stgeometrytype-geography-data-type.md).  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] формирует только допустимые экземпляры **geography**, однако позволяет хранить и получать недопустимые экземпляры. Допустимый экземпляр, представляющий тот же набор точек, что и недопустимый экземпляр, может быть получен с помощью метода `MakeValid()`.  
  
## <a name="examples"></a>Примеры  
 В следующем примере создается экземпляр `geography` и используется метод `STIsValid()`, чтобы проверить, допустим ли экземпляр.  
  
```  
DECLARE @g geography = geography::STGeomFromText('LINESTRING(0 0, 2 2, 1 0)', 4326);  
SELECT @g.STIsValid();  
DECLARE @g geography  
```  
  
## <a name="see-also"></a>См. также:  
 [STGeometryType (тип данных geography)](../../t-sql/spatial-geography/stgeometrytype-geography-data-type.md)   
 [MakeValid (тип данных geography)](../../t-sql/spatial-geography/makevalid-geography-data-type.md)   
 [Методы OGC в экземплярах Geography](../../t-sql/spatial-geography/ogc-methods-on-geography-instances.md)  
  
  
