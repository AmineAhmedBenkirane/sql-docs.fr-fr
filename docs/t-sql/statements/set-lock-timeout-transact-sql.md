---
title: SET LOCK_TIMEOUT (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 09/11/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- LOCK_TIMEOUT_TSQL
- SET_LOCK_TIMEOUT_TSQL
- SET LOCK_TIMEOUT
- LOCK_TIMEOUT
dev_langs:
- TSQL
helpviewer_keywords:
- timeout options [SQL Server], locks
- releasing locks
- LOCK_TIMEOUT option
- SET LOCK_TIMEOUT statement
- locking [SQL Server], time-outs
- wait time for lock releases [SQL Server]
ms.assetid: dd0c389e-956d-435e-bf71-e16624a0a215
caps.latest.revision: 26
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: On Demand
ms.translationtype: MT
ms.sourcegitcommit: 754242a86367b07b98caa9f70f457b70d0840075
ms.openlocfilehash: 3de86c7f33afd6e708ad8e773470ec650e092d2c
ms.contentlocale: fr-fr
ms.lasthandoff: 09/12/2017

---
# <a name="set-locktimeout-transact-sql"></a>SET LOCK_TIMEOUT (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Spécifie le nombre de millisecondes de qu'attente d’une instruction d’un verrou est libéré.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
SET LOCK_TIMEOUT timeout_period  
```  
  
## <a name="arguments"></a>Arguments  
 *timeout_period*  
 Est le nombre de millisecondes écoulées avant que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] renvoie une erreur de verrouillage. La valeur -1 (par défaut) indique qu'il n'y a pas de délai d'expiration (et par conséquent une attente infinie).  
  
 Si le délai d'attente avant la libération d'un verrou est supérieur au délai d'expiration spécifié, une erreur est renvoyée. Une valeur égale à 0 signifie que l'instruction n'attend pas et qu'elle retourne un message dès qu'elle rencontre un verrou.  
  
## <a name="remarks"></a>Notes  
 Au début d'une connexion, la valeur de ce paramètre est -1 Une fois celle-ci modifiée, le nouveau paramètre reste en vigueur pour le reste de la durée de la connexion.  
  
 L'option SET LOCK_TIMEOUT est appliquée lors de l'exécution, et non pas lors de l'analyse.  
  
 L'indicateur de verrouillage READPAST est une alternative à cette option SET.  
  
 Les instructions CREATE DATABASE, ALTER DATABASE et DROP DATABASE ignorent le paramètre SET LOCK_TIMEOUT.  
  
## <a name="permissions"></a>Permissions  
 Nécessite l'appartenance au rôle **public** .  
  
## <a name="examples"></a>Exemples  
  
### <a name="a-set-the-lock-timeout-to-1800-milliseconds"></a>R : définir le délai d’attente de verrou à 1 800 millisecondes  
 L'exemple suivant définit le délai d'attente de déverrouillage à `1800` millisecondes.  
  
```sql  
SET LOCK_TIMEOUT 1800;  
GO  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Exemples : [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] et[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="b-set-the-lock-timeout-to-wait-forever-for-a-lock-to-be-released"></a>B. Définir le délai d’attente de verrou pour attendre indéfiniment un verrou soit libéré.  
 L’exemple suivant définit le délai d’attente de verrou pour attendre indéfiniment et ne jamais expirer. Il s’agit du comportement par défaut qui est déjà défini au début de chaque connexion.  
  
```sql  
SET LOCK_TIMEOUT -1;  
```  
  
 L'exemple suivant définit le délai d'attente de déverrouillage à `1800` millisecondes. Dans cette version, [!INCLUDE[ssDW](../../includes/ssdw-md.md)] sera analyser l’instruction avec succès, mais ignore la valeur 1800 et continuer à utiliser le comportement par défaut.  
  
```sql  
SET LOCK_TIMEOUT 1800;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [@@LOCK_TIMEOUT &#40;Transact-SQL&#41;](../../t-sql/functions/lock-timeout-transact-sql.md)   
 [Instructions SET &#40;Transact-SQL&#41;](../../t-sql/statements/set-statements-transact-sql.md)  
  
  


