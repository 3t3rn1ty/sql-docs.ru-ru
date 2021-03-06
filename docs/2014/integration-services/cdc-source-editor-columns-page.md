---
title: Редактор источника «CDC» (страница "столбцы") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.columns.f1
ms.assetid: bcf3030e-98d8-4445-967c-33c3f8ecb4fc
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 4369ab3606310e38a4bf6927f6abfae10fdc0ffb
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48187884"
---
# <a name="cdc-source-editor-columns-page"></a>Редактор источника «CDC» (страница «Столбцы»)
  Страница **Столбцы** диалогового окна **Редактор источника CDC** используется для сопоставления выходного столбца с каждым внешним (исходным) столбцом.  
  
 Дополнительные сведения об источнике CDC см. в разделе [CDC Source](data-flow/cdc-source.md).  
  
## <a name="task-list"></a>Список задач  
 **Открытие страницы «Столбцы» редактора источника CDC**  
  
1.  В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]откройте пакет служб [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] , содержащий источник CDC.  
  
2.  На вкладке **Поток данных** дважды щелкните источник CDC.  
  
3.  В окне **Редактор источника CDC**нажмите кнопку **Столбцы**.  
  
## <a name="options"></a>Параметры  
 **Доступные внешние столбцы**  
 Список доступных внешних столбцов источника данных. В этой таблице нельзя добавлять или удалять столбцы. Выберите используемые столбцы источника. Выбранные столбцы добавляются в список **Внешний столбец** в порядке выбора.  
  
 **Внешний столбец**  
 Представление внешних (исходных) столбцов в порядке, заданном при настройке компонентов, которые обрабатывают данные из источника CDC. Чтобы изменить этот порядок, снимите флажки для выбранных столбцов в списке **Доступные внешние столбцы** , а затем выберите внешние столбцы в другом порядке. Выбранные столбцы добавляются в список **Внешний столбец** в порядке выбора.  
  
 **Выходной столбец**  
 Введите уникальное имя для каждого выходного столбца. По умолчанию используется имя выбранного внешнего (исходного) столбца, но можно выбрать любое уникальное описательное имя. Введенное имя отображается в конструкторе служб SSIS.  
  
## <a name="see-also"></a>См. также  
 [Редактор источника CDC &#40;страницы диспетчера соединений&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md)   
 [Редактор источника CDC &#40;странице вывода ошибок&#41;](../../2014/integration-services/cdc-source-editor-error-output-page.md)  
  
  
