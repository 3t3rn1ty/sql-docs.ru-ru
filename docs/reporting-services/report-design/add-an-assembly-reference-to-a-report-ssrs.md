---
title: Добавление в отчет ссылку на сборку (службы SSRS) | Документы Майкрософт
ms.date: 03/14/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.technology: report-design
ms.topic: conceptual
helpviewer_keywords:
- code [Reporting Services]
- custom assemblies [Reporting Services], referencing
- custom code [Reporting Services]
- adding assembly references
- assemblies [Reporting Services], references
ms.assetid: 0a03939e-48ce-4c30-b227-98533f2e0ccb
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 91e4536925b37277f81ccafe41b6a30c6dc52504
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2018
ms.locfileid: "47657460"
---
# <a name="add-an-assembly-reference-to-a-report-ssrs"></a>Добавление в отчет ссылку на сборку (службы SSRS)
  При внедрении пользовательского кода, содержащего ссылки на классы платформы [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , не входящие в <xref:System.Math> или <xref:System.Convert>, необходимо предоставить в отчете ссылку на сборку, чтобы обработчик отчетов мог разрешать имена этих классов. Дополнительные сведения см. в разделе [Добавление кода в отчет (службы SSRS)](../../reporting-services/report-design/add-code-to-a-report-ssrs.md).  
  
### <a name="to-add-an-assembly-reference-to-a-report"></a>Добавление в отчет ссылки на сборку  
  
1.  В режиме **конструктора** щелкните правой кнопкой мыши в области конструктора за границей отчета и выберите команду **Свойства отчета**.  
  
2.  Нажмите кнопку **Ссылки**.  
  
3.  В окне **Добавить или удалить сборки**нажмите кнопку **Добавить** и затем нажмите кнопку с многоточием, чтобы найти сборку.  
  
4.  В окне **Добавить или удалить классы**нажмите кнопку **Добавить** , а затем введите имя класса и предоставьте имя экземпляра для использования в отчете.  
  
    > [!NOTE]  
    >  Укажите имя класса и имя экземпляра только для элементов, зависимых от экземпляров. Не задавайте статические элементы в списке **Классы** . Дополнительные сведения см. в разделе [Пользовательский код и ссылки на сборки в выражениях в конструкторе отчетов (службы SSRS)](../../reporting-services/report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a>См. также:  
 [Использование пользовательских сборок с отчетами](../../reporting-services/custom-assemblies/using-custom-assemblies-with-reports.md)   
 [Диалоговое окно "Свойства отчета" — "Ссылки"](http://msdn.microsoft.com/library/4639d368-9918-4bb1-9953-7a724ca78dea)  
  
  
