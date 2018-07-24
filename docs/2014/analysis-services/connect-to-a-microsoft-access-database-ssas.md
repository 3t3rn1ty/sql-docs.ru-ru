---
title: Соединение с базой данных Microsoft Access (службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connaccessdb.f1
ms.assetid: 9fa81839-dd8b-41d3-915e-c774a707ed53
caps.latest.revision: 11
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: c97b313a5f1cfc3a9c4dfb76f7f0b58f77e59f7b
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37204464"
---
# <a name="connect-to-a-microsoft-access-database-ssas"></a>Соединение с базой данных Microsoft Access (SSAS)
  Эта страница **мастера импорта таблиц** позволяет задать параметры для соединения с базой данных Microsoft Access. Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.  
  
 Для соединения с базой данных Microsoft Access необходимо, чтобы на компьютере был установлен поставщик ACE. Дополнительные сведения см. в разделе [Поддерживаемые источники данных (табличные службы SSAS)](tabular-models/data-sources-supported-ssas-tabular.md).  
  
> [!NOTE]  
>  При выборе файла на этой странице используются учетные данные текущего пользователя. Тем не менее импорт не будет успешным, если пользователь, указанный на странице сведений об олицетворении, не имеет достаточных прав для чтения из выбранного файла.  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Понятное имя соединения**  
 Введите уникальное имя для соединения с источником данных. Это поле является обязательным.  
  
 **Имя базы данных**  
 Укажите полный путь к файлу базы данных Microsoft Access.  
  
 **Обзор**  
 Перейдите к расположению, в котором доступен файл базы данных Microsoft Access.  
  
 **Имя пользователя**  
 Укажите имя пользователя для подключения к базе данных.  
  
 **Пароль**  
 Укажите пароль для подключения к базе данных.  
  
 **Сохранить пароль**  
 Укажите, нужно ли сохранить пароль, введенный в поле **Пароль** .  
  
 **Дополнительно**  
 Задайте дополнительные свойства соединения в диалоговом окне **Задание дополнительных свойств** .  
  
 **Проверка соединения**  
 Установите соединение с источником данных с использованием текущих параметров. Появится сообщение об успешном или неуспешном соединении.  
  
  