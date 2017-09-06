---
title: "Подключения к базе данных Azure SQL (MySQLToSQL) | Документы Microsoft"
ms.prod: sql-non-specified
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 81623d27-25af-444f-9779-1edb8c6fb470
caps.latest.revision: 8
author: sabotta
ms.author: carlasab
manager: lonnyb
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 98888517c8f092b5d014be0bf2c0112f1afa1629
ms.contentlocale: ru-ru
ms.lasthandoff: 08/02/2017

---
# <a name="connect-to-azure-sql-db-mysqltosql"></a>Подключения к базе данных Azure SQL (MySQLToSQL)
Подключения в SQL Azure-диалоговое окно можно используйте для подключения к базе данных SQL Azure, которые требуется перенести.  
  
Чтобы открыть это диалоговое окно на **файл** последовательно выберите пункты **подключение к SQL Azure**. Если ранее вы подключились, команда является **повторно подключиться к SQL Azure.**  
  
## <a name="options"></a>Параметры  
**Имя сервера**  
  
Выберите или введите имя сервера для подключения к SQL Azure.  
  
**База данных**  
  
Выберите, введите или **Обзор** имя базы данных.  
  
> [!IMPORTANT]  
> SSMA для MySQL не поддерживает подключение к базе данных master в SQL Azure.  
  
**Имя пользователя**  
  
Введите имя пользователя, который будет использоваться SSMA для подключения к базе данных SQL Azure  
  
**Пароль**  
  
Введите пароль для имени пользователя.  
  
**Шифрование**  
  
SSMA рекомендует зашифрованное соединение с SQL Azure.  
  
## <a name="create-azure-database"></a>Создание базы данных SQL Azure  
Если нет никаких баз данных в учетной записи SQL Azure, можно создать очень первой базы данных.  
  
Чтобы создать новую базу данных в первый раз, выполните следующие действия  
  
1.  Нажмите кнопку обзора, который присутствует в окне подключения к SQL Azure-диалоговое окно  
  
2.  Если нет никаких баз данных, отображаются следующие два элемента меню.  
  
    1.  **(не найдены базы данных)**  которого отключено и серым все время  
  
    2.  **Создать новую базу данных** включен только в том случае, если нет никаких баз данных в учетной записи SQL Azure. При выборе этого пункта меню, диалоговое окно создания базы данных Azure отсутствует имя базы данных и размером.  
  
3.  Во время создания базы данных следующие два параметра, назначается в качестве входных данных:  
  
    1.  **Имя базы данных:** введите имя базы данных.  
  
    2.  **Размер базы данных:** выбрать размер базы данных, который необходимо создать в учетной записи SQL Azure.  
  
