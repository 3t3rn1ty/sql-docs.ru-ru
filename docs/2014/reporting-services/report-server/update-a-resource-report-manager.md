---
title: Обновление ресурса (диспетчер отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- updating resources
- resources [Reporting Services], updating
ms.assetid: d21f7493-bcf7-4e9e-9886-55ebdc1f1037
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 5482a935a5357d4557a6ffd202feac6be07900e9
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48130364"
---
# <a name="update-a-resource-report-manager"></a>обновить ресурс (диспетчер отчетов)
  Ресурс можно обновить, заменив его более новой версией. Ресурсы представляют собой хранящиеся на сервере отчетов элементы, по содержимому аналогичные переданным файлам. Можно заменить существующий ресурс, импортировав в существующий ресурс обновленное или совершенно другое содержимое файла. Обновление ресурса позволяет заменить только содержимое ресурса, сохраняя его существующие свойства и настройки безопасности.  
  
### <a name="to-update-a-resource"></a>Обновление ресурса  
  
1.  Запустите [диспетчер отчетов (службы SSRS в собственном режиме)](../report-manager-ssrs-native-mode.md).  
  
2.  В диспетчере отчетов перейдите к ресурсу, который нужно обновить, или найдите его.  
  
3.  Щелкните ресурс, чтобы открыть его на странице **Вид** .  
  
4.  Нажмите кнопку **Свойства** , чтобы открыть страницу свойств **Общие** .  
  
5.  Нажмите кнопку **Заменить** , чтобы открыть страницу **Импорт ресурса** .  
  
6.  Нажмите кнопку **Обзор**.  
  
7.  Выберите файл, которым нужно заменить содержимое текущего ресурса. Можно использовать обновленную версию файла или указать файл, имеющий другое имя или тип.  
  
8.  Нажмите кнопку **ОК** , чтобы передать файл ресурса, закройте страницу **Импорт ресурса** и сохраните произведенные изменения на сервере отчетов.  
  
 Если обновляемый ресурс содержит изображение, используемое в отчете, необходимо обновить отчет, чтобы изображение в нем обновилось.  
  
## <a name="see-also"></a>См. также  
 [Содержимое страницы &#40;диспетчера отчетов&#41;](../contents-page-report-manager.md)   
 [Страница "Передача файла" (диспетчер отчетов)](../upload-file-page-report-manager.md)   
 [Передача файлов в папку](upload-files-to-a-folder.md)   
 [Справка F1 диспетчера отчетов](../report-manager-f1-help.md)  
  
  
