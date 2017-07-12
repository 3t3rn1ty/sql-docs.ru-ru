---
title: "Последняя функция (построитель отчетов и службы SSRS) | Документы Microsoft"
ms.custom: 
ms.date: 03/07/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 123b78a0-d6c9-4f78-b0e7-73b21854a250
caps.latest.revision: 7
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: b3b3313f3622a613540c990273d457ddcad1a173
ms.contentlocale: ru-ru
ms.lasthandoff: 06/22/2017

---
# <a name="report-builder-functions---last-function"></a>О функциях построителя - функция Last
  Возвращает последнее значение указанного выражения для заданной области.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Last(expression, scope)  
```  
  
#### <a name="parameters"></a>Параметры  
 *expression*  
 (**Variant** или **Binary**) Выражение, к которому применяется статистическая обработка, например `=Fields!Fieldname.Value`.  
  
 *область*  
 (**String**) Имя набора данных, области данных или группы, содержащей элементы отчета, к которым применяется статистическая функция (необязательно). Если аргумент *scope* не задан, используется текущая область.  
  
## <a name="return-type"></a>Тип возвращаемых данных  
 Определяется типом выражения.  
  
## <a name="remarks"></a>Замечания  
 Функция **Last** возвращает конечное значение в набор данных после сортировки и фильтрации, примененных к заданной области.  
  
 Функция **Last** не может использоваться в критериях фильтра группирования с какой-либо областью, кроме текущей области (по умолчанию).  
  
 Также можно использовать **Last** в верхнем колонтитуле страницы для возвращения последнего значения из коллекции **ReportItems** для страницы, чтобы произвести словарные заголовки в первой и последней записях страницы.  
  
 Значение *scope* должно быть строковой константой и не может быть выражением. Для внешних агрегатов и агрегатов, в которых не задаются другие агрегаты, параметр *scope* должен ссылаться не текущую область или включающую область. Для агрегатов, содержащих агрегаты, во вложенных агрегатах может указываться дочерняя область.  
  
 *Expression* может содержать вызовы вложенных агрегатных функций со следующими условиями и исключениями.  
  
-   Параметр*Scope* для вложенных агрегатов должен совпадать с областью внешнего агрегата или входить в нее. Одна область из всех уникальных областей в выражении должна быть дочерней относительно всех других областей.  
  
-   Параметр*Scope* для вложенных агрегатов не может быть именем набора данных.  
  
-   *Expression* не может содержать функции **First**, **Last**, **Previous**и **RunningValue** .  
  
-   *Expression* не может содержать вложенные агрегаты, в которых указан параметр *recursive*.  
  
 Дополнительные сведения см. в разделах [Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](../../reporting-services/report-design/report-builder-functions-aggregate-functions-reference.md) и [Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)](../../reporting-services/report-design/expression-scope-for-totals-aggregates-and-built-in-collections.md).  
  
 Дополнительные сведения о рекурсивных агрегатах см. в разделе [Создание групп рекурсивной иерархии (построитель отчетов и службы SSRS)](../../reporting-services/report-design/creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).  
  
## <a name="example"></a>Пример  
 Следующий пример кода предоставляет номер последнего продукта в группе или области данных `Category` .  
  
```  
=Last(Fields!ProductNumber.Value, "Category")  
```  
  
## <a name="see-also"></a>См. также  
 [Использование выражений в отчетах (построитель отчетов и службы SSRS)](../../reporting-services/report-design/expression-uses-in-reports-report-builder-and-ssrs.md)   
 [Примеры выражений (построитель отчетов и службы SSRS)](../../reporting-services/report-design/expression-examples-report-builder-and-ssrs.md)   
 [Типы данных в выражениях (построитель отчетов и службы SSRS)](../../reporting-services/report-design/data-types-in-expressions-report-builder-and-ssrs.md)   
 [Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)](../../reporting-services/report-design/expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  