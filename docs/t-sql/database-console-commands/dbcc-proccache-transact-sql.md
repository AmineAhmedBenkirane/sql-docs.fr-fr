---
title: DBCC PROCCACHE (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 07/17/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DBCC PROCCACHE
- DBCC_PROCCACHE_TSQL
- PROCCACHE_TSQL
- PROCCACHE
dev_langs:
- TSQL
helpviewer_keywords:
- procedure cache [SQL Server]
- displaying procedure cache information
- DBCC PROCCACHE statement
ms.assetid: 7a4f9f8a-13ff-4bf2-ba29-c17012a23659
caps.latest.revision: 31
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 97e617e7867c90bf1e66c5e64e37b9039087d463
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="dbcc-proccache-transact-sql"></a>DBCC PROCCACHE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

Affiche des informations sous forme de table relatives au cache de procédure.
  
![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntaxe  
  
```sql
DBCC PROCCACHE [ WITH NO_INFOMSGS ]  
```  
  
## <a name="arguments"></a>Arguments  
 par  
 Permet de spécifier des options.  
  
 NO_INFOMSGS  
 Supprime tous les messages d'information dont le niveau de gravité est compris entre 0 et 10.  
  
## <a name="remarks"></a>Notes  
Le cache de procédure permet de mettre en cache les plans compilés et exécutables afin d'accélérer l'exécution des traitements. Les entrées d'un cache de procédure sont situées à un niveau de traitement. Le cache de procédure comporte les entrées suivantes :
-   Plans compilés  
-   Plans d'exécution  
-   Arborescence d'algébrisation  
-   Procédures étendues  
  
## <a name="result-sets"></a>Jeux de résultats  
Le tableau suivant décrit les colonnes du jeu de résultats.
  
|Nom de colonne| Description|  
|-----------------|-----------------|  
|**Num proc tampons**|Nombre total de pages utilisées par toutes les entrées du cache de procédure.|  
|**tampons de proc num utilisés**|Nombre total de pages utilisées par toutes les entrées en cours d'utilisation.|  
|**tampons de proc num actives**|Pour compatibilité descendante uniquement. Nombre total de pages utilisées par toutes les entrées en cours d'utilisation.|  
|**taille du cache de procédure**|Nombre total d'entrées du cache de procédure.|  
|**cache de procédure utilisé**|Nombre total d'entrées en cours d'utilisation.|  
|**cache de procédure actif**|Pour compatibilité descendante uniquement. Nombre total d'entrées en cours d'utilisation.|  
  
## <a name="permissions"></a>Permissions  
Nécessite l’appartenance au rôle de serveur fixe **sysadmin** ou au rôle de base de données fixe **db_owner** .
  
## <a name="see-also"></a>Voir aussi  
[DBCC &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-transact-sql.md)
  
  

