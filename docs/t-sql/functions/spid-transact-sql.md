---
title: '@@SPID (Transact-SQL) | Documents Microsoft'
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '@@SPID'
- '@@SPID_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- '@@SPID function'
- session_id
- server process IDs [SQL Server]
- IDs [SQL Server], user processes
- SPID
- session IDs [SQL Server]
- process ID of current user process
ms.assetid: df955d32-8194-438e-abee-387eebebcbb7
caps.latest.revision: 39
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 69413cf65e25d2ee962e4e3a7325a019e321c164
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="spid-transact-sql"></a>@@SPID (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Renvoie l'ID de session du processus utilisateur actuel.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
@@SPID  
```  
  
## <a name="return-types"></a>Types de retour  
 **smallint**  
  
## <a name="remarks"></a>Notes  
 @@SPID peut être utilisé pour identifier le processus utilisateur en cours dans la sortie de **sp_who**.  
  
## <a name="examples"></a>Exemples  
 Cet exemple renvoie l'identificateur de session, le nom de connexion et le nom de l'utilisateur pour le processus utilisateur actuel.  
  
```  
SELECT @@SPID AS 'ID', SYSTEM_USER AS 'Login Name', USER AS 'User Name';  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
ID     Login Name                     User Name                       
------ ------------------------------ ------------------------------  
54     SEATTLE\joanna                 dbo                             
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Exemples : [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] et[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 Cet exemple retourne le [!INCLUDE[ssDW](../../includes/ssdw-md.md)] ID de session, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contrôler l’ID de session de nœud, nom de connexion et nom d’utilisateur pour le processus utilisateur actuel.  
  
```  
SELECT SESSION_ID() AS ID, @@SPID AS 'Control ID', SYSTEM_USER AS 'Login Name', USER AS 'User Name';  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions de configuration](../../t-sql/functions/configuration-functions-transact-sql.md)   
 [sp_lock &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-lock-transact-sql.md)   
 [sp_who](../../relational-databases/system-stored-procedures/sp-who-transact-sql.md)  
  
  


