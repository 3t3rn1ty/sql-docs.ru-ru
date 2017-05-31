---
title: "Открытие конструктора запросов и представлений (визуальные инструменты для баз данных) | Документация Майкрософт"
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
- opening View Designer
- View Designer, opening
- Query Designer [SQL Server], opening
- opening Query Designer
ms.assetid: b473f258-d53c-41c0-9ad9-528a2ff141f4
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 6d4b09ac45528392c55f47ab7b62ed7881a1ebc9
ms.contentlocale: ru-ru
ms.lasthandoff: 04/11/2017

---
# <a name="open-the-query-and-view-designer-visual-database-tools"></a>Открытие конструктора запросов и представлений (визуальные инструменты для баз данных)
Конструктор запросов и представлений открывается при открытии определения представления, показе результатов запроса или представления, при создании или открытии запроса. Он состоит из четырех отдельных панелей.  
  
-   Панель диаграмм представляет в графическом виде таблицы или возвращающие табличное значение объекты, выбранные из подключения к данным. Отображаются также все связи соединений между ними.  
  
-   Вводя значения в табличную сетку, на панели критериев можно указывать параметры запроса, например: какие из столбцов данных следует отображать, как упорядочивать результаты, какие строки выделить.  
  
-   Панель SQL можно использовать для создания собственных инструкций SQL; можно также создать инструкцию на панели критериев или панели диаграмм, и на панели SQL будут созданы инструкции SQL. После построения запрос автоматически обновляется и переформатируется на панели SQL, становясь удобным для чтения.  
  
-   Панель результатов показывает результаты выполнения самого последнего запроса Select (результаты запросов других типов отображаются в окнах сообщений).  
  
-   Эти панели полезны для работы с запросами и представлениями.  
  
-   При открытии представления или запроса одновременно открываются некоторые или все панели. Какая именно панель открывается, зависит от настроек в диалоговом окне **Параметры** и от текущей системы управления базами данных. По умолчанию, открываются все четыре панели.  
  
### <a name="to-open-the-query-and-view-designer-for-a-view"></a>Открытие конструктора запросов и представлений для представления  
  
1.  В обозревателе объектов щелкните правой кнопкой мыши нужное представление и выберите команду **Конструктор** или **Открыть представление**.  
  
    При выборе команды **Конструктор**панели конструктора запросов и представлений открываются с учетом параметров, заданных в диалоговом окне **Параметры** . При выборе пункта меню **Открыть представление**по умолчанию открывается только панель результатов.  
  
### <a name="to-open-the-query-and-view-designer-for-an-existing-query"></a>Открытие конструктора запросов и представлений для существующего запроса  
  
1.  В обозревателе решений разверните папку **Запросы** .  
  
2.  Дважды щелкните мышью открываемый запрос.  
  
3.  Выделите инструкции запроса, щелкните правой кнопкой мыши выделенную область и выберите команду **Создать запрос в редакторе**.  
  
## <a name="see-also"></a>См. также:  
[Разделы по конструированию запросов и представлений (визуальные инструменты для баз данных)](../../ssms/visual-db-tools/design-queries-and-views-how-to-topics-visual-database-tools.md)  
[Инструменты конструктора запросов и представлений (визуальные инструменты для баз данных)](../../ssms/visual-db-tools/query-and-view-designer-tools-visual-database-tools.md)  
  
