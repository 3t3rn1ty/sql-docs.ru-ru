---
title: "BACKUP SERVICE MASTER KEY (Transact-SQL) | Документы Microsoft"
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- BACKUP SERVICE MASTER KEY
- DUMP_SERVICE_MASTER_KEY_TSQL
- DUMP SERVICE MASTER KEY
- BACKUP_SERVICE_MASTER_KEY_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- backing up service master keys [SQL Server]
- BACKUP SERVICE MASTER KEY statement
- cryptography [SQL Server], Service Master Key
- exporting Service Master Keys
- encryption [SQL Server], Service Master Key
- service master key [SQL Server], exporting
ms.assetid: f8356683-6680-4f1c-9eaf-5c29a9a9020d
caps.latest.revision: 29
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: dd3f95e0f3606d23dd1418b2cc0b3b32b5c61ac8
ms.contentlocale: ru-ru
ms.lasthandoff: 09/01/2017

---
# <a name="backup-service-master-key-transact-sql"></a>BACKUP SERVICE MASTER KEY (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Экспорт главного ключа службы.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
BACKUP SERVICE MASTER KEY TO FILE = 'path_to_file'   
    ENCRYPTION BY PASSWORD = 'password'  
```  
  
## <a name="arguments"></a>Аргументы  
 ФАЙЛ **= "***путь_к_файлу***"**  
 Указывает полный путь (включая имя файла) к файлу, в который будет выполнен экспорт главного ключа службы. Это может быть локальный путь или UNC-путь к сетевой папке.  
  
 ПАРОЛЬ **= "***пароль***"**  
 Пароль, используемый для шифрования главного ключа службы в файле резервной копии. Пароль проходит проверку сложности. Дополнительные сведения см. в разделе [Password Policy](../../relational-databases/security/password-policy.md).  
  
## <a name="remarks"></a>Замечания  
 Необходимо создавать резервные копии главного ключа службы и хранить их в безопасном, удаленном месте. Создание такой резервной копии должно быть одной из первых задач администрирования, выполненных на сервере.  
  
## <a name="permissions"></a>Permissions  
 Необходимо разрешение CONTROL SERVER на сервер.  
  
## <a name="examples"></a>Примеры  
 В следующем примере создается файл резервной копии главного ключа службы.  
  
```  
BACKUP SERVICE MASTER KEY TO FILE = 'c:\temp_backups\keys\service_master_key' ENCRYPTION BY PASSWORD = '3dH85Hhk003GHk2597gheij4';  
```  
  
## <a name="see-also"></a>См. также:  
 [ALTER SERVICE MASTER KEY &#40; Transact-SQL &#41;](../../t-sql/statements/alter-service-master-key-transact-sql.md)   
 [RESTORE SERVICE MASTER KEY (Transact-SQL)](../../t-sql/statements/restore-service-master-key-transact-sql.md)  
  
  