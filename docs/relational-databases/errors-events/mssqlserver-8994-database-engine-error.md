---
title: "MSSQLSERVER_8994 | Документация Майкрософт"
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords:
- 8994 (Database Engine error)
ms.assetid: 8f4b0e2f-04c0-46e4-9208-20a7085d7a1a
caps.latest.revision: 17
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 5bbe6e23318bf3590eccfa8e063af1b17a019485
ms.contentlocale: ru-ru
ms.lasthandoff: 04/11/2017

---
# <a name="mssqlserver8994"></a>MSSQLSERVER_8994
  
## <a name="details"></a>Сведения  
  
|||  
|-|-|  
|Название продукта|SQL Server|  
|Идентификатор события|8994|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|DBCC3_MISSING_FORWARDING_ROW|  
|Текст сообщения|На идентификатор объекта O_ID, страницу переадресованной строки P_ID1, область памяти S_ID1 должна указывать страница переадресующей строки P_ID2, область памяти S_ID2. Переадресующая строка не обнаружена. Возможно, произошла ошибка размещения.|  
  
## <a name="explanation"></a>Объяснение  
В переадресованной строке в куче отсутствует переадресующая строка, которая должна на нее указывать.  
  
## <a name="user-action"></a>Действие пользователя  
  
### <a name="look-for-hardware-failure"></a>Поиск сбоев оборудования  
Выполните диагностику оборудования и исправьте все найденные проблемы. Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования. Исправьте все неполадки оборудования, обнаруженные в журналах.  
  
Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему. Убедитесь, что в системе не включено кэширование записи для контроллера дисков. Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.  
  
В конце концов можно попробовать сменить оборудование. Это может включать форматирование дисков и переустановку операционной системы.  
  
### <a name="restore-from-backup"></a>Восстановление из резервной копии  
Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.  
  
### <a name="run-dbcc-checkdb"></a>Запуск DBCC CHECKDB  
Если безошибочной резервной копии нет, выполните инструкцию DBCC CHECKDB без предложения REPAIR, чтобы определить степень повреждения. Инструкция DBCC CHECKDB выдаст рекомендацию по тому, какое предложение REPAIR следует использовать. После этого выполните инструкцию DBCC CHECKDB с соответствующим предложением REPAIR, чтобы устранить повреждение.  
  
> [!CAUTION]  
> Если достоверно неизвестно, к каким последствиям приведет выполнение инструкции DBCC CHECKDB с выбранным предложением REPAIR, перед выполнением этой инструкции обратитесь к вашему основному поставщику услуг технической поддержки.  
  
Если в результате выполнения инструкции DBCC CHECKDB с одним из предложений REPAIR неполадка устранена не была, обратитесь к вашему основному поставщику услуг технической поддержки.  
  
#### <a name="results-of-running-repair-options"></a>Результаты выполнения инструкции REPAIR  
Переадресованная строка будет преобразована в обычную строку данных.  
  
