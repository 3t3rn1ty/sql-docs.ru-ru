---
title: "Интерактивные возможности - различных модулей подготовки отчетов | Документы Microsoft"
ms.custom: 
ms.date: 03/07/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0bd1c4c-e8b5-467f-b5a1-541f19c7e3e2
caps.latest.revision: 7
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: 9a422c1619ae284ec49643465bd8b84efda1910b
ms.contentlocale: ru-ru
ms.lasthandoff: 06/22/2017

---
# <a name="interactive-functionality---different-report-rendering-extensions"></a>Интерактивные возможности - различных модулей подготовки отчетов
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] предоставляет функции для взаимодействия с отчетом с разбиением на страницы во время выполнения. Не все выходные форматы отчета поддерживают полный диапазон интерактивных возможностей. Чтобы понять, как интерактивные возможности работают с конкретными выходными форматами, воспользуйтесь приведенной ниже таблицей.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="interactive-features-in-different-output-formats"></a>Интерактивные возможности в различных выходных форматах  
 Отчеты с разбиением на страницы, подготовленные в выходных форматах XML, CSV или в виде изображений, не поддерживают интерактивные возможности.  
  
 Отчеты, просматриваемые на веб-портале [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , в веб-частях SharePoint или браузере, отображаются в формате HTML. Форматы HTML и Windows Forms представляют собой единственные выходные форматы отчета, которые полностью поддерживают все интерактивные средства. Альтернативные форматы HTML (например, MHTML) поддерживают большинство интерактивных возможностей. Если для формата MHTML существуют какие-либо исключения, они указаны в следующей таблице.  
  
### <a name="document-maps"></a>Схемы документа  
  
|Параметр экспорта|Данные поддержки|  
|-------------------|-------------------------|  
|Просмотр/средство просмотра отчетов, HTML|Интерактивная схема документа представляет панель переходов, которая содержит набор иерархических ссылок, с помощью которых можно перемещаться к различным разделам отчета.|  
|PDF|Модули подготовки отчетов в формате PDF обращаются со схемой документа как с панелью закладок. Все элементы схемы документа размещаются один за другим на панели. Включает иерархию ссылок. Если указан диапазон страниц, то в иерархии существуют только те закладки, которые представлены при выводе.|  
|Excel|Программа Excel подготавливает к просмотру схему документа как первый лист в книге. Включает иерархию ссылок. Щелкнув ссылку в схеме документа, можно открыть соответствующую целевую ячейку в относящемся к ней листе.|  
|Word|Программа Word подготавливает к просмотру схему документа как метки оглавления документа.|  
|Другие (например, TIFF, XML и CSV)|Отсутствует в MHTML, XML, CSV и изображениях.|  
  
### <a name="drillthrough-links-to-other-reports"></a>Ссылки детализации к другим отчетам  
  
|Параметр экспорта|Данные поддержки|  
|-------------------|-------------------------|  
|Просмотр/средство просмотра отчетов, HTML|Пользователи щелкают в отчете значения данных для просмотра взаимосвязанных данных в другом отчете.|  
|PDF|В документе PDF ссылки детализации не доступны. Рассмотрите возможность использования гиперссылок для отчетов в формате PDF, ссылающихся на другие страницы.|  
|Excel|Ссылки детализации могут использоваться в формате Excel.<br /><br /> Ссылка становится гиперссылкой на отчет, на который указывает ссылка детализации. Пользователь щелкает ссылку, и в окне браузера открывается отчет.|  
|Word|Ссылки детализации подготовлены к просмотру в Word.<br /><br /> Ссылка становится гиперссылкой на отчет, на который указывает ссылка детализации. Пользователь щелкает ссылку, и в окне браузера открывается отчет.|  
|Другое|Недоступна в XML, CSV и изображениях.|  
  
### <a name="toggle-items-within-a-report"></a>Переключаемые элементы в пределах отчета  
  
|Параметр экспорта|Данные поддержки|  
|-------------------|-------------------------|  
|Просмотр/средство просмотра отчетов, HTML|Пользователи щелкают значки «Развернуть» или «Свернуть» для отображения или сворачивания разделов отчета.|  
|PDF|Сервер отчетов экспортирует в формат PDF текущее состояние видимости отчета. Интерактивное переключение не поддерживается|  
|Excel|Ссылки и элементы углубленной детализации, которые могут быть переключены, представляются в Excel как свертываемые структуры. В отчете, экспортированном в формате Excel, разделы можно разворачивать и сворачивать. Дополнительные сведения о налагаемых Excel ограничениях см. в разделе [Экспорт в Microsoft Excel (построитель отчетов и службы SSRS)](../../reporting-services/report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).|  
|Word|Сервер отчетов экспортирует в формат PDF текущее состояние видимости отчета. Интерактивное переключение не поддерживается|  
|Другое|Недоступно в форматах MHTML, XML или CSV. При экспорте в формат изображения сервер отчетов учитывает параметры отображения или скрытия, относящиеся к экспорту отчета в формат PDF. Интерактивное переключение не поддерживается.|  
  
### <a name="interactive-sorting"></a>Интерактивная сортировка  
  
|Параметр экспорта|Данные поддержки|  
|-------------------|-------------------------|  
|Просмотр/средство просмотра отчетов, HTML|В табличных отчетах пользователи щелкают стрелки сортировки в заголовке столбца для изменения порядка сортировки данных.|  
|PDF|Недоступна в формате PDF.|  
|Excel|Недоступна в формате Excel.|  
|Word|Недоступно в Word.|  
|Другое|Отсутствует в MHTML, XML, CSV и изображениях.|  
  
### <a name="hyperlinks-to-external-web-content-or-images"></a>Гиперссылки, указывающие на внешнее веб-содержимое или изображения  
  
|Параметр экспорта|Данные поддержки|  
|-------------------|-------------------------|  
|Просмотр/средство просмотра отчетов, HTML|Пользователи щелкают ссылку, чтобы открыть внешние веб-страницы в новом окне браузера.|  
|PDF|Гиперссылки выводятся модулем подготовки отчетов в формате PDF. Когда пользователь щелкает гиперссылку, связанные с ней страницы открываются в браузере.|  
|Excel|Гиперссылки выводятся в формате Excel.|  
|Word|Гиперссылки подготовлены к просмотру в Word.|  
|Другое|Гиперссылки недоступны в форматах MHTML, XML, CSV или в формате изображения.<br /><br /> Для формата MHTML и формата изображения внешние изображения выводятся в виде статических картинок.|  
  
### <a name="bookmark-or-anchor"></a>Закладка или привязка  
  
|Параметр экспорта|Данные поддержки|  
|-------------------|-------------------------|  
|Просмотр/средство просмотра отчетов, HTML|Пользователи щелкают ссылку для перехода к другому разделу того же отчета.|  
|PDF|Недоступна в формате PDF.|  
|Excel|Закладки выводятся в формате Excel.<br /><br /> Закладка становится гиперссылкой на имя элемента отчета.|  
|Word|Закладки представляются средствами программы Word.<br /><br /> Закладка становится гиперссылкой, указывающей на обозначенный закладкой элемент отчета. При экспорте отчета преобразуются только 40 символов имени закладки или привязки, что может стать причиной появления повторяющихся имен закладок или привязок. Пробелы преобразуются в символы подчеркивания (_).|  
|Другое|Недоступна в XML, CSV и изображениях.|  
  
### <a name="prompted-parameters-obtained-at-run-time"></a>Запрашиваемые параметры, получаемые во время выполнения  
  
|Параметр экспорта|Данные поддержки|  
|-------------------|-------------------------|  
|Просмотр/средство просмотра отчетов, HTML|Область ввода параметров появляется в верхней части отчета. Эта область является частью средства просмотра HTML-страниц, которое используется для просмотра отчетов в браузере.|  
|PDF|Сервер отчетов экспортирует отчет в формат PDF, используя значения параметров, действующих для отчета на данный момент.|  
|Excel|Сервер отчетов экспортирует отчет в формат Excel, используя значения параметров, действующих для отчета на данный момент.|  
|Word|Сервер отчетов экспортирует отчет в формат Word, используя значения параметров, действующих для отчета на данный момент.|  
|Другое|Сервер отчетов экспортирует отчет в другие форматы, используя значения параметров, действующих для отчета на данный момент.|  
  
### <a name="filters-applied-at-run-time"></a>Фильтры, применяемые во время выполнения  
  
|Параметр экспорта|Данные поддержки|  
|-------------------|-------------------------|  
|Просмотр/средство просмотра отчетов, HTML|Во время выполнения пользователю отображаются отфильтрованные данные.|  
|PDF|Сервер отчетов экспортирует отчет в формат PDF, используя в данном отчете отфильтрованные данные.|  
|Excel|Сервер отчетов экспортирует отчет в формат Excel, используя в данном отчете отфильтрованные данные.|  
|Word|Сервер отчетов экспортирует отчет в формат Word, используя в данном отчете отфильтрованные данные.|  
|Другое|Сервер отчетов экспортирует отчет в другие форматы, используя в данном отчете отфильтрованные данные.|  
  
## <a name="see-also"></a>См. также  
 [Экспорт отчетов (построитель отчетов и службы SSRS)](../../reporting-services/report-builder/export-reports-report-builder-and-ssrs.md)   
 [Интерактивная сортировка, схемы документов и ссылки (построитель отчетов и службы SSRS)](../../reporting-services/report-design/interactive-sort-document-maps-and-links-report-builder-and-ssrs.md)   
    
 [Таблицы, матрицы и списки (построитель отчетов и службы SSRS)](../../reporting-services/report-design/tables-matrices-and-lists-report-builder-and-ssrs.md)   
 [Диаграммы (построитель отчетов и службы SSRS)](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)  
  
  
