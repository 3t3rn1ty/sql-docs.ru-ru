---
title: "Переупорядочение выходных столбцов (визуальные инструменты для баз данных) | Документация Майкрософт"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- reordering output columns [SQL Server]
- output columns [SQL Server]
ms.assetid: 76462885-de4a-4290-a26b-90696d3671f4
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 155ed404983ad72dadefc9aa8d7a6a93e27a2619
ms.contentlocale: ru-ru
ms.lasthandoff: 04/11/2017

---
# <a name="reorder-output-columns-visual-database-tools"></a>Переупорядочение выходных столбцов (визуальные инструменты для баз данных)
Порядком, в соответствии с которым столбцы данных добавляются в запрос Select, определяется порядок, в котором они будут представлены в результатах. Первый столбец, добавляемый в запрос, в результатах располагается в крайней левой позиции, второй добавляемый в запрос столбец следует за ним и т. д.  
  
При создании запросов Update или Insert порядок добавления столбцов влияет на порядок обработки данных.  
  
Переупорядочивая столбцы, можно изменять местоположение столбца данных в результирующем наборе или порядок его использования.  
  
### <a name="to-reorder-columns-for-output"></a>Переупорядочение столбцов для вывода  
  
1.  На [панели критериев](../../ssms/visual-db-tools/criteria-pane-visual-database-tools.md)выберите строку, содержащую столбец, нажав кнопку выбора слева от строки.  
  
2.  Укажите кнопку выбора строки и перетащите строку в новое место.  
  
    -или-  
  
    Измените порядок имен столбцов на [панели SQL](../../ssms/visual-db-tools/sql-pane-visual-database-tools.md).  
  
> [!TIP]  
> Можно добавить строку данных в определенную позицию на панель критериев, вставив пустую строку на панель критериев, а затем указав столбец данных для вставки. Дополнительные сведения см. в разделе [Добавление столбцов в запросы (визуальные инструменты для баз данных)](../../ssms/visual-db-tools/add-columns-to-queries-visual-database-tools.md).  
  
## <a name="see-also"></a>См. также:  
[Результаты запросов сортировки и группирования (визуальные инструменты для баз данных)](../../ssms/visual-db-tools/sort-and-group-query-results-visual-database-tools.md)  
[Резюмирование результатов запросов (визуальные инструменты для баз данных)](../../ssms/visual-db-tools/summarize-query-results-visual-database-tools.md)  
[Выполнение основных операций с запросами (визуальные инструменты для баз данных)](../../ssms/visual-db-tools/perform-basic-operations-with-queries-visual-database-tools.md)  
  
