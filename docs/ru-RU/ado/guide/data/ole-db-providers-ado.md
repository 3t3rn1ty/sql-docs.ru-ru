---
title: Поставщики OLE DB (ADO) | Документы Microsoft
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: ado
ms.technology:
- drivers
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- OLE DB providers [ADO]
- ADO, OLE DB providers
ms.assetid: 6e0488c3-934d-4976-99dc-65c580dc7a3c
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 32b276f97950405caabd5e5d30d45cd2b3fba297
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ole-db-providers-ado"></a>Поставщики OLE DB (ADO)
OLE DB определяет набор COM-интерфейсы для предоставления приложениям стандартизированный доступ к данным, которые хранятся в различных источниках. Такой подход позволяет источнику данных для совместного использования данных через интерфейсы, поддерживающие объем функциональность СУБД, подходящие для источника данных. Разработчиками предусмотрено высокой производительности архитектуры OLE DB основан на его использование модель гибкую, основанных на компонентах служб. Вместо того, назначенные количество промежуточных слоев между приложением и данных, OLE DB требуется только в том случае, как многие компоненты, так как необходимые для выполнения конкретной задачи.  
  
 Например предположим, что пользователь хочет выполнить запрос. Рассмотрим следующие сценарии.  
  
-   Данные хранятся в реляционной базе данных, для которого в настоящее время существует драйвера ODBC, но нет собственного поставщика OLE DB: приложение использует ADO для обращайтесь к поставщику OLE DB для ODBC, который затем загружает соответствующий драйвер ODBC. Драйвер передает инструкции SQL в СУБД, в которую извлекаются данные.  
  
-   Данные находятся в Microsoft SQL Server, для которых нет собственного поставщика OLE DB: приложение использует ADO для обращайтесь непосредственно к поставщику OLE DB для Microsoft SQL Server. Посредники, не являются обязательными.  
  
-   Данные находятся в Microsoft Exchange Server, для которой имеется поставщик OLE DB, но не предоставляет механизм для обработки запросов SQL: приложения, использующего ADO для обращайтесь к поставщику OLE DB для Microsoft Exchange и вызывает обработчик запросов OLE DB компонент для обработки запросов.  
  
-   Они находятся в файловой системе NTFS Майкрософт в виде документов: доступ к данным с помощью собственного поставщика OLE DB по службе индексирования, который индексирует содержимое и свойства документов в файловой системе для включения эффективный содержимого выполняет поиск.  
  
 В предыдущих примерах приложения могут запрашивать данные. Потребности пользователей в выполняются с минимальным количеством компонентов. В каждом случае дополнительные компоненты, используются только в том случае, если требуется, и вызываются только необходимые компоненты. Это-загрузку по требованию для повторного использования и совместного использования компонентов значительно вносит свой вклад высокой производительности при использовании OLE DB.  
  
 Поставщики делятся на две категории: те, предоставление данных, так и предоставления услуг. Поставщик данных владеют собственными данными и предоставляет доступ к нему в табличной форме в приложение. Поставщик услуг инкапсулирует службы посредством создания и использования данных, расширения возможностей в приложениях ADO. Поставщик услуг можно также детализировать как компонент службы, который необходимо работать совместно с других поставщиков служб или компонентов.  
  
 ADO предоставляет согласованный, высокий уровень интерфейс для различных поставщиков OLE DB.  
  
 Этот раздел содержит следующие подразделы.  
  
-   [Поставщики данных](../../../ado/guide/data/data-providers.md)  
  
-   [Поставщики служб и компоненты](../../../ado/guide/data/service-providers-and-components.md)