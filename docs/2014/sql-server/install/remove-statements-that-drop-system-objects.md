---
title: Удалите инструкции, удаляющие системные объекты | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- drop system objects [SQL Server]
ms.assetid: cdfc3c50-c801-4039-a4bf-b35f876f1c61
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: e1f355b9e13bb85f1bc91d9626e27d6ee3fafa15
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48153727"
---
# <a name="remove-statements-that-drop-system-objects"></a>Удалите инструкции, которые удаляют системные объекты
  Советник по переходу обнаружил инструкции, удаляющие системные объекты. Системные объекты, включая расширенные хранимые процедуры, развертываются в базе данных **resource** , доступной только для чтения (mssqlsystemresource), и не могут быть удалены. Измените свои приложения так, чтобы они отменяли или запрещали разрешение EXECUTE для системных объектов.  
  
## <a name="component"></a>Компонент  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a>Описание  
 Такие инструкции, как DROP TABLE, DROP PROCEDURE и **sp_dropextendedproc** , не могут использоваться для удаления системных объектов, поскольку эти объекты развернуты в базе данных **resource** , доступной только для чтения.  
  
## <a name="corrective-action"></a>Действие по исправлению  
 Удалите из своих приложений все инструкции, которые пытаются удалить системные объекты. Измените свои приложения так, чтобы они отменяли или запрещали разрешение EXECUTE для системных объектов. В качестве альтернативы для отключения некоторых из этих объектов можно воспользоваться средством настройки контактной зоны (SAC). Например, с помощью средства SAC можно отключить или включить расширенную хранимую процедуру **xp_cmdshell** .  
  
## <a name="see-also"></a>См. также  
 [Проблемы обновления компонента Database Engine](../../../2014/sql-server/install/database-engine-upgrade-issues.md)   
 [Помощник по обновлению SQL Server 2014 &#91;new&#93;](/sql/2014/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  
