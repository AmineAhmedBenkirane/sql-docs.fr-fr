---
title: '@@NESTLEVEL (Transact-SQL) | Documents Microsoft'
ms.custom: 
ms.date: 09/17/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '@@NESTLEVEL'
- '@@NESTLEVEL_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- '@@NESTLEVEL function'
- nesting stored procedures
- stored procedure nesting levels [SQL Server]
ms.assetid: 8c0b2134-8616-44f6-addc-6583c432fb62
caps.latest.revision: 40
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: aecf422ca2289b2a417147eb402921bb8530d969
ms.openlocfilehash: 4945bbe718bd8561100a3dd8e296a9f1faa9d93a
ms.contentlocale: fr-fr
ms.lasthandoff: 10/24/2017

---
# <a name="x40x40nestlevel-transact-sql"></a>& #x 40 ; & #x 40 ; NESTLEVEL (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Retourne le niveau d'imbrication de la procédure stockée en cours d'exécution (initialement 0) sur le serveur local.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
@@NESTLEVEL  
```  
  
## <a name="return-types"></a>Types de retour  
 **int**  
  
## <a name="remarks"></a>Notes  
 Chaque fois qu'une procédure stockée appelle une autre procédure stockée ou exécute du code managé en référençant une agrégation, un type ou une routine CLR (Common Language Runtime), le niveau d'imbrication est incrémenté. En cas de dépassement du maximum autorisé (32), la transaction s'arrête.  
  
 Lorsque @@NESTLEVEL est exécutée dans un [!INCLUDE[tsql](../../includes/tsql-md.md)] chaîne, la valeur retournée est 1 + actuel niveau d’imbrication. Lorsque @@NESTLEVEL est exécuté dynamiquement à l’aide de sp_executesql la valeur renvoyée est 2 + niveau d’imbrication actuel.  
  
## <a name="examples"></a>Exemples  
  
### <a name="a-using-nestlevel-in-a-procedure"></a>A. À l’aide de@NESTLEVEL dans une procédure  
 L'exemple suivant crée deux procédures : une qui appelle l'autre et une qui affiche le paramètre `@@NESTLEVEL` de chacune d'entre elles.  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID (N'usp_OuterProc', N'P')IS NOT NULL  
    DROP PROCEDURE usp_OuterProc;  
GO  
IF OBJECT_ID (N'usp_InnerProc', N'P')IS NOT NULL  
    DROP PROCEDURE usp_InnerProc;  
GO  
CREATE PROCEDURE usp_InnerProc AS   
    SELECT @@NESTLEVEL AS 'Inner Level';  
GO  
CREATE PROCEDURE usp_OuterProc AS   
    SELECT @@NESTLEVEL AS 'Outer Level';  
    EXEC usp_InnerProc;  
GO  
EXECUTE usp_OuterProc;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 ```
Outer Level  
-----------  
1  
  
Inner Level  
-----------  
2
```  
  
### <a name="b-calling-nestlevel"></a>B. Appel de @@NESTLEVEL  
 L’exemple suivant montre la différence entre les valeurs retournées par `SELECT`, `EXEC`, et `sp_executesql` lorsque chacune d’elles appelle `@@NESTLEVEL`.  
  
```  
CREATE PROC usp_NestLevelValues AS  
    SELECT @@NESTLEVEL AS 'Current Nest Level';  
EXEC ('SELECT @@NESTLEVEL AS OneGreater');   
EXEC sp_executesql N'SELECT @@NESTLEVEL as TwoGreater' ;  
GO  
EXEC usp_NestLevelValues;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 ```
Current Nest Level  
------------------  
1  
  
(1 row(s) affected)  
  
OneGreater  
-----------  
2  
  
(1 row(s) affected)  
  
TwoGreater  
-----------  
3  
  
(1 row(s) affected)
```  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions de configuration &#40;Transact-SQL&#41;](../../t-sql/functions/configuration-functions-transact-sql.md)   
 [Créer une procédure stockée](../../relational-databases/stored-procedures/create-a-stored-procedure.md)   
 [@@TRANCOUNT &#40;Transact-SQL&#41;](../../t-sql/functions/trancount-transact-sql.md)  
  
  

