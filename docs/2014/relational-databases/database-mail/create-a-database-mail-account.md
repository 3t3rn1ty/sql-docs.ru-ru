---
title: Создание учетной записи компонента Database Mail | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], accounts
- accounts [Database Mail]
ms.assetid: c07abbc6-fc6a-470b-8fa3-532f2e06b16a
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 0d066f107460e9671d4f5840271d8c4a466eb968
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48081392"
---
# <a name="create-a-database-mail-account"></a>Создание учетной записи компонента Database Mail
  Для создания учетной записи компонента Database Mail применяется **мастер настройки компонента Database Mail** или [!INCLUDE[tsql](../../includes/tsql-md.md)] .  
  
-   **Перед началом работы:**  [необходимые компоненты](#Prerequisites)  
  
-   **Создание учетной записи компонента Database Mail с использованием следующих средств:**  [мастер настройки компонента Database Mail](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)  
  
-   **Дальнейшие действия.**  [Следующие шаги настройки компонента Database Mail](#FollowUp)  
  
##  <a name="BeforeYouBegin"></a> Перед началом  
  
###  <a name="Prerequisites"></a> необходимые компоненты  
  
-   Определите имя сервера и номер порта для сервера протокола SMTP, который используется для отправки электронной почты. Если SMTP-сервер требует проверки подлинности, определите имя пользователя и пароль для SMTP-сервера.  
  
-   Также можно указать тип сервера и номер его порта. Для исходящих сообщений всегда используется тип сервера «SMTP». Большинство SMTP-серверов по умолчанию используют порт 25.  
  
##  <a name="SSMSProcedure"></a> Использование мастера настройки компонента Database Mail  
 **Создание учетной записи компонента Database Mail с использованием мастера**  
  
-   В обозревателе объектов подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , для которого необходимо настроить компонент Database Mail, и разверните дерево сервера.  
  
-   Разверните узел **Управление**  
  
-   Дважды щелкните компонент Database Mail, чтобы открыть мастер настройки компонента Database Mail.  
  
-   На странице **Выбор задачи настройки** выберите **Управление учетными записями и профилями компонента Database Mail**и нажмите **Далее**.  
  
-   На странице **Управление учетными записями и профилями** выберите **Создать новую учетную запись** и нажмите **Далее**.  
  
-   На странице **Создать учетную запись** задайте имя учетной записи, описание, сведения о почтовом сервере и тип проверки подлинности. Нажмите кнопку **Далее**  
  
-   На странице **Завершение работы мастера** просмотрите действия, подлежащие выполнению, и нажмите **Готово** , чтобы завершить создание новой учетной записи.  
  
##  <a name="TsqlProcedure"></a> Использование Transact-SQL  
 **Создание учетной записи компонента Database Mail с помощью инструкций Transact-SQL**  
  
 Выполните хранимую процедуру **msdb.dbo.sysmail_add_account_sp** , чтобы создать учетную запись, и задайте следующие сведения:  
  
-   Имя создаваемой учетной записи.  
  
-   Необязательное описание учетной записи.  
  
-   Обратный адрес электронной почты, который будет вставляться в исходящие электронные сообщения.  
  
-   Имя отправителя, которое будет отображаться в исходящих электронных сообщениях.  
  
-   Имя SMTP-сервера.  
  
-   Имя пользователя для входа на SMTP-сервер, если этот сервер требует проверки подлинности.  
  
-   Пароль для входа на SMTP-сервер, если этот сервер требует проверки подлинности.  
  
 В следующем примере создается новая учетная запись компонента Database Mail.  
  
```  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Administrator',  
    @description = 'Mail account for administrative e-mail.',  
    @email_address = 'dba@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
```  
  
##  <a name="FollowUp"></a> Дальнейшие действия. Следующие шаги настройки компонента Database Mail  
  
-   [Создание профиля компонента Database Mail](create-a-database-mail-profile.md)  
  
  
