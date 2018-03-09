---
title: sp_scriptsubconflicttable (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- sp_scriptsubconflicttable
- sp_scriptsubconflicttable_TSQL
helpviewer_keywords:
- sp_scriptsubconflicttable
ms.assetid: 13867145-3dad-47a4-8d50-a65175418479
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: db78a4bee31ae7962e6401fb2ef54f3d1e1488b7
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="spscriptsubconflicttable-transact-sql"></a>sp_scriptsubconflicttable (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Génère un script afin de créer une table de conflits sur l'Abonné pour un article d'abonnement en attente donné. Le script généré est exécuté sur la base de données d'abonnement de l'Abonné. Cette procédure stockée est exécutée sur le serveur de publication dans la base de données de publication.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
sp_scriptsubconflicttable [@publication =] 'publication'    , [@article =] 'article'  
```  
  
## <a name="arguments"></a>Arguments  
 [  **@publication=**] **'***publication***'**  
 Nom de la publication contenant l'article. Le nom doit être unique dans la base de données. *publication* est **sysname**, sans valeur par défaut.  
  
 [  **@article=**] **'***article***'**  
 Nom de l'article d'abonnement. *article* est **sysname**, sans valeur par défaut.  
  
## <a name="return-code-values"></a>Valeurs des codes de retour  
 **0** (réussite) ou **1** (échec)  
  
## <a name="result-sets"></a>Jeux de résultats  
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**cmdtext**|**nvarchar(4000)**|Retourne le script [!INCLUDE[tsql](../../includes/tsql-md.md)] pour la création de la table de conflits sur l'Abonné pour l'article d'abonnement en attente. Ce script est exécuté dans la base de données d'abonnement de l'Abonné.|  
  
## <a name="remarks"></a>Notes  
 **sp_scriptsubconflicttable** est utilisé pour les abonnés qui ont des abonnements où l’instantané initial est appliqué manuellement. La table de conflits est une table facultative sur l'Abonné.  
  
## <a name="permissions"></a>Permissions  
 Seuls les membres de la **sysadmin** rôle serveur fixe ou **db_owner** du rôle de base de données fixe peut exécuter **sp_scriptsubconflicttable**.  
  
## <a name="see-also"></a>Voir aussi  
 [Détection et résolution des conflits de mise à jour en attente](../../relational-databases/replication/transactional/updatable-subscriptions-queued-updating-conflict-resolution.md)   
 [Procédures stockées système &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
