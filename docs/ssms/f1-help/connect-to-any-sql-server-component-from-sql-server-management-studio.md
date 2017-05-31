---
title: "Подключение к любому компоненту сервера SQL Server из среды SQL Server Management Studio | Документация Майкрософт"
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
- connections [SQL Server], SQL Server Management Studio
- saving connections
- components [SQL Server], connections
- SQL Server Management Studio [SQL Server], connections
ms.assetid: 5eeb41bd-b25b-4d3b-a005-a7d9e4b5978e
caps.latest.revision: 5
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 567cb988769e738f414f1c2a37971a792f8a41ec
ms.contentlocale: ru-ru
ms.lasthandoff: 04/11/2017

---
# <a name="connect-to-any-sql-server-component-from-sql-server-management-studio"></a>Подключение к любому компоненту сервера SQL Server из среды SQL Server Management Studio
[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)] содержит функции управления всеми компонентами [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]. Используйте среду [!INCLUDE[ssManStudio](../../includes/ssmanstudio_md.md)] для соединения со следующими компонентами и службами:  
  
-   Экземпляр компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion_md.md)].  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion_md.md)].  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion_md.md)].  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion_md.md)].  
  
Хотя [!INCLUDE[ssManStudio](../../includes/ssmanstudio_md.md)] позволяет работать с запросами без предварительного установления соединения с источником данных, для большинства других задач такое соединение требуется. [!INCLUDE[ssManStudio](../../includes/ssmanstudio_md.md)] предоставляет диалоговое окно **Соединение с сервером** , в котором можно настроить свойства компонентов [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] . При запуске [!INCLUDE[ssManStudio](../../includes/ssmanstudio_md.md)] открывается диалоговое окно **Соединение с сервером** с запросом на подключение к серверу. В диалоговом окне **Соединение с сервером** запоминаются параметры, заданные во время предыдущего его использования.  
  
> [!NOTE]  
> Эту функцию можно отключить, чтобы отменить автоматическую установку соединения. Дополнительные сведения см. в разделе [Параметры запуска службы ядра СУБД](http://msdn.microsoft.com/en-us/d373298b-f6cf-458a-849d-7083ecb54ef5).  
  
## <a name="saving-connections"></a>Сохранение соединений  
Соединение с конкретными серверами можно сохранять в списке «Зарегистрированные серверы», а также в проектах, создаваемых с помощью обозревателя решений.  
  
### <a name="saving-connections-in-registered-servers"></a>Сохранение соединений в списке «Зарегистрированные серверы»  
При регистрации сервера среда [!INCLUDE[ssManStudio](../../includes/ssmanstudio_md.md)] сохраняет данные соединения к нему в списке «Зарегистрированные серверы». Для соединения с зарегистрированным сервером дважды щелкните имя сервера в списке «Зарегистрированные серверы». После этого соединение с сервером откроется в обозревателе объектов.  
  
### <a name="saving-connections-in-solution-explorer"></a>Сохранение соединений в обозревателе решений  
Обозреватель решений позволяет хранить связанные запросы, скрипты, соединения, а также другие связанные данные в проекте. Каждый проект скриптов содержит узел **Соединения**, в котором можно сохранить одно или несколько соединений. Для добавления соединения щелкните правой кнопкой мыши узел **Соединения**и выберите **Создать соединение**. Для доступа к сохраненному соединению разверните пункт **Соединения** и дважды щелкните нужное соединение. [!INCLUDE[ssManStudio](../../includes/ssmanstudio_md.md)] позволяет открыть окно запроса, связанное с заданным соединением. При сохранении скриптов они остаются связанными с конкретным соединением.  
  
## <a name="see-also"></a>См. также:  
[Использование среды SQL Server Management Studio](../../ssms/use-sql-server-management-studio.md)  
[Обозреватель объектов](../../ssms/object/object-explorer.md)  
  
