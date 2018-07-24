---
title: Подключение к отчету или веб-канала данных (службы SSAS) | Документация Майкрософт
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
- sql12.asvs.bidtoolset.connreportdatafeed.f1
ms.assetid: e0ccfb0b-e646-4de8-b7da-f88c986c96e4
caps.latest.revision: 11
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 726007e635a41295c682ebc929e909fda8f0b0a9
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37210294"
---
# <a name="connect-to-a-report-or-data-feed-ssas"></a>Соединение с отчетом или веб-каналом данных (SSAS)
  Эта страница **мастера импорта таблиц** позволяет подключиться к потоку данных. Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.  
  
## <a name="from-a-report"></a>Из отчета  
 **Понятное имя соединения**  
 Введите понятное имя для соединения с потоком данных.  
  
 **Путь отчета**  
 Перечисляет URL-адреса для отчета служб SQL Server Reporting Services, который формирует каналы данных. Нажмите кнопку **Обзор** , чтобы указать URL-адрес для отчета.  
  
 Нажмите кнопку **Просмотр отчета** , чтобы отобразить отчет.  
  
 **Обзор**  
 Перейдите в расположение, где находится отчет.  
  
 **Дополнительно**  
 Задайте дополнительные свойства соединения в диалоговом окне **Задание дополнительных свойств** .  
  
 **Проверка соединения**  
 Установите соединение с источником данных с использованием текущих параметров. Появится сообщение об успешном или неуспешном соединении.  
  
## <a name="from-an-azure-datamarket-dataset"></a>Из набора данных Azure DataMarket  
 **Понятное имя соединения**  
 Введите понятное имя для соединения с потоком данных.  
  
 **URL-адрес веб-канала данных**  
 Укажите полный путь к сервисному документу Atom (ATOMSVC, ATOM), URL-адрес для единичного потока данных или нажмите кнопку **Обзор** , чтобы выбрать сервисный документ Atom.  
  
 **Обзор**  
 Перейдите в расположение, где находится отчет.  
  
 Нажмите кнопку **Просмотр доступных наборов Azure DataMarket** для отображения доступных наборов.  
  
 **Ключ учетной записи**  
 Укажите ключ учетной записи для доступа к подпискам набора данных Windows Azure Marketplace.  
  
 **Найти**  
 Найдите ключ учетной записи, связанный с учетной записью Windows Live.  
  
 **Сохранить мой ключ учетной записи**  
 Сохраняет ключ учетной записи (зашифрованный) с подключением к данным.  
  
 **Дополнительно**  
 Задайте дополнительные свойства соединения в диалоговом окне **Задание дополнительных свойств** .  
  
 **Проверка соединения**  
 Установите соединение с источником данных с использованием текущих параметров. Появится сообщение об успешном или неуспешном соединении.  
  
## <a name="from-other-feeds"></a>Из других потоков  
 **Понятное имя соединения**  
 Введите понятное имя для соединения с потоком данных.  
  
 **URL-адрес веб-канала данных**  
 Укажите полный путь к сервисному документу Atom (ATOMSVC, ATOM), URL-адрес для единичного потока данных или нажмите кнопку **Обзор** , чтобы выбрать сервисный документ Atom.  
  
 Нажмите **Включить все столбцы потока** , чтобы указать, следует ли импортировать все столбцы потока данных.  
  
 **Обзор**  
 Перейдите в расположение, в котором доступен поток данных.  
  
 **Дополнительно**  
 Задайте дополнительные свойства соединения в диалоговом окне **Задание дополнительных свойств** .  
  
 **Проверка соединения**  
 Установите соединение с источником данных с использованием текущих параметров. Появится сообщение об успешном или неуспешном соединении.  
  
  