---
title: Элемент SourceColumnID (ASSL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- SourceColumnID Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- SourceColumnID
helpviewer_keywords:
- SourceColumnID element
ms.assetid: 715c0be7-aa07-4dff-a909-9738224941ec
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: f4bfcf8969123515436be0d53b181747c322b110
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48187904"
---
# <a name="sourcecolumnid-element-assl"></a>Элемент SourceColumnID (ASSL)
  Содержит идентификатор (ID) из исходного столбца структуры интеллектуального анализа данных в предке [MiningStructure](../objects/miningstructure-element-assl.md) элемент.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
  
<MiningModelColumn>  
   ...  
   <SourceColumnID>...</SourceColumnID>  
   ...  
</MiningModelColumn>  
```  
  
## <a name="element-characteristics"></a>Характеристики элемента  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|Тип данных и длина|String|  
|Значение по умолчанию|None|  
|Количество элементов|1-1: обязательный элемент, который встречается ровно один раз.|  
  
## <a name="element-relationships"></a>Связи элемента  
  
|Связь|Элемент|  
|------------------|-------------|  
|Родительский элемент|[MiningModelColumn](../data-type/miningmodelcolumn-data-type-assl.md)|  
|Дочерние элементы|None|  
  
## <a name="remarks"></a>Примечания  
 Значение `SourceColumnID` совпадает с идентификатором столбца структуры интеллектуального анализа данных в [столбцы](../collections/columns-element-assl.md) коллекции родительского объекта `MiningStructure`.  
  
 Элемент, соответствующий родителю параметра `SourceColumnID` в объекты управления Analysis AMO объектной модели это <xref:Microsoft.AnalysisServices.MiningModelColumn>.  
  
## <a name="see-also"></a>См. также  
 [Свойства &#40;ASSL&#41;](properties-assl.md)  
  
  
