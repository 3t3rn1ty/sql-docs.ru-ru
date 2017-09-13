---
title: "(Шаблон — символ(ы) для сопоставления) (Transact-SQL) | Документы Microsoft"
ms.custom: 
ms.date: 12/06/2016
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Match
- wildcard
- '[ ]'
- '[_]_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- wildcard characters [SQL Server]
- '[ ] (wildcard - character(s) to match)'
ms.assetid: 57817576-0bf1-49ed-b05d-fac27e8fed7a
caps.latest.revision: 32
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 18688c96cd0369905844d79a1a109f4e5032bce3
ms.contentlocale: ru-ru
ms.lasthandoff: 09/01/2017

---
# <a name="wildcard---characters-to-match-transact-sql"></a>(Шаблон — символ(ы) для сопоставления) (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Соответствует любому одиночному символу в пределах указанного диапазона или набора, указывается в квадратных скобках `[ ]`. Эти символы-шаблоны можно использовать при сравнении строк, которые задействуют соответствие шаблону, таких как `LIKE` и `PATINDEX`.  
  
## <a name="examples"></a>Примеры  
### <a name="a-simple-example"></a>А. простой пример   
Следующий пример возвращает имена, начинающиеся с буквы `m`. `[n-z]`Указывает, что вторая буква должен быть где-нибудь в диапазоне от `n` для `z`. Шаблон процента `%` позволяет ни один не символов, начиная с 3. `model` И `msdb` базы данных соответствуют этому критерию. `master` База данных не поддерживает и исключается из результирующего набора.
 
```tsql
SELECT name FROM sys.databases
WHERE name LIKE 'm[n-z]%';
```
[!INCLUDE[ssResult_md](../../includes/ssresult-md.md)]  

```
name
-----
model
msdb
```   
 Вы можете иметь дополнительные соответствующие базы данных установлен.


### <a name="b-more-complex-example"></a>Б. более сложный пример   
 В следующем примере оператор [] используется для поиска идентификаторов и имен всех сотрудников из базы данных [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)], имеющих адреса с четырехзначным почтовым индексом.  
  
```tsql  
-- Uses AdventureWorks  
  
SELECT e.BusinessEntityID, p.FirstName, p.LastName, a.PostalCode  
FROM HumanResources.Employee AS e  
INNER JOIN Person.Person AS p ON e.BusinessEntityID = p.BusinessEntityID  
INNER JOIN Person.BusinessEntityAddress AS ea ON e.BusinessEntityID = ea.BusinessEntityID  
INNER JOIN Person.Address AS a ON a.AddressID = ea.AddressID  
WHERE a.PostalCode LIKE '[0-9][0-9][0-9][0-9]';  
```  
  
 Результирующий набор:  
  
```  
EmployeeID      FirstName      LastName      PostalCode  
----------      ---------      ---------     ----------  
290             Lynn           Tsoflias      3000  
```  



  
## <a name="see-also"></a>См. также:  
 [КАК &#40; Transact-SQL &#41;](../../t-sql/language-elements/like-transact-sql.md)   
 [Функция PATINDEX &#40; Transact-SQL &#41;](../../t-sql/functions/patindex-transact-sql.md)   
  [% (Шаблон — символ(ы) для сопоставления)](../../t-sql/language-elements/percent-character-wildcard-character-s-to-match-transact-sql.md)   
 [&#91; ^ &#93; (Шаблон — символ(ы) должны совпасть)](../../t-sql/language-elements/wildcard-character-s-not-to-match-transact-sql.md)     
 [_ (Шаблон — совпадение одного символа)](../../t-sql/language-elements/wildcard-match-one-character-transact-sql.md)  
    
  
