---
title: "MSSQLSERVER_916 | Документация Майкрософт"
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
- 916 (Database Engine error)
ms.assetid: 73eb6581-99fe-49a5-9b42-e239d7ffe27f
caps.latest.revision: 8
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 69490614063e878043c59bce1bc7836f813eb517
ms.contentlocale: ru-ru
ms.lasthandoff: 04/11/2017

---
# <a name="mssqlserver916"></a>MSSQLSERVER_916
  
## <a name="details"></a>Сведения  
  
|||  
|-|-|  
|Название продукта|SQL Server|  
|Идентификатор события|916|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|NOTUSER|  
|Текст сообщения|Субъект сервера "%.*ls" не может получить доступ к базе данных "%.\*ls" в текущем контексте безопасности.|  
  
## <a name="explanation"></a>Объяснение  
У имени входа отсутствуют необходимые разрешения для соединения с именованной базой данных. Имена входа, которые могут использоваться для подключения к этому экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], но не имеют специальных разрешений в базе данных, получают разрешения пользователя guest. Это одна из мер безопасности, которая не позволяет пользователям одной базы данных подключаться к другим базам данных, в которых они не имеют прав доступа. Это сообщение об ошибке отображается, если у пользователя guest отсутствует разрешение CONNECT для подключения к именованной базе данных и свойство доверительных отношений не включено. Это сообщение об ошибке отображается, если у пользователя guest отсутствует разрешение CONNECT для соединения с именованной базой данных.  
  
Если разрешение CONNECT для подключения к базе данных msdb не предоставлено или отозвано, такая ошибка может произойти в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] при попытке обозревателя объектов отобразить состояние управления на основе политик для всех баз данных. Обозреватель объектов использует разрешения текущего имени для входа, чтобы получить эту информацию из базы данных msdb, что и вызывает указанную ошибку. Также отображается следующее сообщение об ошибке:  
  
Ошибка при получении данных по этому запросу. (Microsoft.SqlServer.Management.Sdk.Sfc)  
  
## <a name="user-action"></a>Действие пользователя  
  
> [!WARNING]  
> Прежде чем обойти эту меру безопасности, необходимо достичь четкого понимания того, какие пользователи проходят проверку в различных базах данных. Следующие методы могут позволить пользователям, имеющим разрешения в одной базе данных, подключаться к другим базам данных, в результате чего доступ к данным может получить злонамеренный пользователь. Если автономные базы данных включены, владельцы этих баз данных могут выполнить следующие шаги в одной базе данных, чтобы предоставить доступ к другой базе данных на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
Можно подключиться к базе данных одним из следующих способов.  
  
-   Предоставить имени входа специальный доступ к указанной базе данных. В следующем примере предоставляется разрешение для имени входа для доступа `Adventure-Works\Larry` к базе данных `msdb`.  
  
    USE msdb;  
  
    GO  
  
    GRANT CONNECT TO [Adventure-Works\Larry] ;  
  
-   Предоставить для пользователя guest разрешение CONNECT для базы данных, указанной в сообщении об ошибке. В следующем примере пользователю `CONNECT` предоставляется разрешение `msdb` для базы данных `guest`.  
  
    USE msdb;  
  
    GO  
  
    GRANT CONNECT TO guest ;  
  
-   Включите свойство TRUSTWORTHY в базе данных, применительно к которой прошел проверку пользователь.  
  
    `ALTER DATABASE AdventureWorks SET TRUSTWORTHY ON;`  
  
