---
title: Числовые функции | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- functions [ODBC], numeric functions
- numeric functions [ODBC]
ms.assetid: 4fa548dc-e8b0-4179-92ff-81d6a79d10c3
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: ca33d451fe5e1431d9bc4fb29196b98adcfb933f
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2018
ms.locfileid: "47620372"
---
# <a name="numeric-functions"></a>Числовые функции
В следующей таблице описаны числовые функции, включенные в набор скалярные функции ODBC. Путем вызова **SQLGetInfo** с *тип сведений* из SQL_NUMERIC_FUNCTIONS, приложение может определить, числовые функции, которые поддерживаются драйвером.  
  
 Все числовые функции возвращают значения типа данных SQL_FLOAT, за исключением ABS, ROUND, TRUNCATE, входа, FLOOR и CEILING, которые возвращают значения этих же данных введите в качестве входных параметров.  
  
 Аргументы обозначается как *выражение «числовое_выражение»* может быть именем столбца, результат другой скалярной функцией, или *litera цифровой*l, где базовый тип данных может быть представлено как SQL_NUMERIC SQL_ DECIMAL, SQL_TINYINT, SQL_SMALLINT, SQL_INTEGER, SQL_BIGINT, SQL_FLOAT, SQL_REAL или SQL_DOUBLE.  
  
 Аргументы обозначается как *float_exp* может быть именем столбца, результат другой скалярной функцией, или *числовой литерал*, где базовый тип данных можно представить как SQL_FLOAT.  
  
 Аргументы обозначается как *целое_выражение* может быть именем столбца, результат другой скалярной функцией, или *числовой литерал*, где базовый тип данных может быть представлено как SQL_TINYINT SQL_ SMALLINT, SQL_INTEGER или SQL_BIGINT.  
  
 Функция CURRENT_DATE CURRENT_TIME и CURRENT_TIMESTAMP скалярные функции были добавлены в ODBC 3.0 в соответствии со стандартом SQL-92.  
  
|Компонент|Описание|  
|--------------|-----------------|  
|**ABS (** *выражение «числовое_выражение»* **)** (ODBC 1.0)|Возвращает абсолютное значение *выражение «числовое_выражение»*.|  
|**ACOS (** *float_exp* **)** (ODBC 1.0)|Возвращает арккосинус *float_exp* как угол, выраженное в радианах.|  
|**ASIN (** *float_exp* **)** (ODBC 1.0)|Возвращает арксинус *float_exp* как угол, выраженное в радианах.|  
|**ATAN (** *float_exp* **)** (ODBC 1.0)|Возвращает арктангенс *float_exp* как угол, выраженное в радианах.|  
|**ATAN2 (** *float_exp1*, *float_exp2 ***)** (ODBC 2.0)|Возвращает арктангенс *x* и *y* координат, указанных по *float_exp1* и *float_exp2*, соответственно, угол выраженное в радианах.|  
|**CEILING (** *выражение «числовое_выражение»* **)** (ODBC 1.0)|Возвращает наименьшее целое число, больше или равно *выражение «числовое_выражение»*. Возвращаемое значение имеет тот же тип данных в качестве входного параметра.|  
|**COS (** *float_exp* **)** (ODBC 1.0)|Возвращает косинус *float_exp*, где *float_exp* угла в радианах.|  
|**COT (** *float_exp* **)** (ODBC 1.0)|Возвращает котангенс *float_exp*, где *float_exp* угла в радианах.|  
|**ГРАДУСОВ (** *выражение «числовое_выражение»* **)** (ODBC 2.0)|Возвращает число градусов, преобразованные из *выражение «числовое_выражение»* радиан.|  
|**EXP (** *float_exp* **)** (ODBC 1.0)|Возвращает значение экспоненты *float_exp*.|  
|**FLOOR (** *выражение «числовое_выражение»* **)** (ODBC 1.0)|Возвращает наибольшее целое число меньше или равно *выражение «числовое_выражение»*. Возвращаемое значение имеет тот же тип данных в качестве входного параметра.|  
|**LOG (** *float_exp* **)** (ODBC 1.0)|Возвращает натуральный логарифм числа *float_exp*.|  
|**LOG10 (** *float_exp* **)** (ODBC 2.0)|Возвращает десятичный логарифм *float_exp*.|  
|**MOD (** *integer_exp1*, *integer_exp2 ***)** (ODBC 1.0)|Возвращает остаток (остаток от деления) *integer_exp1* деления на *integer_exp2*.|  
|**PI ()** (ODBC 1.0)|Возвращает значение числа пи как значение с плавающей запятой.|  
|**POWER (** *выражение «числовое_выражение»*, *целое_выражение ***)** (ODBC 2.0)|Возвращает значение *выражение «числовое_выражение»* в степень *целое_выражение*.|  
|**RADIANS (** *выражение «числовое_выражение»* **)** (ODBC 2.0)|Возвращает количество радиан, преобразованные из *выражение «числовое_выражение»* градусов.|  
|**RAND (**[*целое_выражение*]**)** (ODBC 1.0)|Возвращает случайное значение с плавающей запятой, используя *целое_выражение* как необязательный начального значения.|  
|**ROUND (** *выражение «числовое_выражение»*, *целое_выражение ***)** (ODBC 2.0)|Возвращает *выражение «числовое_выражение»* округляется до *целое_выражение* помещает справа от десятичной запятой. Если *целое_выражение* отрицательное, *выражение «числовое_выражение»* округляется до &#124; *целое_выражение* &#124; помещает слева от десятичной запятой.|  
|**SIGN (** *выражение «числовое_выражение»* **)** (ODBC 1.0)|Возвращает индикатор знак *выражение «числовое_выражение»*. Если *выражение «числовое_выражение»* – меньше 1, значение равно нулю, возвращается. Если *выражение «числовое_выражение»* равно нулю, возвращается значение 0. Если *выражение «числовое_выражение»* не равно нулю, возвращается 1.|  
|**SIN (** *float_exp* **)** (ODBC 1.0)|Возвращает синус *float_exp*, где *float_exp* угла в радианах.|  
|**SQRT (** *float_exp* **)** (ODBC 1.0)|Возвращает квадратный корень из *float_exp*.|  
|**TAN (** *float_exp* **)** (ODBC 1.0)|Возвращает тангенс *float_exp*, где *float_exp* угла в радианах.|  
|**TRUNCATE (** *выражение «числовое_выражение»*, *целое_выражение ***)** (ODBC 2.0)|Возвращает *выражение «числовое_выражение»* усечено до *целое_выражение* помещает справа от десятичной запятой. Если *целое_выражение* отрицательное, *выражение «числовое_выражение»* усекается до &#124; *целое_выражение* &#124; помещает слева от десятичной запятой.|
