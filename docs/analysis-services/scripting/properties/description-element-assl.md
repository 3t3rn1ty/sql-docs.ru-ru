---
title: Элемент Description (ASSL) | Документы Microsoft
ms.date: 5/8/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7235f524cb4754470e15f250df7c61c7ffa20a26
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
---
# <a name="description-element-assl"></a>Элемент Description (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Содержит описание родительского элемента.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
  
<Action> <!-- or one of the elements listed below in the Element Relationships table -->  
   ...  
   <Description>...</Description>  
   ...  
</Action>  
```  
  
## <a name="element-characteristics"></a>Характеристики элемента  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|Тип данных и длина|Строковые значения|  
|Значение по умолчанию|None|  
|Количество элементов|0—1: необязательный элемент, который появляется только один раз.|  
  
## <a name="element-relationships"></a>Связи элемента  
  
|Связь|Элемент|  
|------------------|-------------|  
|Родительские элементы|[Действие](../../../analysis-services/scripting/objects/action-element-assl.md), [статистической обработки](../../../analysis-services/scripting/objects/aggregation-element-assl.md), [AggregationDesign](../../../analysis-services/scripting/objects/aggregationdesign-element-assl.md), [сборки](../../../analysis-services/scripting/objects/assembly-element-assl.md), [AttributePermission](../../../analysis-services/scripting/objects/attributepermission-element-assl.md), [ CalculationProperty](../../../analysis-services/scripting/objects/calculationproperty-element-assl.md), [CellPermission](../../../analysis-services/scripting/objects/cellpermission-element-assl.md), [куба](../../../analysis-services/scripting/objects/cube-element-assl.md), [CubeDimensionPermission](../../../analysis-services/scripting/data-type/cubedimensionpermission-data-type-assl.md), [базы данных](../../../analysis-services/scripting/objects/database-element-assl.md) , [DataSource](../../../analysis-services/scripting/objects/datasource-element-assl.md), [DataSourceView](../../../analysis-services/scripting/objects/datasourceview-element-assl.md), [измерения](../../../analysis-services/scripting/objects/dimension-element-assl.md), [DimensionAttribute](../../../analysis-services/scripting/data-type/dimensionattribute-data-type-assl.md), [иерархии](../../../analysis-services/scripting/objects/hierarchy-element-assl.md), [Ключевого показателя эффективности](../../../analysis-services/scripting/objects/kpi-element-assl.md), [уровень](../../../analysis-services/scripting/objects/level-element-assl.md), [MdxScript](../../../analysis-services/scripting/objects/mdxscript-element-assl.md), [мер](../../../analysis-services/scripting/objects/measure-element-assl.md), [MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md), [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md), [MiningModelColumn](../../../analysis-services/scripting/data-type/miningmodelcolumn-data-type-assl.md), [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md), [MiningStructureColumn](../../../analysis-services/scripting/data-type/miningstructurecolumn-data-type-assl.md), [ Раздел](../../../analysis-services/scripting/objects/partition-element-assl.md), [разрешение](../../../analysis-services/scripting/data-type/permission-data-type-assl.md), [перспективы](../../../analysis-services/scripting/objects/perspective-element-assl.md), [роли](../../../analysis-services/scripting/objects/role-element-assl.md), [сервера](../../../analysis-services/scripting/objects/server-element-assl.md), [ Трассировки](../../../analysis-services/scripting/objects/trace-element-assl.md), [перевода](../../../analysis-services/scripting/objects/translation-element-assl.md)|  
|Дочерние элементы|None|  
  
## <a name="remarks"></a>Примечания  
 На значение элемента **Description** накладываются следующие ограничения.  
  
-   Значение не может содержать начальные или конечные пробелы. Если начальные или конечные пробелы будут включены в значение **описание** элемента, эти пробелы будут неявно удалены службой [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].  
  
-   Значение не может содержать управляющие символы. Если в значении содержатся управляющие символы **описание** , эти символы будут неявно удалены по [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].  
  
## <a name="see-also"></a>См. также  
 [Элемент Name &#40;ASSL&#41;](../../../analysis-services/scripting/properties/name-element-assl.md)   
 [Свойства & #40; ASSL & #41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
