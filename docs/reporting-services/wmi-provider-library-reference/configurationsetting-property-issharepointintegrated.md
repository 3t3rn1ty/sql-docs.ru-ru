---
title: Свойство IsSharePointIntegrated (WMI) | Документы Майкрософт
ms.date: 03/01/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.technology: wmi-provider-library-reference
ms.topic: conceptual
helpviewer_keywords:
- IsSharePointIntegrated property
ms.assetid: c548fed8-5e04-4faf-8b10-b37c86178056
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 431d11c50aef27f84cb7595a8716b6f7387b0f83
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2018
ms.locfileid: "47836993"
---
# <a name="configurationsetting-property---issharepointintegrated"></a>Свойство ConfigurationSetting — IsSharePointIntegrated
  Указывает, находится ли сервер отчетов в режиме интеграции с SharePoint. Начиная с [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], это свойство всегда возвращает значение **False** , поскольку в режиме интеграции с SharePoint экземпляры служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] являются совместно используемыми службами SharePoint, которые не управляются поставщиками WMI.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Public Dim IsSharePointIntegrated As Boolean  
```  
  
```csharp  
public Boolean IsSharePointIntegrated;  
```  
  
## <a name="property-values"></a>Значения свойств  
 Объект **Boolean** , который показывает, работает ли сервер отчетов в режиме интеграции с SharePoint.  
  
## <a name="example-code"></a>Пример кода  
 [Класс MSReportServer_ConfigurationSetting](../../reporting-services/wmi-provider-library-reference/msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]  
  
## <a name="see-also"></a>См. также:  
 [Элементы MSReportServer_ConfigurationSetting](../../reporting-services/wmi-provider-library-reference/msreportserver-configurationsetting-members.md)  
  
  
