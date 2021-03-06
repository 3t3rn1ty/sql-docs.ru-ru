---
title: Добавление индикаторов и датчиков на панель датчиков (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.date: 03/01/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.technology: report-design
ms.topic: conceptual
ms.assetid: 4dff9b67-b483-4c51-a822-6dbe706a6840
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 1f5e493485df8346ca66da5f9125a0ff024addf6
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2018
ms.locfileid: "47743912"
---
# <a name="include-indicators-and-gauges-in-a-gauge-panel-report-builder-and-ssrs"></a>Добавление индикаторов и датчиков на панель датчиков (построитель отчетов и службы SSRS)
  Панель датчиков — это контейнер верхнего уровня, который содержит один или несколько датчиков и индикаторов. Индикаторы могут быть встроены в датчики или помещены рядом с ними на панели датчиков.  
  
 Если индикатор и датчик являются смежными на панели датчиков и показывают данные из разных полей, то может потребоваться добавить метки, чтобы было ясно, какие данные представлены датчиком и индикатором.  
  
 Параметры датчика и индикатора могут быть заданы с помощью выражений. Дополнительные сведения см. в разделе [Выражения (построитель отчетов и службы SSRS)](../../reporting-services/report-design/expressions-report-builder-and-ssrs.md).  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-embed-an-indicator-in-a-gauge"></a>Внедрение индикатора в датчик  
  
1.  Откройте существующий отчет или создайте новый отчет, содержащий таблицу и матрицу с данными, которые необходимо отобразить.   
  
2.  Вставьте столбец в таблицу или матрицу. Дополнительные сведения см. в разделе [Вставка или удаление столбца (построитель отчетов и службы SSRS)](../../reporting-services/report-design/insert-or-delete-a-column-report-builder-and-ssrs.md).  
  
3.  На вкладке **Вставить** в группе **Области данных** нажмите **Датчик**, затем щелкните ячейку в новом столбце. Откроется диалоговое окно **Выбор типа датчика** .  
  
4.  Нажмите **Радиальный**. Будет выбран первый радиальный датчик.  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
6.  Щелкните датчик. Откроется панель **Данные датчика** .  
  
7.  В области **Значения** в раскрывающемся списке **(Не указано)** выберите поле, значения которого необходимо отобразить в датчике. Можно также перетащить нужное поле из набора данных отчета.  
  
8.  Правой кнопкой мыши щелкните датчик, **Добавить индикатор**, а затем **Дочерний**. Откроется диалоговое окно **Выбор стиля индикатора** .  
  
9. В диалоговом окне **Выбор стиля индикатора** в левой панели выберите тип нужного индикатора, а затем выберите набор индикаторов.  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
11. Щелкните индикатор. Откроется панель **Данные датчика** .  
  
12. В области **Значения** в раскрывающемся списке **(Не указано)** выберите поле, значения которого необходимо отобразить в качестве индикатора. Можно также перетащить нужное поле из набора данных отчета.  
  
     Это поле может быть таким же или иным по сравнению с тем, которое используется в датчике.  
  
13. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-show-an-indicator-and-gauge-side-by-side"></a>Отображение индикатора и датчика рядом друг с другом  
  
1.  Откройте существующий отчет или создайте новый отчет, содержащий таблицу и матрицу с данными, которые необходимо отобразить.  
  
2.  Вставьте столбец в таблицу или матрицу. Дополнительные сведения см. в разделе [Вставка или удаление столбца (построитель отчетов и службы SSRS)](../../reporting-services/report-design/insert-or-delete-a-column-report-builder-and-ssrs.md).  
  
3.  На вкладке **Вставить** в группе **Области данных** нажмите **Датчик**, затем щелкните ячейку во вставленном столбце. Откроется диалоговое окно **Выбор типа датчика** .  
  
4.  Нажмите **Радиальный**. Будет выбран первый радиальный датчик.  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
6.  Щелкните датчик. Откроется панель **Данные датчика** .  
  
7.  В области **Значения** в раскрывающемся списке **(Не указано)** выберите поле, значения которого необходимо отобразить в датчике. Можно также перетащить нужное поле из набора данных отчета.  
  
8.  Правой кнопкой мыши щелкните датчик, **Добавить индикатор**, затем **Смежный**. Откроется диалоговое окно **Выбор стиля индикатора** .  
  
9. В диалоговом окне **Выбор стиля индикатора** в левой панели выберите тип нужного индикатора, а затем выберите набор индикаторов.  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
11. Щелкните индикатор. Откроется панель **Данные датчика** .  
  
12. В области **Значения** в раскрывающемся списке **(Не указано)** выберите поле, значения которого необходимо отобразить в качестве индикатора. Можно также перетащить нужное поле из набора данных отчета.  
  
     Это поле может быть таким же или иным по сравнению с тем, которое используется в датчике.  
  
13. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
14. Щелкните правой кнопкой мыши панель датчиков и выберите **Добавить метку**. Метка добавится на панель датчиков. Повторите это действие еще раз.  
  
     На панели датчиков появятся две метки.  
  
15. Перетащите каждую метку в местоположение рядом с датчиком или индикатором.  
  
16. Щелкните правой кнопкой метку рядом с датчиком, выберите пункт **Свойства метки**и введите требуемый текст в поле **Текст** .  
  
17. Щелкните правой кнопкой метку рядом с индикатором, выберите пункт **Свойства метки**и введите требуемый текст в поле **Текст** .  
  
18. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a>См. также:  
 [Индикаторы (построитель отчетов и службы SSRS)](../../reporting-services/report-design/indicators-report-builder-and-ssrs.md)  
  
  
