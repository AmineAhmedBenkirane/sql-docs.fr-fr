---
title: CURRENT_TIMESTAMP (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/24/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- CURRENT_TIMESTAMP
- CURRENT_TIMESTAMP_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- dates [SQL Server], functions
- niladic functions
- current date and time [SQL Server]
- time [SQL Server], current
- date and time [SQL Server], CURRENT_TIMESTAMP
- functions [SQL Server], time
- system date and time [SQL Server]
- system time [SQL Server]
- functions [SQL Server], date and time
- time [SQL Server], functions
- dates [SQL Server], current date and time
- dates [SQL Server], system date and time
- CURRENT_TIMESTAMP function [SQL Server]
- time [SQL Server], system
ms.assetid: c724d9cc-7b1f-4c71-bdf5-08bc52b33afc
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Active
ms.openlocfilehash: 5248e50bbcfeef5b57b220899f85800af98f9877
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="currenttimestamp-transact-sql"></a>CURRENT_TIMESTAMP (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

Renvoie l’horodateur système de base de données actuel en tant que valeur **datetime** sans le décalage de fuseau horaire de la base de données. Cette valeur est dérivée du système d'exploitation de l'ordinateur sur lequel l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécute.
  
> [!NOTE]  
>  SYSDATETIME et SYSUTCDATE ont plus de précision en fractions de seconde que GETDATE et GETUTCDATE. SYSDATETIMEOFFSET inclut le décalage de fuseau horaire système. SYSDATETIME, SYSUTCDATE et SYSDATETIMEOFFSET peuvent être assignés à une variable de chacun des types de date et d'heure.  
  
Cette fonction est l’équivalent SQL ANSI de [GETDATE](../../t-sql/functions/getdate-transact-sql.md).
  
Pour obtenir une vue d’ensemble de tous les types de données et fonctions de date et d’heure [!INCLUDE[tsql](../../includes/tsql-md.md)], consultez [Types de données et fonctions de date et d’heure](../../t-sql/functions/date-and-time-data-types-and-functions-transact-sql.md).
  
![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntaxe  
  
```sql
CURRENT_TIMESTAMP  
```  
  
## <a name="arguments"></a>Arguments  
Ne nécessite aucun argument.
  
## <a name="return-type"></a>Type de retour  
**datetime**
  
## <a name="remarks"></a>Notes   
Les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] peuvent faire référence à CURRENT_TIMESTAMP partout où elles peuvent faire référence à une expression **datetime**.
  
CURRENT_TIMESTAMP est une fonction non déterministe. Les vues et les expressions qui référencent cette colonne ne peuvent pas être indexées.
  
## <a name="examples"></a>Exemples  
Les exemples suivants utilisent les six fonctions système [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui renvoient les date et heure actuelles pour retourner la date, l’heure ou les deux. Les valeurs sont retournées en séries et leurs fractions de seconde peuvent différer.
  
### <a name="a-get-the-current-system-date-and-time"></a>A. Obtention des date et heure système actuelles  
  
```sql
SELECT SYSDATETIME()  
    ,SYSDATETIMEOFFSET()  
    ,SYSUTCDATETIME()  
    ,CURRENT_TIMESTAMP  
    ,GETDATE()  
    ,GETUTCDATE();  
/* Returned:  
SYSDATETIME()      2007-04-30 13:10:02.0474381  
SYSDATETIMEOFFSET()2007-04-30 13:10:02.0474381 -07:00  
SYSUTCDATETIME()   2007-04-30 20:10:02.0474381  
CURRENT_TIMESTAMP  2007-04-30 13:10:02.047  
GETDATE()          2007-04-30 13:10:02.047  
GETUTCDATE()       2007-04-30 20:10:02.047  
```  
  
### <a name="b-get-the-current-system-date"></a>B. Obtention de la date système actuelle  
  
```sql
SELECT CONVERT (date, SYSDATETIME())  
    ,CONVERT (date, SYSDATETIMEOFFSET())  
    ,CONVERT (date, SYSUTCDATETIME())  
    ,CONVERT (date, CURRENT_TIMESTAMP)  
    ,CONVERT (date, GETDATE())  
    ,CONVERT (date, GETUTCDATE());  
  
/* Returned   
SYSDATETIME()      2007-05-03  
SYSDATETIMEOFFSET()2007-05-03  
SYSUTCDATETIME()   2007-05-04  
CURRENT_TIMESTAMP  2007-05-03  
GETDATE()          2007-05-03  
GETUTCDATE()       2007-05-04  
*/  
```  
  
### <a name="c-get-the-current-system-time"></a>C. Obtention de l'heure système actuelle  
  
```sql
SELECT CONVERT (time, SYSDATETIME())  
    ,CONVERT (time, SYSDATETIMEOFFSET())  
    ,CONVERT (time, SYSUTCDATETIME())  
    ,CONVERT (time, CURRENT_TIMESTAMP)  
    ,CONVERT (time, GETDATE())  
    ,CONVERT (time, GETUTCDATE());  
  
/* Returned  
SYSDATETIME()      13:18:45.3490361  
SYSDATETIMEOFFSET()13:18:45.3490361  
SYSUTCDATETIME()   20:18:45.3490361  
CURRENT_TIMESTAMP  13:18:45.3470000  
GETDATE()          13:18:45.3470000  
GETUTCDATE()       20:18:45.3470000  
*/  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Exemples : [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] et [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
```sql
SELECT CURRENT_TIMESTAMP;  
```  
  
## <a name="see-also"></a>Voir aussi
[CAST et CONVERT &#40;Transact-SQL&#41;](../../t-sql/functions/cast-and-convert-transact-sql.md)
  
  

