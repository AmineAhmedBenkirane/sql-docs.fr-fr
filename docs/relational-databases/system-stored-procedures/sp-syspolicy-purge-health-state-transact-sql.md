---
title: sp_syspolicy_purge_health_state (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_syspolicy_purge_health_state_TSQL
- sp_syspolicy_purge_health_state
dev_langs: TSQL
helpviewer_keywords: sp_syspolicy_purge_health_state
ms.assetid: 4ba4aa91-4c19-41c7-b70d-5fd9d0e89a5e
caps.latest.revision: "7"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: e5421e3faa445f78dfcd1f885b6703a402bfb500
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="spsyspolicypurgehealthstate-transact-sql"></a>sp_syspolicy_purge_health_state (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Supprime les états d'intégrité des stratégies de la Gestion basée sur des stratégies. Les états d'intégrité des stratégies sont des indicateurs visuels (symbole de parchemin marqué d'un « X » rouge) dans l'Explorateur d'objets qui vous permettent de déterminer sur quels nœuds une évaluation de stratégie a échoué.  
  
||  
|-|  
|**S’applique à**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] jusqu’à [version actuelle](http://go.microsoft.com/fwlink/p/?LinkId=299658)).|  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
sp_syspolicy_purge_health_state [ @target_tree_root_with_id = ] 'target_tree_root_with_id'  
```  
  
## <a name="arguments"></a>Arguments  
 [  **@target_tree_root_with_id =** ] **'***target_tree_root_with_id***'**  
 Représente le nœud de l'Explorateur d'objets dont vous voulez supprimer l'état d'intégrité. *target_tree_root_with_id* est **nvarchar (400)**, avec NULL comme valeur par défaut.  
  
 Vous pouvez spécifier des valeurs de la colonne target_query_expression_with_id de la vue système msdb.dbo.syspolicy_system_health_state.  
  
## <a name="return-code-values"></a>Valeurs des codes de retour  
 **0** (réussite) ou **1** (échec)  
  
## <a name="remarks"></a>Notes  
 Vous devez exécuter sp_syspolicy_purge_health_state dans le contexte de la base de données système msdb.  
  
 Si vous exécutez cette procédure stockée sans aucun paramètre, l'état d'intégrité du système est supprimé pour tous les nœuds dans l'Explorateur d'objets.  
  
## <a name="permissions"></a>Permissions  
 Nécessite l'appartenance au rôle de base de données fixe PolicyAdministratorRole.  
  
> [!IMPORTANT]  
>  Élévation possible des informations d’identification : les utilisateurs du rôle PolicyAdministratorRole peuvent créer des déclencheurs de serveur et planifier des exécutions de stratégie qui peuvent affecter le fonctionnement de l’instance de la [!INCLUDE[ssDE](../../includes/ssde-md.md)]. Par exemple, les utilisateurs du rôle PolicyAdministratorRole peuvent créer une stratégie qui peut empêcher la plupart des objets soient créés dans le [!INCLUDE[ssDE](../../includes/ssde-md.md)]. Étant donné cette possible élévation des informations d’identification, le rôle PolicyAdministratorRole doit être accordé uniquement aux utilisateurs qui sont approuvés avec contrôle de la configuration de la [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant supprime les états d'intégrité pour un nœud spécifique dans l'Explorateur d'objets.  
  
```  
EXEC msdb.dbo.sp_syspolicy_purge_health_state @target_tree_root_with_id = 'Server/Database[@ID=7]';  
  
GO  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion basée sur la stratégie stockée procédures &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/policy-based-management-stored-procedures-transact-sql.md)  
  
  
