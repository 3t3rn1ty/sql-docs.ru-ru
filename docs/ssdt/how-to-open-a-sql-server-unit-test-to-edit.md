---
title: Практическое руководство. Открытие модульного теста SQL Server для изменения | Документация Майкрософт
ms.custom:
- SSDT
ms.date: 02/09/2017
ms.prod: sql
ms.technology: ssdt
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: c6af1b12-54cd-42f9-b2ef-7164f8078323
caps.latest.revision: 8
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 1c2a7dfd1d5e9bafd023d2289c801758e9670629
ms.sourcegitcommit: c8f7e9f05043ac10af8a742153e81ab81aa6a3c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2018
ms.locfileid: "39086626"
---
# <a name="how-to-open-a-sql-server-unit-test-to-edit"></a>Практическое руководство. Открытие модульного теста SQL Server для его изменения
После создания модульного теста SQL Server добавьте инструкции и условия тестов Transact**SQL с помощью** конструктора модульных тестов SQL Server\-. Тесты, создаваемые с помощью конструктора, формируют код Visual C# или Visual Basic. Код выполняется при запуске теста.  
  
Если тест соответствует требованиям, его можно запускать без изменений. Если в модульный тест требуется добавить дополнительные функции, его код можно изменить. Код находится в файле с расширением CS или VB в тестовом проекте. Дополнительные сведения см. в статье [Файлы модульного теста SQL Server](../ssdt/sql-server-unit-test-files.md). Тесты также можно настраивать путем создания новых тестовых условий. Дополнительные сведения см. в статье [Практическое руководство. Создание условий теста для конструктора модульных тестов базы данных](http://msdn.microsoft.com/library/aa833409(VS.100).aspx) (Visual Studio 2010).  
  
> [!NOTE]  
> Если для удаления метода теста вносятся изменения в файл с расширением .cs или .vb, этот метод все равно будет отображаться в **конструкторе модульных тестов SQL Server**. Это происходит потому, что метод InitializeComponent класса тестов все еще содержит переменные этого теста. Несмотря на то что тест отображается в конструкторе, выполнить его невозможно, потому что его код удален. Чтобы повторно создать метод для этого теста, измените в редакторе код Transact\-SQL, а затем сохраните CS- или VB-файл либо перепостройте тестовый проект.  
  
### <a name="to-open-the-source-code-file-of-a-sql-server-unit-test-from-solution-explorer"></a>Открытие файла с исходным кодом модульного теста SQL Server из обозревателя решений  
  
-   В **обозревателе решений** щелкните правой кнопкой мыши файл с исходным кодом, содержащий модульный тест SQL Server, и выберите команду **Просмотр кода**.  
  
    При открытии файла метод модульного теста отображается в главном окне редактора Visual Studio.  
  
### <a name="to-open-the-source-code-file-of-a-sql-server-unit-test-from-the-test-view-window-visual-studio-2010"></a>Открытие файла с исходным кодом модульного теста SQL Server из окна представления теста (Visual Studio 2010)  
  
1.  Запустите модульный тест. Дополнительные сведения см. в разделе "Выполнение модульных тестов SQL Server" в статье [Пошаговое руководство. Создание и запуск модульного теста SQL Server](../ssdt/walkthrough-creating-and-running-a-sql-server-unit-test.md).  
  
2.  В окне "Представление теста" щелкните тест правой кнопкой мыши и выберите команду **Открыть тест**.  
  
    При открытии файла метод модульного теста отображается в главном окне редактора Visual Studio.  
  
### <a name="to-open-the-source-code-file-of-a-sql-server-unit-test-from-the-test-view-window-visual-studio-2012"></a>Открытие файла с исходным кодом модульного теста SQL Server из окна представления теста (Visual Studio 2012)  
  
1.  Запустите модульный тест. Дополнительные сведения см. в разделе "Выполнение модульных тестов SQL Server" в статье [Пошаговое руководство. Создание и запуск модульного теста SQL Server](../ssdt/walkthrough-creating-and-running-a-sql-server-unit-test.md).  
  
2.  В окне «Обозреватель тестов» щелкните имя файла с исходным кодом тестирования модулей.  
  
    При открытии файла метод модульного теста отображается в главном окне редактора Visual Studio.  
  
## <a name="see-also"></a>См. также:  
[Создание и определение модульных тестов SQL Server](../ssdt/creating-and-defining-sql-server-unit-tests.md)  
[Проверка кода базы данных с помощью модульных тестов SQL Server](../ssdt/verifying-database-code-by-using-sql-server-unit-tests.md)  
  