---
title: "MSSQLSERVER_5235 | Документация Майкрософт"
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
- 5235 (Database Engine error)
ms.assetid: 1aa7e6a5-7ccb-43c8-a1fd-d50e92e0a798
caps.latest.revision: 16
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: bb6ed08c7ffad0e723dea7ad4774439049de3d99
ms.contentlocale: ru-ru
ms.lasthandoff: 04/11/2017

---
# <a name="mssqlserver5235"></a>MSSQLSERVER_5235
  
## <a name="details"></a>Сведения  
  
|||  
|-|-|  
|Название продукта|SQL Server|  
|Идентификатор события|5235|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|DBCC4_ERRORLOG_SUMMARY_PREMATURE_TERMINATION|  
|Текст сообщения|Аварийное завершение инструкции [EMERGENCY] DBCC DBCC_COMMAND_DETAILS, выполненной пользователем USER_NAME, в результате ошибки с состоянием ERROR_STATE. Затраченное время: HOURS часы MINUTES минуты SECONDS секунды.|  
  
## <a name="explanation"></a>Объяснение  
Это сообщение сводки, которое DBCC распечатывает в журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при аварийном завершении во время выполнения команды. Состояние ошибки в сообщении определяет тип аварийного завершения.  
  
В следующей ниже таблице приведены состояния ошибок и их определения.  
  
|Состояние ошибки|Определение|  
|---------------|--------------|  
|Состояние 0|Инструкция завершена из-за неустранимого повреждения метаданных. Это сообщение будет сопровождаться одним или несколькими экземплярами ошибки 8930.|  
|Состояние 1|Инструкция завершена из-за сбоя выполнения внутренней проверки. Это сообщение будет сопровождаться одним или несколькими экземплярами ошибки 8967.|  
|Состояние 2|Основной системной таблице не удалось выполнить проверку базовых системных таблиц подсистемы хранилища. Это сообщение будет сопровождаться одним или несколькими экземплярами ошибок [7984](../../relational-databases/errors-events/mssqlserver-7984-database-engine-error.md), 7985, [7986](~/relational-databases/errors-events/mssqlserver-7986-database-engine-error.md), [7987](~/relational-databases/errors-events/mssqlserver-7987-database-engine-error.md) или [7988](~/relational-databases/errors-events/mssqlserver-7988-database-engine-error.md).|  
|Состояние 3|Произошел сбой при аварийном восстановлении DBCC, поскольку базу данных не удалось запустить после перестроения журнала транзакций. Это сообщение будет сопровождаться ошибкой 7909.|  
|Состояние 4|Во время выполнения команды произошло нарушение предположения или нарушение доступа.|  
|Состояние 5|Возникла неизвестная ошибка, которая привела к непредвиденному завершению команды DBCC.|  
  
## <a name="user-action"></a>Действие пользователя  
В следующей таблице приведены действия пользователя, соответствующие указанному состоянию ошибки.  
  
|Состояние ошибки|Действие пользователя|  
|---------------|---------------|  
|Состояние 0|Выполните восстановление из резервной копии.|  
|Состояние 1|Обратитесь в службу поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)] (CSS).|  
|Состояние 2|Выполните восстановление из резервной копии.|  
|Состояние 3|Выполните восстановление из резервной копии.|  
|Состояние 4|Обратитесь в службу поддержки пользователей.|  
|Состояние 5|Запустите команду еще раз: если устранить неполадку не удается, обратитесь в службу поддержки пользователей.|  
  
## <a name="see-also"></a>См. также:  
[DBCC (Transact-SQL)](~/t-sql/database-console-commands/dbcc-transact-sql.md)  
  
