---
title: "MSSQLSERVER_17204 | Документация Майкрософт"
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords:
- 17204 (Database Engine error)
ms.assetid: 40db66f9-dd5e-478c-891e-a06d363a2552
caps.latest.revision: 14
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 282af6b3e7c620f4937baf811b5fb300edf9e8f7
ms.contentlocale: ru-ru
ms.lasthandoff: 04/11/2017

---
# <a name="mssqlserver17204"></a>MSSQLSERVER_17204
  
## <a name="details"></a>Сведения  
  
|||  
|-|-|  
|Название продукта|SQL Server|  
|Идентификатор события|17204|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|DBLKIO_DEVOPENFAILED|  
|Текст сообщения|%ls: Не удалось открыть файл %ls для номера файла %d.  Ошибка операционной системы: %ls.|  
  
## <a name="explanation"></a>Объяснение  
Программе SQL Server не удалось открыть указанный файл из-за указанной ошибки.  
  
## <a name="user-action"></a>Действие пользователя  
Определите причину, исправьте ошибку операционной системы, затем еще раз попытайтесь выполнить операцию.  
  
