---
title: "(Деление) (DMX) | Документы Microsoft"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- DMX
helpviewer_keywords:
- / (divide)
- divide operator (/)
ms.assetid: 7afc06cd-054b-48c3-9c3c-9a0c17d15e63
caps.latest.revision: 14
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 8485c6e5cb68fcfd07f1ee812ba4c9a7035b1931
ms.contentlocale: ru-ru
ms.lasthandoff: 08/02/2017

---
# <a name="divide-dmx"></a>(Деление) (РАСШИРЕНИЯ ИНТЕЛЛЕКТУАЛЬНОГО АНАЛИЗА ДАННЫХ)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Выполняет арифметическую операцию, которая делит одно число на другое.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Dividend / Divisor  
```  
  
#### <a name="parameters"></a>Параметры  
 *Делимое*  
 Допустимое выражение расширений интеллектуального анализа данных, возвращающее числовое значение.  
  
 *Делитель*  
 Допустимое выражение расширений интеллектуального анализа данных, возвращающее числовое значение.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение с типом данных параметра, имеющего более высокий приоритет.  
  
## <a name="remarks"></a>Замечания  
 Значение, возвращаемое оператором, представляет собой частное от деления первого выражения на второе.  
  
 Оба выражения должны иметь одинаковый тип данных, или одно из выражений должно допускать неявное преобразование к типу данных другого выражения. Если делитель возвращает значение NULL, оператор выдает ошибку. Если как делитель, так и делимое возвращают значения NULL, оператор возвращает значение NULL.  
  
## <a name="see-also"></a>См. также:  
 [Арифметические операторы &#40; расширений интеллектуального анализа данных &#41;](../dmx/operators-arithmetic.md)   
 [Расширения интеллектуального анализа данных &#40; расширений интеллектуального анализа данных &#41; Справочник по операторам](../dmx/data-mining-extensions-dmx-operator-reference.md)   
 [Операторы &#40; расширений интеллектуального анализа данных &#41;](../dmx/operators-dmx.md)   
 [Деление &#40; Выражение служб SSIS &#41;](../integration-services/expressions/divide-ssis-expression.md)   
 [&#40; деления &#41; &#40; Transact-SQL &#41;](../t-sql/language-elements/divide-transact-sql.md)  
  
  
