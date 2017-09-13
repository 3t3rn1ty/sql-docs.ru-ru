---
title: "Учетные данные (Transact-SQL) в области базы данных GRANT | Документы Microsoft"
ms.custom: 
ms.date: 06/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GRANT DATABASE SCOPED CREDENTIAL
- GRANT_DATABASE_SCOPED_CREDENTIAL_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- granting permissions [SQL Server], database scoped credential
- permissions [SQL Server], database scoped credential
- database scoped credential [SQL Server], permissions
- GRANT statement, database scoped credentials
ms.assetid: 501f2c8a-6aeb-41af-bf0b-974d17af33c0
caps.latest.revision: 3
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 8fff82fbd6c81fea9cd9a7a95cabf35b0b8ecb7f
ms.contentlocale: ru-ru
ms.lasthandoff: 09/01/2017

---
# <a name="grant-database-scoped-credential-permissions-transact-sql"></a>В области базы данных GRANT разрешений учетных данных (Transact-SQL)
[!INCLUDE[tsql-appliesto-ssvNxt-asdb-xxxx-xxx](../../includes/tsql-appliesto-ssvnxt-asdb-xxxx-xxx.md)]

  Предоставление разрешений на базу данных учетные данные области. 
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
GRANT permission  [ ,...n ]    
    ON DATABASE SCOPED CREDENTIAL :: credential_name   
    TO principal [ ,...n ] [ WITH GRANT OPTION ]   
    [ AS granting_principal ]   
