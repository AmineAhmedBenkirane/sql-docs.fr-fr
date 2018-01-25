---
title: "L’instruction DBCC FREEPROCCACHE (Transact-SQL) | Documents Microsoft"
ms.custom: 
ms.date: 10/13/2017
ms.prod: sql-non-specified
ms.prod_service: sql-data-warehouse, pdw, sql-database
ms.service: 
ms.component: t-sql|database-console-commands
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- FREEPROCCACHE_TSQL
- FREEPROCCACHE
- DBCC_FREEPROCCACHE_TSQL
- DBCC FREEPROCCACHE
dev_langs: TSQL
helpviewer_keywords:
- freeing procedure cache
- removing procedure cache elements
- deleting procedure cache elements
- DBCC FREEPROCCACHE statement
- procedure cache [SQL Server]
- clearing procedure cache
ms.assetid: 0e09d210-6f23-4129-aedb-3d56b2980683
caps.latest.revision: "61"
author: barbkess
ms.author: barbkess
manager: craigg
ms.workload: Active
ms.openlocfilehash: b5fd65fa2a764d87d2c5481a7c20560551ca3311
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="dbcc-freeproccache-transact-sql"></a>DBCC FREEPROCCACHE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2008-xxxx-asdw-pdw-md.md)]

Supprime tous les éléments du cache du plan, supprime un plan spécifique du cache du plan en spécifiant un handle de plan ou un handle SQL, ou supprime toutes les entrées de cache associées à un pool de ressources spécifié.

>[!NOTE]
>DBCC FREEPROCCACHE n'efface pas les statistiques d'exécution pour les procédures stockées compilées en mode natif. Le cache de procédures ne contient pas d'informations relatives aux procédures stockées compilées en mode natif. Toutes les statistiques d’exécution collectées à partir des exécutions de procédure seront affiche dans les vues de gestion dynamique de statistiques d’exécution : [sys.dm_exec_procedure_stats &#40; Transact-SQL &#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql.md) et [sys.dm_exec_query_plan &#40; Transact-SQL &#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-exec-query-plan-transact-sql.md).  
  
![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntaxe  
Syntaxe pour SQL Server :

```sql
DBCC FREEPROCCACHE [ ( { plan_handle | sql_handle | pool_name } ) ] [ WITH NO_INFOMSGS ]  
```  

Syntaxe de l’entrepôt de données SQL Azure et Parallel Data Warehouse :
  
```sql
DBCC FREEPROCCACHE [ ( COMPUTE | ALL ) ] 
     [ WITH NO_INFOMSGS ]   
[;]  
```  
  
## <a name="arguments"></a>Arguments  
 ( { *plan_handle* | *sql_handle* | *pool_name* } )  
*plan_handle* identifie de façon unique un plan de requête pour un lot exécuté et dont le plan réside dans le cache du plan. *plan_handle* est **varbinary(64)** et peut être obtenu à partir des objets de gestion dynamique suivants :  
 -   [sys.dm_exec_cached_plans](../../relational-databases/system-dynamic-management-views/sys-dm-exec-cached-plans-transact-sql.md)  
 -   [sys.dm_exec_requests](../../relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql.md)  
 -   [sys.dm_exec_query_memory_grants](../../relational-databases/system-dynamic-management-views/sys-dm-exec-query-memory-grants-transact-sql.md)  
 -   [sys.dm_exec_query_stats](../../relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql.md)  

*sql_handle* est le handle SQL du lot à effacer. *sql_handle* est **varbinary(64)** et peut être obtenu à partir des objets de gestion dynamique suivants :  
 -   [sys.dm_exec_query_stats](../../relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql.md)  
 -   [sys.dm_exec_requests](../../relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql.md)  
 -   [sys.dm_exec_cursors](../../relational-databases/system-dynamic-management-views/sys-dm-exec-cursors-transact-sql.md)  
 -   [sys.dm_exec_xml_handles](../../relational-databases/system-dynamic-management-views/sys-dm-exec-xml-handles-transact-sql.md)  
 -   [sys.dm_exec_query_memory_grants](../../relational-databases/system-dynamic-management-views/sys-dm-exec-query-memory-grants-transact-sql.md)  

*nom du pool* est le nom d’un pool de ressources du gouverneur de ressources. *pool_name* est **sysname** et peut être obtenu en interrogeant le [sys.dm_resource_governor_resource_pools](../../relational-databases/system-dynamic-management-views/sys-dm-resource-governor-resource-pools-transact-sql.md) vue de gestion dynamique.  
 Pour associer un groupe de charges de travail du gouverneur de ressources à un pool de ressources, interrogez la [sys.dm_resource_governor_workload_groups](../../relational-databases/system-dynamic-management-views/sys-dm-resource-governor-workload-groups-transact-sql.md) vue de gestion dynamique. Pour plus d’informations sur le groupe de charges de travail pour une session, interrogez la [sys.dm_exec_sessions](../../relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql.md) vue de gestion dynamique.  

  
 WITH NO_INFOMSGS  
 Supprime tous les messages d'information.  
  
 COMPUTE  
 Vider le cache du plan de requête à partir de chaque nœud de calcul. Ceci est la valeur par défaut.  
  
 ALL  
 Vider le cache du plan de requête à partir de chaque nœud de calcul et de nœud de contrôle.  

> [!NOTE]
> En commençant par [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)], le `ALTER DATABASE SCOPED CONFIGURATION CLEAR PROCEDURE_CACHE` pour effacer le cache de procédure (plan) pour la base de données dans la portée.

