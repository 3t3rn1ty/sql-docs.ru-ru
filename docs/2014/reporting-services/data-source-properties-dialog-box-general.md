---
title: Диалоговое окно свойств «Общие» источника данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.datasourceproperties.general.f1
- "10120"
ms.assetid: 44b5edd3-5c11-4d3d-91b8-5871aa0572ed
caps.latest.revision: 35
author: maggiesmsft
ms.author: douglasl
manager: craigg
ms.openlocfilehash: d5e5b2f1c1792a2fdbc6b83d94f85dd5883b8954
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37206734"
---
# <a name="data-source-properties-dialog-box-general"></a>Диалоговое окно «Свойства источника данных» — «Общие»
  Вкладка **Общие** в диалоговом окне **Источник данных** позволяет просмотреть и изменить сведения о соединении источника данных с отчетом.  
  
## <a name="options"></a>Параметры  
 **Название**  
 Введите имя источника данных. Имя источника данных должно быть уникальным в пределах отчета. По умолчанию источнику данных присваивается стандартное имя, например ИсточникДанных1 или ИсточникДанных2.  
  
 **Внедренное соединение**  
 Выберите этот параметр, если общий источник данных не нужен.  
  
 **Тип**  
 Выберите модуль обработки данных. В списке перечислены все зарегистрированные модули.  
  
 **Строка соединения**  
 Введите строку соединения для источника данных. Чтобы построить строку соединения с помощью диалогового окна **Свойства соединения** , нажмите кнопку **Изменить** . Чтобы изменить выражение, нажмите кнопку **Выражение** (*fx*).  
  
 **Использовать ссылку на источник общих данных**  
 Выберите этот параметр, чтобы задать ссылку на общий источник данных. Выберите общий источник данных из раскрывающегося списка. Чтобы изменить выбранный источник данных, нажмите кнопку **Изменить**. Если установлен флажок **Использовать ссылку на общий источник данных** , флажки **Тип** и **Строка соединения** отключены.  
  
 **Использовать одну транзакцию при обработке запросов**  
 Выберите этот параметр, чтобы указать, что все наборы данных, использующие этот источник данных, запускаются в единой транзакции базы данных. Чтобы транзакции вложенного отчета использовали тот же источник данных, задайте для этого вложенного отчета в панели **Свойства** в разделе **Прочее** для свойства **MergeTransactions** значение **True** .  
  
## <a name="see-also"></a>См. также  
 [Добавление данных в отчет &#40;построитель отчетов и службы SSRS&#41;](report-data/report-datasets-ssrs.md)   
 [Создать источник данных на внедренный или общий &#40;SSRS&#41;](../../2014/reporting-services/create-an-embedded-or-shared-data-source-ssrs.md)   
 [Подключения к данным, источники данных и строки подключения в службах Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md)   
 [Диалоговое окно "Свойства источника данных" — "Учетные данные"](../../2014/reporting-services/data-source-properties-dialog-box-credentials.md)  
  
  