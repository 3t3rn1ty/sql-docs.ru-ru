---
title: "PDOStatement::setFetchMode | Документы Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f132b2af-0433-4fbe-b03f-69a7d631093a
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 0dc89d9cbe9f0420fdbaab1e47a68780d80b478d
ms.contentlocale: ru-ru
ms.lasthandoff: 09/09/2017

---
# <a name="pdostatementsetfetchmode"></a>PDOStatement::setFetchMode
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Указывает режим извлечения для дескриптора PDOStatement.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
bool PDOStatement::setFetchMode( $mode );  
```  
  
#### <a name="parameters"></a>Параметры  
$*режим*: все параметры, допустимые для передачи в [PDOStatement::fetch](../../connect/php/pdostatement-fetch.md).  
  
## <a name="return-value"></a>Возвращаемое значение  
Значение true в случае успеха, в противном случае — значение false.  
  
## <a name="remarks"></a>Замечания  
Поддержка PDO была добавлена в версии 2.0 [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)].  
  
## <a name="example"></a>Пример  
  
```  
<?php  
   $server = "(local)";  
   $database = "AdventureWorks";  
   $conn = new PDO( "sqlsrv:server=$server ; Database = $database", "", "");  
  
   $stmt1 = $conn->query( "select * from Person.ContactType where ContactTypeID < 5 " );  
   while ( $row = $stmt1->fetch()) {   
      print($row['Name'] . "\n");   
   }  
   print( "\n---------- PDO::FETCH_ASSOC -------------\n" );  
   $stmt = $conn->query( "select * from Person.ContactType where ContactTypeID < 5 " );  
   $stmt->setFetchMode(PDO::FETCH_ASSOC);  
   $result = $stmt->fetch();  
   print_r( $result );  
  
   print( "\n---------- PDO::FETCH_NUM -------------\n" );  
   $stmt = $conn->query( "select * from Person.ContactType where ContactTypeID < 5 " );  
   $stmt->setFetchMode(PDO::FETCH_NUM);  
   $result = $stmt->fetch();  
   print_r ($result );  
  
   print( "\n---------- PDO::FETCH_BOTH -------------\n" );  
   $stmt = $conn->query( "select * from Person.ContactType where ContactTypeID < 5 " );  
   $stmt->setFetchMode(PDO::FETCH_BOTH);  
   $result = $stmt->fetch();  
   print_r( $result );  
  
   print( "\n---------- PDO::FETCH_LAZY -------------\n" );  
   $stmt = $conn->query( "select * from Person.ContactType where ContactTypeID < 5 " );  
   $stmt->setFetchMode(PDO::FETCH_LAZY);  
   $result = $stmt->fetch();  
   print_r( $result );  
  
   print( "\n---------- PDO::FETCH_OBJ -------------\n" );  
   $stmt = $conn->query( "select * from Person.ContactType where ContactTypeID < 5 " );  
   $stmt->setFetchMode(PDO::FETCH_OBJ);  
   $result = $stmt->fetch();  
   print $result->Name;  
   print( "\n \n" );  
?>  
```  
  
## <a name="see-also"></a>См. также:  
[Класс PDOStatement](../../connect/php/pdostatement-class.md)  
[PDO](http://go.microsoft.com/fwlink/?LinkID=187441)  
  
