---
title: "Удаление объектов | Документация Майкрософт"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.swb.deleteobjects.f1
helpviewer_keywords:
- Delete Objects dialog box
ms.assetid: 49541441-179c-40d3-ba0c-01bcae545984
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 053e53c609786f9ba9193c5dd2f70c58ec00eba3
ms.contentlocale: ru-ru
ms.lasthandoff: 04/11/2017

---
# <a name="delete-objects"></a>Удаление объектов
Используйте данное диалоговое окно для удаления базы данных или объекта базы данных.  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
**Объект для удаления**  
Отображаются имена, типы, владельцы и состояние объектов, которые будут удалены, а также любые сообщения об ошибках во время выполнения.  
  
> [!NOTE]  
> Команда **Удалить** , применяемая к базе данных, соответствует команде DROP DATABASE в [!INCLUDE[tsql](../../includes/tsql_md.md)].  
  
**Показать зависимости**  
Нажмите, чтобы отобразить объекты, зависимые от выбранного объекта, и объекты, от которых зависит выбранный объект (восходящая или нисходящая зависимость). Данные, отображаемые в диалоговом окне **Показать зависимости** , доступны только для чтения.  
  
> [!NOTE]  
> Не для всех типов объектов базы данных отображается кнопка **Показать зависимости** . Чтобы просмотреть зависимости при отсутствии кнопки **Показать зависимости** , щелкните правой кнопкой мыши объект в обозревателе объектов и выберите в контекстном меню пункт **Просмотреть зависимости**.  
  
**Удалить журналы резервного копирования и восстановления баз данных**  
Данный флажок отображается только после удаления базы данных и вызывает удаление журнала резервного копирования и восстановления объектной базы данных из базы данных **msdb** .  
  
**Закрыть существующие соединения**  
Флажок отображается только после удаления базы данных и используется для закрытия соединения с базой данных.  
  