## <a name="remarks"></a>Notes  
Utilisez l'instruction DBCC FREEPROCCACHE pour effacer le cache du plan avec précaution. Effacement de la procédure (plan), le cache en sorte que tous les plans à supprimer et exécutions compile un plan de requête entrante au lieu de réutiliser un plan mis en cache précédemment. 

Cela peut entraîner une baisse temporaire et brutale des performances des requêtes en tant que le nombre de nouvelles compilations augmente. Pour chaque mémoire cache effacée dans le cache du plan, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] journal des erreurs contient le message d’information suivant : «[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a rencontré l’occurrence (s) de %d de vidages de mémoire pour les vidages de « %s » (partie du cache du plan) en raison d’opérations 'DBCC FREEPROCCACHE' ou 'DBCC FREESYSTEMCACHE'. » Ce message est enregistré toutes les cinq minutes si le cache est vidé au cours de cet intervalle de temps.

Les opérations de reconfiguration suivantes effacent également le cache de procédures :
-   access check cache bucket count  
-   access check cache quota  
-   clr enabled  
-   cost threshold for parallelism  
-   cross db ownership chaining  
-   index create memory  
-   max degree of parallelism  
-   max server memory  
-   max text repl size  
-   max worker threads  
-   min memory per query  
-   min server memory  
-   query governor cost limit  
-   query wait  
-   remote query timeout  
-   user options  
  
## <a name="result-sets"></a>Jeux de résultats  
Lorsque la clause WITH NO_INFOMSGS n’est pas spécifiée, DBCC FREEPROCCACHE retourne le message : « exécution de DBCC terminée. Si DBCC vous a adressé des messages d'erreur, contactez l'administrateur système. »
  
## <a name="permissions"></a>Autorisations  
S’applique à : [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)],[!INCLUDE[ssPDW](../../includes/sspdw-md.md)] 
- Nécessite l'autorisation ALTER SERVER STATE sur le serveur.  

S’applique à :[!INCLUDE[ssSDW](../../includes/sssdw-md.md)]
- L’appartenance au rôle de serveur fixe DB_OWNER.  

## <a name="general-remarks-for-includesssdwincludessssdw-mdmd-and-includesspdwincludessspdw-mdmd"></a>Remarques d’ordre général pour [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] et[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
Plusieurs commandes DBCC FREEPROCCACHE peuvent être exécutées simultanément.
Dans [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] ou [!INCLUDE[ssPDW](../../includes/sspdw-md.md)], l’effacement du cache de plan peut entraîner une baisse temporaire des performances des requêtes que les requêtes entrantes compiler un nouveau plan, au lieu de réutiliser les précédemment plan en cache. 

DBCC FREEPROCCACHE (calcul) provoque uniquement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de recompiler des requêtes lorsqu’elles sont exécutées sur les nœuds de calcul. Cela n’entraîne pas [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] ou [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] à recompiler le plan de requête parallèle est généré sur le nœud de contrôle.
DBCC FREEPROCCACHE peut être annulée lors de l’exécution.
  
## <a name="limitations-and-restrictions-for-includesssdwincludessssdw-mdmd-and-includesspdwincludessspdw-mdmd"></a>Limitations et Restrictions pour [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] et[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
DBCC FREEPROCCACHE ne peut pas être exécuté dans une transaction.
DBCC FREEPROCCAHCE n’est pas pris en charge dans une instruction d’explication.
  