```  
  
## <a name="arguments"></a>Аргументы  
 *разрешение*  
 Указывает разрешение, которое может быть предоставлено в базе данных учетные данные области. Перечислены ниже.  
  
 В учетных данных области базы данных **::***credential_name*  
 Задает учетные данные уровня базы данных, которой предоставляется разрешение. Необходим квалификатор области «::».  
  
 *database_principal*  
 Участник, которому предоставляется разрешение. Это может быть:  
  
-   пользователь базы данных;  
-   роль базы данных;  
-   роль приложения;  
-   пользователь базы данных, сопоставленный с именем входа Windows;  
-   пользователь базы данных, сопоставленный с группой Windows;  
-   пользователь базы данных, сопоставленный с сертификатом;  
-   пользователь базы данных, сопоставленный асимметричному ключу;  
-   пользователь базы данных, не сопоставленный участнику [системы безопасности] на уровне сервера.  
  
GRANT OPTION  
 Показывает, что участнику будет дана возможность предоставлять указанное разрешение другим участникам.  
  
AS *granting_principal*  
 Указывает участника, от которого участник, выполняющий данный запрос, наследует право на предоставление разрешения. Это может быть:  
  
-   пользователь базы данных;  
-   роль базы данных;  
-   роль приложения;  
-   пользователь базы данных, сопоставленный с именем входа Windows;  
-   пользователь базы данных, сопоставленный с группой Windows;  
-   пользователь базы данных, сопоставленный с сертификатом;  
-   пользователь базы данных, сопоставленный асимметричному ключу;  
-   пользователь базы данных, не сопоставленный участнику [системы безопасности] на уровне сервера.  
  
## <a name="remarks"></a>Замечания  
 Учетные данные уровня базы данных — это защищаемый объект уровня базы данных, содержащихся в базе данных, которая является родительской в иерархии разрешений. Наиболее специфичные и ограниченные разрешения, которые могут быть предоставлены на учетные данные уровня базы данных, перечислены ниже вместе с более общими разрешениями, неявно их содержащими.  
  
|Разрешение учетных данных области базы данных|Содержится в разрешении учетные данные уровня базы данных|Содержится в разрешении базы данных|  
|----------------------------|---------------------------------------|------------------------------------|  
|CONTROL|CONTROL|CONTROL|  
|TAKE OWNERSHIP|CONTROL|CONTROL|  
|ALTER|CONTROL|CONTROL|  
|REFERENCES|CONTROL|REFERENCES|  
|VIEW DEFINITION|CONTROL|VIEW DEFINITION|  
  
## <a name="permissions"></a>Permissions  
 Объект, предоставляющий разрешение (или участник, указанный параметром AS), должен иметь либо само разрешение, выданное с помощью параметра GRANT OPTION, либо разрешение более высокого уровня, которое неявно включает предоставляемое.  
  
 Если используется параметр AS, налагаются следующие дополнительные требования.  
  
|AS *granting_principal*|Необходимо дополнительное разрешение|  
|------------------------------|------------------------------------|  
|Пользователь базы данных|Разрешение IMPERSONATE для пользователя, членство в **db_securityadmin** предопределенной роли базы данных, членство в **db_owner** предопределенной роли базы данных или членство в **sysadmin** предопределенной роли сервера.|  
|Пользователь базы данных, сопоставленный имени входа Windows|Разрешение IMPERSONATE для пользователя, членство в **db_securityadmin** предопределенной роли базы данных, членство в **db_owner** предопределенной роли базы данных или членство в **sysadmin** предопределенной роли сервера.|  
|Пользователь базы данных, сопоставленный группе Windows|Членство в группе Windows, членство в **db_securityadmin** предопределенной роли базы данных, членство в **db_owner** предопределенной роли базы данных или членство в **sysadmin**предопределенной роли сервера.|  
|Пользователь базы данных, сопоставленный сертификату|Членство в **db_securityadmin** предопределенной роли базы данных, членство в **db_owner** предопределенной роли базы данных или членство в **sysadmin** предопределенной роли сервера.|  
|Пользователь базы данных, сопоставленный асимметричному ключу|Членство в **db_securityadmin** предопределенной роли базы данных, членство в **db_owner** предопределенной роли базы данных или членство в **sysadmin** предопределенной роли сервера.|  
|Пользователь базы данных, не сопоставленный ни с одним участником на уровне сервера|Разрешение IMPERSONATE для пользователя, членство в **db_securityadmin** предопределенной роли базы данных, членство в **db_owner** предопределенной роли базы данных или членство в **sysadmin** предопределенной роли сервера.|  
|Роль базы данных|Разрешение ALTER для роли, членство в **db_securityadmin** предопределенной роли базы данных, членство в **db_owner** предопределенной роли базы данных или членство в **sysadmin**предопределенной роли сервера.|  
|Роль приложения|Разрешение ALTER для роли, членство в **db_securityadmin** предопределенной роли базы данных, членство в **db_owner** предопределенной роли базы данных или членство в **sysadmin**предопределенной роли сервера.|  
  
 Владельцы объектов могут предоставлять разрешения на объекты, которыми они владеют. Участники, имеющие разрешение CONTROL на защищаемый объект, могут предоставлять разрешение на этот защищаемый объект.  
  
 Участники, заведующие выдачей разрешений CONTROL SERVER, такие как члены **sysadmin** фиксированной серверной роли, могут предоставлять любое разрешение на любой защищаемый объект сервера. Участник, получивший разрешение CONTROL на базу данных, такие как члены **db_owner** предопределенной роли базы данных, могут предоставлять любое разрешение на любой защищаемый объект в базе данных. Владельцы разрешения CONTROL, связанного со схемой, могут предоставлять любые разрешения на работу с любыми объектами, содержащимися в данной схеме.  
  
## <a name="see-also"></a>См. также:  
 [GRANT (Transact-SQL)](../../t-sql/statements/grant-transact-sql.md)   
 [В области базы данных REVOKE учетных данных (Transact-SQL)](../../t-sql/statements/revoke-database-scoped-credential-transact-sql.md)   
 [ЗАПРЕЩАЮЩИЕ области базы данных учетных данных (Transact-SQL)](../../t-sql/statements/deny-database-scoped-credential-transact-sql.md)   
 [Разрешения (компонент Database Engine)](../../relational-databases/security/permissions-database-engine.md)   
 [Участники (компонент Database Engine)](../../relational-databases/security/authentication-access/principals-database-engine.md)   
 [Иерархия шифрования](../../relational-databases/security/encryption/encryption-hierarchy.md)  
  
  
