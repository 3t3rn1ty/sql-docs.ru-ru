---
title: UNION (многомерные Выражения) | Документы Microsoft
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: e51749416c0668ccc4760132bb860121ebae6e3d
ms.sourcegitcommit: 97bef3f248abce57422f15530c1685f91392b494
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34743493"
---
# <a name="union--mdx"></a>UNION (многомерные Выражения)


  Возвращает набор, порожденный объединением двух наборов, по желанию сохраняя повторяющиеся элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Standard syntax  
Union(Set_Expression1, Set_Expression2 [,...n][, ALL])  
  
Alternate syntax 1  
Set_Expression1 + Set_Expression2 [+...n]  
  
Alternate syntax 2  
{Set_Expression1 , Set_Expression2 [,...n]}  
```  
  
## <a name="arguments"></a>Аргументы  
 *Выражение набора 1*  
 Допустимое многомерное выражение, возвращающее набор.  
  
 *Выражение набора 2*  
 Допустимое многомерное выражение, возвращающее набор.  
  
## <a name="remarks"></a>Примечания  
 Эта функция возвращает объединение двух или более заданных наборов *.* При использовании стандартного синтаксиса и первого альтернативного варианта дубликаты исключаются по умолчанию. При использовании стандартного синтаксиса с помощью **все** флаг сохраняет дубликаты в объединенном наборе. Дубликаты удаляются из конца набора. При использовании второго альтернативного варианта синтаксиса дубликаты всегда сохраняются.  
  
## <a name="examples"></a>Примеры  
 В следующих примерах демонстрируется поведение **объединения** функции с помощью каждого из синтаксисов.  
  
### <a name="standard-syntax-duplicates-eliminated"></a>Стандартный синтаксис, дубликаты исключаются  
  
```  
SELECT Union   
   ([Date].[Calendar Year].children  
   , {[Date].[Calendar Year].[CY 2002]}  
   , {[Date].[Calendar Year].[CY 2003]}  
   ) ON 0  
FROM [Adventure Works]  
  
```  
  
### <a name="standard-syntax-duplicates-retained"></a>Стандартный синтаксис, дубликаты сохраняются  
  
```  
SELECT Union   
   ([Date].[Calendar Year].children  
   , {[Date].[Calendar Year].[CY 2002]}  
   , {[Date].[Calendar Year].[CY 2003]}  
   , ALL  
   ) ON 0  
FROM [Adventure Works]  
  
```  
  
### <a name="alternate-syntax-1-duplicates-eliminated"></a>Первый альтернативный синтаксис, дубликаты исключаются  
  
```  
SELECT   
   [Date].[Calendar Year].children   
   + {[Date].[Calendar Year].[CY 2002]}   
   + {[Date].[Calendar Year].[CY 2003]} ON 0  
FROM [Adventure Works]  
  
```  
  
### <a name="alternate-syntax-2-duplicates-retained"></a>Второй альтернативный синтаксис, дубликаты сохраняются  
  
```  
SELECT   
   {[Date].[Calendar Year].children  
   , [Date].[Calendar Year].[CY 2002]  
   , [Date].[Calendar Year].[CY 2003]} ON 0  
FROM [Adventure Works]  
  
```  
  
## <a name="see-also"></a>См. также  
 [+ &#40;Объединения&#41; &#40;многомерных Выражений&#41;](../mdx/union-mdx-operator-reference.md)   
 [Справочник по функциям многомерных Выражений &#40;многомерных Выражений&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