## <a name="metadata-for-includesssdwincludessssdw-mdmd-and-includesspdwincludessspdw-mdmd"></a>Métadonnées pour [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] et[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
Une nouvelle ligne est ajoutée à la vue système sys.pdw_exec_requests lors de l’exécution de DBCC FREEPROCCACHE.

## <a name="examples-includessnoversionincludesssnoversion-mdmd"></a>Exemples :[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]  
  
### <a name="a-clearing-a-query-plan-from-the-plan-cache"></a>A. Effacement d'un plan de requête du cache du plan  
L'exemple suivant efface un plan de requête du cache du plan en spécifiant le descripteur du plan de requête. Pour vérifier que l'exemple de requête se trouve dans le cache du plan, la requête est d'abord exécutée. Le `sys.dm_exec_cached_plans` et `sys.dm_exec_sql_text` vues de gestion dynamique sont interrogées pour retourner le descripteur de plan pour la requête. 

Puis, la valeur du descripteur de plan extraite du jeu de résultats est insérée dans l'instruction `DBCC FREEPROCACHE` pour supprimer uniquement le plan du cache du plan.
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT * FROM Person.Address;  
GO  
SELECT plan_handle, st.text  
FROM sys.dm_exec_cached_plans   
CROSS APPLY sys.dm_exec_sql_text(plan_handle) AS st  
WHERE text LIKE N'SELECT * FROM Person.Address%';  
GO  
```  
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]

```
plan_handle                                         text  
--------------------------------------------------  -----------------------------  
0x060006001ECA270EC0215D05000000000000000000000000  SELECT * FROM Person.Address;  
  
(1 row(s) affected)
 ```
 
```sql  
-- Remove the specific plan from the cache.  
DBCC FREEPROCCACHE (0x060006001ECA270EC0215D05000000000000000000000000);  
GO  
```  
  
### <a name="b-clearing-all-plans-from-the-plan-cache"></a>B. Effacement de tous les plans du cache du plan  
L'exemple suivant efface tous les éléments du cache du plan. WITH `NO_INFOMSGS` clause est spécifiée pour l’empêcher de s’afficher le message d’information.
  
```sql  
DBCC FREEPROCCACHE WITH NO_INFOMSGS;  
```  
  
### <a name="c-clearing-all-cache-entries-associated-with-a-resource-pool"></a>C. Effacement de toutes les entrées de cache associées à un pool de ressources  
L'exemple suivant efface toutes les entrées de cache associées à un pool de ressources spécifié. Le `sys.dm_resource_governor_resource_pools` affichage est d’abord interrogée pour obtenir la valeur de *pool_name*.
  
```sql  
SELECT * FROM sys.dm_resource_governor_resource_pools;  
GO  
DBCC FREEPROCCACHE ('default');  
GO  
```  
  
## <a name="examples-includesssdwincludessssdw-mdmd-and-includesspdwincludessspdw-mdmd"></a>Exemples : [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] et[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="d-dbcc-freeproccache-basic-syntax-examples"></a>D. Exemples de syntaxe de base de l’instruction DBCC FREEPROCCACHE  
L’exemple suivant supprime tous les caches de plan de requête existant à partir des nœuds de calcul. Bien que le contexte est défini sur UserDbSales, les caches de plan de requête de nœud calcul pour toutes les bases de données seront sera supprimés. La clause WITH NO_INFOMSGS empêche les messages d’information d’apparaître dans les résultats.  
  
```sql
USE UserDbSales;  
DBCC FREEPROCCACHE (COMPUTE) WITH NO_INFOMSGS;
```  
  
 L’exemple suivant possède les mêmes résultats que l’exemple précédent, à ceci près que les messages d’information s’affichent dans les résultats.  
  
```sql
USE UserDbSales;  
DBCC FREEPROCCACHE (COMPUTE);  
```  
  
Lorsque les messages d’information sont requis et l’exécution est réussie, les résultats de requête aura une ligne par nœud de calcul.
  
### <a name="e-granting-permission-to-run-dbcc-freeproccache"></a>E. Accorder une autorisation pour exécuter DBCC FREEPROCCACHE  
L’exemple suivant donne l’autorisation de David pour exécuter DBCC FREEPROCCACHE de connexion.  
  
```sql
GRANT ALTER SERVER STATE TO David; 
GO
```  
  
## <a name="see-also"></a>Voir aussi  
[DBCC &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-transact-sql.md)  
[Resource Governor](../../relational-databases/resource-governor/resource-governor.md)  
[ALTER DATABASE SCOPED CONFIGURATION &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-scoped-configuration-transact-sql.md)
  
  
