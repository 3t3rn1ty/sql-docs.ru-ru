---
title: "Автоматическое удаление задания | Документация Майкрософт"
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
- dropping jobs
- SQL Server Agent jobs, removing
- automatic job removal
- jobs [SQL Server Agent], deleting
- deleting jobs
- removing jobs
ms.assetid: 92dbb6da-5919-4bde-9354-d454e9ea3da0
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: a8f3813b1a04cde1ce2d48d1859292f97519aabf
ms.contentlocale: ru-ru
ms.lasthandoff: 04/11/2017

---
# <a name="automatically-delete-a-job"></a>Автоматическое удаление задания
В этом разделе описывается настройка агента [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] в [!INCLUDE[ssCurrent](../../includes/sscurrent_md.md)] для автоматического удаления заданий, когда они успешно или неуспешно завершаются или выполняются с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)] или управляющих объектов SQL Server.  
  
Ответы заданий дают гарантию того, что администраторы базы данных будут знать о завершении выполнения заданий и частоте их выполнения. Обычными ответами заданий являются следующие.  
  
-   Уведомление оператора с помощью электронной почты, системы пейджинга или сообщения **net send** .  
  
    Используйте один из этих ответов на задание, если оператор должен выполнить последующие действия. Например, после успешного выполнения задания резервного копирования оператор должен получить напоминание об удалении магнитной ленты с резервной копией и сохранении ее в безопасном месте.  
  
-   Запись сообщений о событиях в журнал приложений Windows.  
  
    Этот ответ можно использовать только для неудачно завершившихся заданий.  
  
-   Автоматическое удаление задания.  
  
    Используйте этот ответ только тогда, когда есть уверенность в том, что не понадобится выполнять это задание повторно.  
  
**В этом разделе**  
  
-   **Перед началом работы выполните следующие действия.**  
  
    [безопасность](#Security)  
  
-   **Для задания ответов заданий используется:**  
  
    [Среда Среда SQL Server Management Studio](#SSMS)  
  
    [Управляющие объекты SQL Server](#SMO)  
  
## <a name="BeforeYouBegin"></a>Перед началом  
  
### <a name="Security"></a>безопасность  
Дополнительные сведения см. в разделе [Implement SQL Server Agent Security](../../ssms/agent/implement-sql-server-agent-security.md).  
  
## <a name="SSMS"></a>Использование среды SQL Server Management Studio  
  
#### <a name="to-automatically-delete-a-job"></a>Автоматическое удаление задания  
  
1.  В **обозревателе объектов** подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion_md.md)]и разверните его.  
  
2.  Разверните узел **Агент SQL Server**, выберите раздел **Задания**, щелкните правой кнопкой мыши задание, которое нужно изменить, и выберите пункт **Свойства**.  
  
3.  Выберите страницу **Уведомления** .  
  
4.  Поставьте флажок **Автоматически удалить задание**и выберите одно из следующих.  
  
    -   Чтобы задание автоматически удалялось при его успешном завершении, выберите пункт **При успешном завершении задания** .  
  
    -   Чтобы задание автоматически удалялось в случае неуспешного завершения, выберите пункт **При ошибке задания** .  
  
    -   Чтобы задание автоматически удалялось по завершении в любом случае, выберите пункт **По завершении задания** .  
  
## <a name="SMO"></a>Использование управляющих объектов SQL Server  
**Автоматическое удаление задания**  
  
Используйте свойство **DeleteLevel** класса **Job** на любом языке программирования, таком как Visual Basic, Visual C# или PowerShell. Дополнительные сведения см. в статье [Управляющие объекты SQL Server (SMO)](http://msdn.microsoft.com/library/ms162169.aspx).  
  
