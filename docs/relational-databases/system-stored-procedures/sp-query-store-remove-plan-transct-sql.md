---
title: sp_query_store_remove_plan (Transct-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/29/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SYS.SP_QUERY_STORE_REMOVE_PLAN_TSQL
- SP_QUERY_STORE_REMOVE_PLAN_TSQL
- SP_QUERY_STORE_REMOVE_PLAN
- SYS.SP_QUERY_STORE_REMOVE_PLAN
dev_langs: TSQL
helpviewer_keywords:
- sys.sp_query_store_remove_plan
- sp_query_store_remove_plan
ms.assetid: 88734726-135b-4b61-9f3f-f568c1fbece6
caps.latest.revision: "8"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 3a3f797e44a7276fbdf14ff823a7cfd04b48c1b3
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="spquerystoreremoveplan-transct-sql"></a>sp_query_store_remove_plan (Transct-SQL)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  Supprime un plan unique à partir du magasin de requête.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
sp_query_store_remove_plan [ @plan_id = ] plan_id [;]  
```  
  
## <a name="arguments"></a>Arguments  
 [  **@plan_id =** ] *plan_id*  
 Est l’id du plan de requête à supprimer. *plan_id* est un **bigint**, sans valeur par défaut.  
  
## <a name="return-code-values"></a>Valeurs des codes de retour  
 0 (réussite) ou 1 (échec)  
  
## <a name="remarks"></a>Notes  
  
## <a name="permissions"></a>Permissions  
 Requiert le **EXECUTE** sur la base de données, et **supprimer** autorisation sur les affichages catalogue du magasin de requête.  
  
## <a name="examples"></a>Exemples  
 L’exemple suivant retourne des informations sur les requêtes dans le magasin de requêtes.  
  
```  
SELECT Txt.query_text_id, Txt.query_sql_text, Pl.plan_id, Qry.*  
FROM sys.query_store_plan AS Pl  
JOIN sys.query_store_query AS Qry  
    ON Pl.query_id = Qry.query_id  
JOIN sys.query_store_query_text AS Txt  
    ON Qry.query_text_id = Txt.query_text_id ;  
```  
  
 Après avoir identifié le plan_id que vous souhaitez supprimer, utilisez l’exemple suivant pour supprimer un plan de requête.  
  
```  
EXEC sp_query_store_remove_plan 3;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [sp_query_store_force_plan &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-query-store-force-plan-transact-sql.md)   
 [sp_query_store_remove_query &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-query-store-remove-query-transact-sql.md)   
 [sp_query_store_unforce_plan &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-query-store-unforce-plan-transact-sql.md)   
 [sp_query_store_reset_exec_stats &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-query-store-reset-exec-stats-transact-sql.md)   
 [sp_query_store_flush_db &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-query-store-flush-db-transact-sql.md)   
 [Affichages catalogue du Magasin des requêtes &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/query-store-catalog-views-transact-sql.md)   
 [Analyse des performances à l'aide du magasin de requêtes](../../relational-databases/performance/monitoring-performance-by-using-the-query-store.md)  
  
  