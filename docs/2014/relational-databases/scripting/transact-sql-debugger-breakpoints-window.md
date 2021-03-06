---
title: Окно "Точки останова" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
f1_keywords:
- vs.debug.breakpoints
helpviewer_keywords:
- Breakpoints Window [Transact-SQL]
ms.assetid: bad88d10-fdd5-4d3d-b5ea-a4f063847485
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 2a8cb745670ebfe1c9a8a08eb4674e0a3755cc50
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48170724"
---
# <a name="breakpoints-window"></a>Окно точек останова
  В окне **Точки останова** перечисляются все точки останова, которые заданы в текущем редакторе запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] . Чтобы управлять точками останова, используйте панель инструментов в окне **Точки останова** . Точки останова представляют собой точки кода, где выполнение в режиме отладке приостанавливается, чтобы можно было просматривать отладочные данные.  
  
## <a name="task-list"></a>Список задач  
 **Доступ к окну «Точки останова»**  
  
-   В меню **Отладка** выберите пункт **Окна**, а затем **Точки останова**.  
  
## <a name="breakpoints-window-columns"></a>Столбцы окна «Точки останова»  
 По умолчанию в окне **Точки останова** перечислены следующие столбцы.  
  
 **Название**  
 Отображается имя точки останова. Имена точек останова предоставляются отладчиком. Это имя включает имя окна редактора запросов компонента Database Engine, которое содержит точку останова, и номер строки в редакторе запросов, на которой задана точка останова.  
  
 **Условие**  
 Отображает **(нет условия)**. Отладчик [!INCLUDE[tsql](../../includes/tsql-md.md)] не поддерживает задание условий точки останова.  
  
 **Число попаданий**  
 Отображает**всегда выполнять останов**.  
  
 Можно добавлять и удалять следующие столбцы, выбирая их в списке **Столбцы** .  
  
 **Фильтр**  
 Отображает **(нет)**. Отладчик [!INCLUDE[tsql](../../includes/tsql-md.md)] не поддерживает задание фильтров для точек останова.  
  
 **При попадании**  
 Отображает **Останов**.  
  
 **Язык**  
 Отображает значение **Transact-SQL** для [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
 **Компонент**  
 Отображается номер строки, на которой задана точка останова.  
  
 **Файл**  
 Отображается имя исходного файла, который содержит точку останова, и номер строки, на которой задана точка останова.  
  
 **Адрес**  
 Отладчик [!INCLUDE[tsql](../../includes/tsql-md.md)] не поддерживает эту функцию.  
  
 **Процесс**  
 Отображает **[SQL]** , указывая, что это — процесс компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] . Затем следует имя экземпляра компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , в котором выполняется код.  
  
## <a name="breakpoints-window-toolbar"></a>Панель инструментов окна «Точки останова»  
 Если в текущем окне редактора запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] имеются активные точки останова, то в окне **Точки останова** отображается панель инструментов, с помощью которой можно управлять точками останова.  
  
 **Удаление**  
 Удаляет выбранную точку останова.  
  
 **Удалить все точки останова**  
 Удаляет все точки останова, которые показаны в окне **Точки останова** .  
  
 **Отключить все точки останова**  
 Отключает все точки останова, чтобы они больше не останавливали выполнение кода, но точки останова сохраняются. После отключения всех точек останова эта кнопка становится кнопкой **Включить все точки останова**.  
  
 **Включить все точки останова**  
 Включает все точки останова, чтобы они останавливали выполнение кода. После включения всех точек останова эта кнопка становится кнопкой **Отключить все точки останова**.  
  
 **К исходному коду**  
 Помещает курсор на строку в редакторе запросов, которая содержит выбранную точку останова.  
  
 **Столбцы**  
 Содержит список всех столбцов, которые могут быть показаны в окне **Точки останова** . Флажками обозначены показанные столбцы. Чтобы добавить или удалить столбец в окне **Точки останова** , выберите этот столбец в списке.  
  
## <a name="see-also"></a>См. также  
 [Отладчик Transact-SQL](transact-sql-debugger.md)  
  
  
