---
title: "Об использовании инвентаризации | Документы Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- usage counts [ODBC]
- file usage counts [ODBC]
- installing ODBC components [ODBC], usage counts
- subkeys [ODBC], usage counts
ms.assetid: 0678aee9-8256-463c-89dd-77b1a0dfdd60
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 0f9db5a35b8b0bb3dc437dd203267c6f53825e22
ms.contentlocale: ru-ru
ms.lasthandoff: 09/09/2017

---
# <a name="usage-counting"></a>Об использовании инвентаризации
> [!NOTE]  
>  Начиная с Windows XP и Windows Server 2003, ODBC включается в операционной системе Windows. ODBC следует устанавливать только явно на более ранних версиях Windows.  
  
 Два типа счетчики использования сохраняются в реестре для каждого компонента: учет использования компонента и один или несколько счетчиков использования дополнительного файла. Счетчик использования компонента помогает установщик DLL Ведение записей реестра. Он сохраняется в значении UsageCount базовый ODBC, драйверов и переводчик подразделов. Формат значения UsageCount и Дополнительные сведения об этих подразделов, в разделе [записи реестра для компонентов ODBC](../../../odbc/reference/install/registry-entries-for-odbc-components.md).  
  
 При первой установке компонента установщик DLL создает подраздел для него и задает значение UsageCount в этом разделе 1. При повторной установки компонента установщика DLL увеличивает счетчик использования. При удалении компонента установщика DLL уменьшает использование счетчик. Если счетчик использования становится равным 0, установщик DLL удаляет подраздел для компонента.  
  
> [!CAUTION]  
>  Приложения не должны физически удалить файлы диспетчера драйверов, когда счетчик использования компонента и счетчик использования файла достигнет нуля.  
  
 Использование файла, если файл необходимо фактически скопировать или удалить как можно определить при помощи счетчиков отличие от увеличения и уменьшения счетчик использования. Это важно, так как компонентов ODBC и файлы компонентов ODBC, являются общими и могут быть установлены или удалены различных приложений. Приложение можно удалить файлы драйверов и преобразователя, если счетчик использования компонента и счетчик использования файла достигнет нуля. Диспетчер драйверов файлы должны храниться в секрете, тем не менее, удален по достижении счетчик использования компонента и счетчик использования файла нулю, так как эти файлы могут использоваться другими приложениями, которые не имеют увеличивается счетчик использования файла.  
  
> [!NOTE]  
>  Счетчики использования файла являются необязательными в Microsoft® WindowsNT® или Windows 2000.  
  
 Счетчики использования файла поддерживаются программой установки, после вызова **SQLInstallDriverManager**, **SQLInstallDriverEx**, **SQLInstallTranslatorEx**, **SQLRemoveDriverManager**, **SQLRemoveDriver**, или **SQLRemoveTranslator**.  
  
 При первой установке компонента программы установки или установщика DLL создает значение в следующем разделе для каждого файла в этом компоненте, который еще не в системе:  
  
> [!NOTE]  
>  HKEY_LOCAL_MACHINE  
>   
>  ПРОГРАММНОЕ ОБЕСПЕЧЕНИЕ  
>   
>  Microsoft  
>   
>  Windows  
>   
>  CurrentVersion  
>   
>  SharedDlls  
  
 Он задает данные для этих значений 1 и копирует файл в системе. При повторной установки компонента программы установки или установщика DLL увеличивает счетчики использования. При удалении компонента установки программы или установщика уменьшает DLL использование счетчиков. Если любой загруженность становится равным 0, программа установки или установщика DLL удаляет значение для файла и удаляет файл, если компонент драйвера или устройством преобразования. Диспетчер драйверов файлы не должны удаляться.  
  
 В следующей таблице показан формат значения числа использования файла.  
  
|Имя|Тип данных|data|  
|----------|---------------|----------|  
|*Полный путь*|REG_DWORD|*count*|  
  
 Например предположим, что драйвер для Informix использует файлы Infrmx32.dll и Infrmx32.hlp и Предположим, что этот драйвер был установлен дважды. Значения в подразделе SharedDlls для драйвера Informix будет выглядеть следующим образом:  
  
```  
C:\WINDOWS\SYSTEM32\INFRMX32.DLL : REG_DWORD : 0x2  
C:\WINDOWS\SYSTEM32\INFRMX32.HLP : REG_DWORD : 0x2  
```