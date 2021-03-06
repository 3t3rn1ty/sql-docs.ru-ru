---
title: Пример. Поэтапное восстановление некоторых файловых групп (простая модель восстановления) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: backup-restore
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- piecemeal restores [SQL Server], simple recovery model
- restore sequences [SQL Server], piecemeal
- simple recovery model [SQL Server], RESTORE examples
ms.assetid: d7ad026c-5355-4308-9560-0dc843940d4f
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 3edbf01717882a696dd9592d545ee29f0603f0fc
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2018
ms.locfileid: "47690532"
---
# <a name="example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model"></a>Пример. Поэтапное восстановление отдельных файловых групп (простая модель восстановления)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

  Данный раздел относится только к базам данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которые содержат доступные только для чтения файловые группы в простой модели восстановления.  
  
 При поэтапной последовательности восстановления база данных восстанавливается в течение нескольких этапов на уровне файловой группы, начиная с первичной, и всех вторичных файловых групп, доступных для чтения и записи.  
  
 В этом примере база данных с именем `adb`, которая использует простую модель восстановления, содержит три файловые группы. Файловая группа `A` доступна для записи и для чтения, файловые группы `B` и `C` доступны только для чтения. Изначально все файловые группы находятся в режиме в сети.  
  
 Первичная группа и файловая группа `B` базы данных `adb` повреждены, поэтому администратор базы данных решает восстановить их с помощью последовательности поэтапного восстановления. При использовании простой модели восстановления все файловые группы, доступные для чтения и записи, должны быть восстановлены из той же частичной резервной копии. Хотя файловая группа `A` не повреждена, но для обеспечения согласованности данных она должна быть восстановлена вместе с первичной файловой группой (база данных будет восстановлена в том виде, который она имела к концу последнего частичного резервного копирования). Файловая группа `C` не повреждена, но она должна быть восстановлена для перевода ее в режим в сети. Файловая группа `B`, даже если она повреждена, содержит меньше важных данных, чем файловая группа `C`, поэтому `B` будет восстановлена в последнюю очередь.  
  
## <a name="restore-sequences"></a>Последовательности восстановления  
  
> [!NOTE]  
>  Синтаксис последовательности восстановления в сети тот же самый, что и в случае последовательности восстановления вне сети.  
  
1.  Частичное восстановление первичной группы и файловой группы `A` из частичной резервной копии.  
  
    ```  
    RESTORE DATABASE adb READ_WRITE_FILEGROUPS FROM partial_backup   
    WITH PARTIAL, RECOVERY  
    ```  
  
     На этом этапе первичная файловая группа и файловая группа `A` работают в режиме в сети. Файлы в файловых группах `B` и `C` ожидают восстановления, поэтому находятся в режиме вне сети.  
  
2.  Восстановление файловой группы `C`в режиме в сети.  
  
     Файловая группа `C` согласована, потому что восстановленная выше резервная копия была сделана после того, как эту группу `C` перевели в режим только для чтения, несмотря на то, что в результате восстановления произошел откат базы данных на более ранний момент времени. Администратор базы данных восстанавливает файловую группу `C`, не восстанавливая ее из копии, чтобы перевести в режим в сети.  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='C' WITH RECOVERY  
    ```  
  
     На этом этапе первичная файловая группа и файловые группы `A` и `C` находятся в режиме в сети. Файлы в файловой группе filegroup B ожидают восстановления, при этом она находится в режиме вне сети.  
  
3.  Восстановление в сети файловой группы `B.`  
  
     Файлы файловой группы `B` должны быть восстановлены из копий. Администратор восстанавливает резервную копию файловой группы `B` , полученную после того, как группа `B` стала доступна только для чтения, но до выполнения частичного резервного копирования.  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup   
    WITH RECOVERY  
    ```  
  
     Теперь все файловые группы находятся в режиме «в сети».  
  
## <a name="additional-examples"></a>Дополнительные примеры  
  
-   [Пример. Поэтапное восстановление базы данных (простая модель восстановления)](../../relational-databases/backup-restore/example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [Пример. Оперативное восстановление доступного только для чтения файла (простая модель восстановления)](../../relational-databases/backup-restore/example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [Пример. Поэтапное восстановление базы данных (модель полного восстановления)](../../relational-databases/backup-restore/example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [Пример. Поэтапное восстановление только некоторых файловых групп (модель полного восстановления)](../../relational-databases/backup-restore/example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [Пример. Оперативное восстановление файла, доступного для чтения и записи (модель полного восстановления)](../../relational-databases/backup-restore/example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [Пример. Оперативное восстановление файла, доступного только для чтения (модель полного восстановления)](../../relational-databases/backup-restore/example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a>См. также:  
 [Восстановление в сети (SQL Server)](../../relational-databases/backup-restore/online-restore-sql-server.md)   
 [BACKUP (Transact-SQL)](../../t-sql/statements/backup-transact-sql.md)   
 [RESTORE (Transact-SQL)](../../t-sql/statements/restore-statements-transact-sql.md)   
 [Поэтапное восстановление (SQL Server)](../../relational-databases/backup-restore/piecemeal-restores-sql-server.md)  
  
  
