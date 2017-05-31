---
title: "Настройка пользователя для создания заданий агента SQL Server и управления ими | Документация Майкрософт"
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
- SQL Server Agent jobs, user configuration
- jobs [SQL Server Agent], user configuration
- SQLAgentUserRole database role
- proxy accounts [SQL Server Agent]
ms.assetid: 67897e3e-b7d0-43dd-a2e2-2840ec4dd1ef
caps.latest.revision: 5
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 2c0a85b70906a7784093ba1fb6905c27278176fa
ms.contentlocale: ru-ru
ms.lasthandoff: 04/11/2017

---
# <a name="configure-a-user-to-create-and-manage-sql-server-agent-jobs"></a>Настройка пользователя для создания заданий агента SQL Server и управления заданиями
В этом разделе описано, как настроить пользователя для создания или выполнения заданий агента [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] .  
  
-   **Перед началом работы:**  [безопасность](#Security)  
  
-   **Настройка пользователя для создания заданий агента SQL Server и управления ими с помощью следующих средств:**  [SQL Server Management Studio](#SSMS)  
  
## <a name="BeforeYouBegin"></a>Перед началом  
  
### <a name="Security"></a>безопасность  
Чтобы разрешить пользователю создавать задания агента [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] и управлять ими, необходимо сначала добавить существующее имя входа для SQL Server или роль базы данных msdb к одной из следующих предопределенных ролей базы данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] в базе данных msdb: SQLAgentUserRole, SQLAgentReaderRole или SQLAgentOperatorRole.  
  
По умолчанию члены этих ролей базы данных могут создавать свои собственные шаги заданий, которые запускаются сами по себе. Если пользователи, не являющиеся администраторами, желают выполнить задания, которые выполняют другие типы шагов заданий, например пакеты [!INCLUDE[ssIS](../../includes/ssis_md.md)] , им необходимо будет получить доступ к учетной записи-посреднику. Все члены предопределенной роли сервера sysadmin имеют разрешения на создание, изменение и удаление учетных записей-посредников. Дополнительные сведения о разрешениях, связанных с этими предопределенными ролями баз данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] , см. в разделе [Предопределенные роли базы данных агента SQL Server](../../ssms/agent/sql-server-agent-fixed-database-roles.md).  
  
#### <a name="Permissions"></a>Permissions  
Дополнительные сведения см. в разделе [Implement SQL Server Agent Security](../../ssms/agent/implement-sql-server-agent-security.md).  
  
## <a name="SSMS"></a>Использование среды SQL Server Management Studio  
**Добавление имени входа SQL или роли базы данных msdb к предопределенной роли базы данных агента SQL Server**  
  
1.  В **Обозревателе объектов**разверните сервер.  
  
2.  Разверните элемент **Безопасность**, а затем элемент **Имена входа**.  
  
3.  Щелкните правой кнопкой мыши имя входа, которое необходимо добавить к предопределенной роли базы данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] , и выберите пункт **Свойства**.  
  
4.  На странице **Сопоставление пользователей** диалогового окна **Свойства имени входа** выберите строку, содержащую базу данных **msdb**.  
  
5.  На вкладке **Членство в роли базы данных для: msdb**выберите соответствующую предопределенную роль базы данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] .  
  
**Настройка учетной записи-посредника для создания и управления шагами заданий агента SQL Server**  
  
1.  В **Обозревателе объектов**разверните сервер.  
  
2.  Разверните узел **Агент SQL Server**.  
  
3.  Щелкните правой кнопкой мыши элемент **Учетные записи-посредники** и выберите пункт **Создать учетную запись-посредник**.  
  
4.  На вкладке **Общие** диалогового окна **Создание учетной записи-посредника** укажите имя учетной записи-посредника, имя входа и описание. Обратите внимание, на то, что прежде чем создавать учетную запись-посредник агента SQL Server, необходимо создать учетные данные. Дополнительные сведения о создании учетных данных см. в разделах [Практическое руководство. Создание учетной записи (среда SQL Server Management Studio)](http://msdn.microsoft.com/en-us/c1e77e91-2a69-40d9-b8b3-97cffc710586) и [CREATE CREDENTIAL (Transact-SQL)](http://msdn.microsoft.com/en-us/d5e9ae69-41d9-4e46-b13d-404b88a32d9d).  
  
5.  Проверьте соответствующие подсистемы для этой учетной записи-посредника.  
  
6.  На вкладке **Участники** добавьте или удалите имена входа или роли, чтобы предоставить или отменить доступ к учетной записи-посреднику.  
  
## <a name="see-also"></a>См. также:  
[Обеспечение безопасности агента SQL Server](../../ssms/agent/implement-sql-server-agent-security.md)  
  
