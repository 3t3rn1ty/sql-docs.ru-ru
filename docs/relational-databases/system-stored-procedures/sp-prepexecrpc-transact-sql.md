---
title: sp_prepexecrpc (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/02/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_cursor_prepexecrpc
- sp_cursor_prepexecrpc_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_prepexecrpc
ms.assetid: 35d686f2-ef31-4eaa-baa9-9cef5d6c87c2
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: aced26fc44c40e28fafc9bb8bcc7d9a44a01959f
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2018
ms.locfileid: "47837902"
---
# <a name="spprepexecrpc-transact-sql"></a>sp_prepexecrpc (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Подготавливает и вызывает параметризованную хранимую процедуру, заданную с помощью идентификатора RPC. sp_prepexecrpc вызывается с ID = 14 в пакете потока табличных данных.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_prepexecrpc handle OUTPUT, RPCCall  
    [ , bound_param ] [ ,...n]]  
```  
  
## <a name="arguments"></a>Аргументы  
 *Дескриптор*  
 Сформированный системой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] идентификатор подготовленного дескриптора. *обрабатывать* является обязательным параметром с **int** возвращаемое значение.  
  
 *RPCCall*  
 Определяет вызов хранимой процедуры с использованием канонического синтаксиса ODBC. *RPCCall* является обязательным параметром, который вызывает для **ntext** входное строковое значение.  
  
 *bound_param*  
 Означает необязательное использование дополнительных параметров. *bound_param* вызывает для входного значения любого типа данных для обозначения дополнительных параметров.  
  
## <a name="see-also"></a>См. также  
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
