---
title: Элемент ImpersonationMode (ASSL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- ImpersonationMode Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- ImpersonateMode
helpviewer_keywords:
- ImpersonateMode element
ms.assetid: 160fdcb2-ac9f-4c5a-a0eb-a5f7669166b9
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 87a68d6ef1035d7caf1d787d9ab44578d17c5489
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48105153"
---
# <a name="impersonationmode-element-assl"></a>Элемент ImpersonationMode (ASSL)
  Содержит значение, указывающее метод олицетворения для элементов, которые являются производными от [ImpersonationInfo](../data-type/impersonationinfo-data-type-assl.md) тип данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
  
<ImpersonationInfo>  
   ...  
   <ImpersonationMode>...</ImpersonationMode>  
  
</ImpersonationInfo>...  
```  
  
## <a name="element-characteristics"></a>Характеристики элемента  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|Тип данных и длина|String (перечисление)|  
|Значение по умолчанию|*По умолчанию*|  
|Количество элементов|0-1: необязательный элемент, который может встречаться только один раз.|  
  
## <a name="element-relationships"></a>Связи элемента  
  
|Связь|Элемент|  
|------------------|-------------|  
|Родительский элемент|[ImpersonationInfo](../data-type/impersonationinfo-data-type-assl.md)|  
|Дочерние элементы|None|  
  
## <a name="remarks"></a>Примечания  
 Значением этого элемента может быть только одна из строк в следующей таблице.  
  
|Значение|Описание|  
|-----------|-----------------|  
|*По умолчанию*|В родительском объекте используется метод олицетворения, наиболее подходящий для контекста, в котором применяется олицетворение.|  
|*ImpersonateAccount*|В родительском объекте используются учетные данные учетной записи пользователя, которая указана в родительском элементе.|  
|*ImpersonateAnonymous*|В родительском объекте используются учетные данные анонимного пользователя.|  
|*ImpersonateCurrentUser*|В родительском объекте используются учетные данные текущего пользователя.|  
|*ImpersonateServiceAccount*|В родительском объекте используются учетные данные учетной записи службы, которая связана с экземпляром [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].|  
  
 Перечисление, соответствующее допустимым значениям элемента `ImpersonationMode` в модели объектов AMO, — это <xref:Microsoft.AnalysisServices.ImpersonationLevel>.  
  
## <a name="see-also"></a>См. также  
 [Свойства &#40;ASSL&#41;](properties-assl.md)  
  
  
