---
title: ALTER DATABASE (Azure SQL Database) | Microsoft Docs
ms.custom: 
ms.date: 02/13/2018
ms.prod: 
ms.prod_service: sql-database
ms.reviewer: 
ms.service: sql-database
ms.component: t-sql|statements
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6fc5fd95-2045-4f20-a914-3598091bc7cc
caps.latest.revision: 
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 6c303c5abe51eaee2208028ea13991d2d557f1b3
ms.sourcegitcommit: a8311ec5ad8313e85e6989f70c5ff9ef120821d6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="alter-database-azure-sql-database"></a>ALTER DATABASE (Azure SQL Database)
[!INCLUDE[tsql-appliesto-xxxxxx-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-xxxxxx-asdb-xxxx-xxx-md.md)]

  Modifie une instance [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)]. Modifie le nom, l’édition et l’objectif de service d’une base de données, et permet de rejoindre un pool élastique et de définir les options de la base de données.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
-- Azure SQL Database Syntax  
ALTER DATABASE { database_name }  
{  
    MODIFY NAME = new_database_name  
  | MODIFY ( <edition_options> [, ... n] )   
  | SET { <option_spec> [ ,... n ] }   
  | ADD SECONDARY ON SERVER <partner_server_name>  
      [WITH ( <add-secondary-option>::= [, ... n] ) ]  
  | REMOVE SECONDARY ON SERVER <partner_server_name>  
  | FAILOVER  
  | FORCE_FAILOVER_ALLOW_DATA_LOSS  
}  
[;] 

<edition_options> ::=   
{  

      MAXSIZE = { 100 MB | 250 MB | 500 MB | 1 … 1024 … 4096 GB }    
    | EDITION = { 'basic' | 'standard' | 'premium' }   
    | SERVICE_OBJECTIVE = 
                 {  <service-objective>
                 | { ELASTIC_POOL (name = <elastic_pool_name>) }   
                 }   
}  

<add-secondary-option> ::=  
   {  
      ALLOW_CONNECTIONS = { ALL | NO }  
     | SERVICE_OBJECTIVE =   
                 {  <service-objective> 
                 | { ELASTIC_POOL ( name = <elastic_pool_name>) }   
                 }   
   }  

<service-objective> ::=  { 'S0' | 'S1' | 'S2' | 'S3'| 'S4'| 'S6'| 'S7'| 'S9'| 'S12' |
                 | 'P1' | 'P2' | 'P4'| 'P6' | 'P11'  | 'P15' }

```  
  
```
-- SET OPTIONS AVAILABLE FOR SQL Database  
-- Full descriptions of the set options are available in the topic   
-- ALTER DATABASE SET Options. The supported syntax is listed here.  

<option_spec> ::=   
{  
    <auto_option>   
  | <change_tracking_option> 
  | <cursor_option>   
  | <db_encryption_option>  
  | <db_update_option>   
  | <db_user_access_option>   
  | <delayed_durability_option>  
  | <parameterization_option>  
  | <query_store_options>  
  | <snapshot_option>  
  | <sql_option>   
  | <target_recovery_time_option>   
  | <termination>  
  | <temporal_history_retention>  
}  
  
<auto_option> ::=   
{  
    AUTO_CREATE_STATISTICS { OFF | ON [ ( INCREMENTAL = { ON | OFF } ) ] }   
  | AUTO_SHRINK { ON | OFF }   
  | AUTO_UPDATE_STATISTICS { ON | OFF }   
  | AUTO_UPDATE_STATISTICS_ASYNC { ON | OFF }  
}  

<change_tracking_option> ::=  
{  
  CHANGE_TRACKING   
   {   
       = OFF  
     | = ON [ ( <change_tracking_option_list > [,...n] ) ]   
     | ( <change_tracking_option_list> [,...n] )  
   }  
}  

   <change_tracking_option_list> ::=  
   {  
       AUTO_CLEANUP = { ON | OFF }   
     | CHANGE_RETENTION = retention_period { DAYS | HOURS | MINUTES }  
   }  

<cursor_option> ::=   
{  
    CURSOR_CLOSE_ON_COMMIT { ON | OFF }   
}  
  
<db_encryption_option> ::=  
    ENCRYPTION { ON | OFF }  
  
<db_update_option> ::=  
    { READ_ONLY | READ_WRITE }  
  
<db_user_access_option> ::=  
    { RESTRICTED_USER | MULTI_USER }  
  
<delayed_durability_option> ::=    DELAYED_DURABILITY = { DISABLED | ALLOWED | FORCED }  
  
<parameterization_option> ::=  
    PARAMETERIZATION { SIMPLE | FORCED }  
  
<query_store_options> ::=  
{  
    QUERY_STORE   
    {  
          = OFF   
        | = ON [ ( <query_store_option_list> [,... n] ) ]  
        | ( < query_store_option_list> [,... n] )  
        | CLEAR [ ALL ]  
    }  
}   
  
<query_store_option_list> ::=  
{  
      OPERATION_MODE = { READ_WRITE | READ_ONLY }   
    | CLEANUP_POLICY = ( STALE_QUERY_THRESHOLD_DAYS = number )  
    | DATA_FLUSH_INTERVAL_SECONDS = number   
    | MAX_STORAGE_SIZE_MB = number   
    | INTERVAL_LENGTH_MINUTES = number   
    | SIZE_BASED_CLEANUP_MODE = [ AUTO | OFF ]  
    | QUERY_CAPTURE_MODE = [ ALL | AUTO | NONE ]  
    | MAX_PLANS_PER_QUERY = number  
}  
  
<snapshot_option> ::=  
{  
    ALLOW_SNAPSHOT_ISOLATION { ON | OFF }  
  | READ_COMMITTED_SNAPSHOT {ON | OFF }  
  | MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT {ON | OFF }  
}  
<sql_option> ::=   
{  
    ANSI_NULL_DEFAULT { ON | OFF }   
  | ANSI_NULLS { ON | OFF }   
  | ANSI_PADDING { ON | OFF }   
  | ANSI_WARNINGS { ON | OFF }   
  | ARITHABORT { ON | OFF }   
  | COMPATIBILITY_LEVEL = { 100 | 110 | 120 | 130 | 140 }  
  | CONCAT_NULL_YIELDS_NULL { ON | OFF }   
  | NUMERIC_ROUNDABORT { ON | OFF }   
  | QUOTED_IDENTIFIER { ON | OFF }   
  | RECURSIVE_TRIGGERS { ON | OFF }   
}  
  
<termination>  ::=   
{  
    ROLLBACK AFTER integer [ SECONDS ]   
  | ROLLBACK IMMEDIATE   
  | NO_WAIT  
}  

<temporal_history_retention>  ::=  TEMPORAL_HISTORY_RETENTION { ON | OFF }
```  
  
 Pour obtenir une description complète des options SET, consultez [Options ALTER DATABASE SET &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql-set-options.md) et [Niveau de compatibilité ALTER DATABASE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql-compatibility-level.md).  
  
## <a name="arguments"></a>Arguments  
 *database_name*  
 Nom de la base de données à modifier.  
  
 CURRENT  
 Indique que la base de données actuelle en cours d'utilisation doit être modifiée.  
  
 MODIFY NAME **=***new_database_name*  
 Renomme la base de données avec le nom spécifié *nouveau_nom_base_de_données*. L’exemple suivant remplace le nom de la base de données `db1` par `db2` :   

```  
ALTER DATABASE db1  
    MODIFY Name = db2 ;  
```    

 MODIFY (EDITION **=** ['basic' | 'standard' | 'premium' ])    
 Modifie le niveau de service de la base de données. La prise en charge de 'premiumrs' a été supprimée. Pour poser des questions, utilisez cet alias de messagerie : premium-rs@microsoft.com.

L’exemple suivant remplace l’édition par `premium` :
  
```  
ALTER DATABASE current 
    MODIFY (EDITION = 'premium');
``` 

La modification d’EDITION échoue si la propriété MAXSIZE de la base de données a une valeur située en dehors de la plage valide prise en charge par cette édition.  

 MODIFY (MAXSIZE **=** [100 MB | 500 MB | 1 | 1024…4096] GB)  
 Spécifie la taille maximale de la base de données. La taille maximale doit être conforme au jeu de valeurs valide pour la propriété EDITION de la base de données. Le fait de modifier la taille maximale de la base de données peut entraîner la modification de la propriété EDITION de la base de données. Le tableau suivant contient la liste des valeurs de MAXSIZE prises en charge et des valeurs par défaut (D) des couches de service [!INCLUDE[ssSDS](../../includes/sssds-md.md)].  
  
|**MAXSIZE**|**De base**|**S0-S2**|**S3-S12**|**P1-P6**|**P11-P15**|  
|-----------------|---------------|------------------|-----------------|-----------------|-----------------|-----------------|  
|100 Mo|√|√|√|√|√|  
|250 Mo|√|√|√|√|√|  
|500 Mo|√|√|√|√|√|  
|1 Go|√|√|√|√|√|  
|2 Go|√ (D)|√|√|√|√|  
|5 Go|Néant|√|√|√|√|  
|10 GB|Néant|√|√|√|√|  
|20 Go|Néant|√|√|√|√|  
|30 Go|Néant|√|√|√|√|  
|40 Go|Néant|√|√|√|√|  
|50 Go|Néant|√|√|√|√|  
|100 Go|Néant|√|√|√|√|  
|150 Go|Néant|√|√|√|√|  
|200 Go|Néant|√|√|√|√|  
|250 Go|Néant|√ (D)|√ (D)|√|√|  
|300 Go|Néant|√|√|√|√|  
|400 Go|Néant|√|√|√|√|  
|500 Go|Néant|√|√|√ (D)|√|  
|750 Go|Néant|√|√|√|√|  
|1 024 Go|Néant|√|√|√|√ (D)|  
|À partir de 1 024 Go jusqu’à 4 096 Go par incréments de 256 Go*|Néant|Néant|Néant|Néant|√|√|  
  
 \* P11 et P15 autorisent MAXSIZE jusqu’à 4 To, 1 024 Go étant la taille par défaut.  P11 et P15 peuvent utiliser jusqu’à 4 To de stockage inclus sans frais supplémentaires. Dans le niveau Premium, une taille supérieure à 1 To est actuellement disponible pour MAXSIZE dans les régions suivantes : Est des États-Unis2, Ouest des États-Unis, Gouvernement des États-Unis - Virginie, Europe de l’Ouest, Centre de l’Allemagne, Asie du Sud-Est, Est du Japon, Est de l’Australie, Centre du Canada et Est du Canada. Pour connaître les limitations actuelles, consultez [Bases de données uniques](https://docs.microsoft.com/azure/sql-database-single-database-resources).  

  
 Les règles suivantes s'appliquent aux arguments MAXSIZE et EDITION.  
  
-   La valeur MAXSIZE, si spécifiée, doit être une valeur valide indiquée dans le tableau ci-dessus.  
  
-   Si EDITION est spécifié, mais MAXSIZE n'est pas spécifié, la valeur par défaut de l'édition est utilisée. Par exemple, si EDITION est défini à Standard et que MAXSIZE n'est pas spécifié, MAXSIZE est automatiquement défini à 500 Mo.  
  
-   Si MAXSIZE et EDITION ne sont pas spécifiés, la valeur de EDITION est définie sur Standard (S0), et celle de MAXSIZE sur 250 Go.  
 

 MODIFY (SERVICE_OBJECTIVE = \<service-objective>)  
 Spécifie le niveau de performances. L’exemple suivant modifie l’objectif de service d’une base de données Premium `P6` :
 
```  
ALTER DATABASE current 
    MODIFY (SERVICE_OBJECTIVE = 'P6');
```  
 Les valeurs possibles pour l’objectif de service sont : `S0`, `S1`, `S2`, `S3`, `S4`, `S6`, `S7`, `S9`, `S12`, `P1`, `P2`, `P4`, `P6`, `P11` ou `P15`. Pour plus d’informations sur les objectifs de service, ainsi que sur la taille, les éditions et les combinaisons d’objectifs de service, consultez [Niveaux de service et niveaux de performances Azure SQL Database](http://msdn.microsoft.com/library/azure/dn741336.aspx). Si le SERVICE_OBJECTIVE spécifié n’est pas pris en charge par l’EDITION, un message d’erreur s’affiche. Si vous voulez modifier la valeur de SERVICE_OBJECTIVE pour passer d'un niveau de service à un autre (par exemple de S1 à P1), vous devrez également modifier la valeur d'EDITION. La prise en charge des objectifs de service PRS a été supprimée. Pour poser des questions, utilisez cet alias de messagerie : premium-rs@microsoft.com. 
  
 MODIFY (SERVICE_OBJECTIVE = ELASTIC\_POOL (name = \<elastic_pool_name>)  
 Pour ajouter une base de données existante à un pool élastique, définissez le SERVICE_OBJECTIVE de la base de données sur ELASTIC_POOL et fournissez le nom du pool élastique. Vous pouvez également utiliser cette option pour ajouter la base de données à un autre pool élastique du même serveur. Pour plus d’informations, consultez [Créer et gérer un pool élastique SQL Database](https://azure.microsoft.com/documentation/articles/sql-database-elastic-pool-portal/). Pour supprimer une base de données d’un pool élastique, utilisez ALTER DATABASE pour définir le SERVICE_OBJECTIVE sur un niveau de performance de base de données.  

 ADD SECONDARY ON SERVER \<partner_server_name>  
 Crée une base de données secondaire de géoréplication de même nom sur un serveur partenaire, faisant ainsi de la base de données locale la base de données de géoréplication primaire, et commence à répliquer des données de manière asynchrone entre la base de données primaire et la nouvelle base de données secondaire. Si une base de données portant le même nom existe déjà dans la base de données secondaire, la commande échoue. La commande est exécutée sur la base de données MASTER, située sur le serveur qui héberge la base de données locale qui devient la base de données primaire.  
  
 WITH ALLOW_CONNECTIONS { **ALL** | NO }  
 Lorsque ALLOW_CONNECTIONS n’est pas spécifié, il est défini sur ALL par défaut. S’il est défini sur ALL, il s’agit d’une base de données en lecture seule qui autorise toutes les connexions disposant des autorisations nécessaires.  
  
 WITH SERVICE_OBJECTIVE {  'S0' | 'S1' | 'S2' | 'S3" | 'S4'| 'S6'| 'S7'| 'S9'| 'S12' | 'P1' | 'P2' | 'P4'| 'P6' | 'P11' | 'P15' }  
 Quand SERVICE_OBJECTIVE n’est pas spécifié, la base de données secondaire est créée au même niveau de service que la base de données primaire. Quand SERVICE_OBJECTIVE est spécifié, la base de données secondaire est créée au niveau spécifié. Cette option prend en charge la création de bases de données secondaires géorépliquées avec des niveaux de service moins coûteux. Le SERVICE_OBJECTIVE spécifié doit appartenir à la même édition que la source. Par exemple, vous ne pouvez pas spécifier S0 si l’édition est Premium.  
  
 ELASTIC_POOL (name = \<elastic_pool_name)  
 Quand ELASTIC_POOL n’est pas spécifié, la base de données secondaire n’est pas créée dans un pool élastique. Quand ELASTIC_POOL est spécifié, la base de données secondaire est créée dans le pool spécifié.  
  
> [!IMPORTANT]  
>  L’utilisateur qui exécute la commande ADD SECONDARY doit avoir le rôle de DBManager pour le serveur principal, appartenir au groupe db_owner de la base de données locale et avoir le rôle de DBManager pour le serveur secondaire.  
  
 REMOVE SECONDARY ON SERVER  \<partner_server_name>  
 Supprime la base de données secondaire géorépliquée spécifiée du serveur spécifié. La commande est exécutée sur la base de données MASTER, située sur le serveur qui héberge la base de données primaire.  
  
> [!IMPORTANT]  
>  L’utilisateur qui exécute la commande REMOVE SECONDARY doit avoir le rôle de DBManager pour le serveur principal.  
  
 FAILOVER  
 Promeut la base de données secondaire du partenariat de géoréplication sur laquelle est exécutée la commande, pour qu’elle devienne la base de données primaire et que la base de données primaire actuelle devienne secondaire. Dans le cadre de ce processus, le mode de géoréplication passe temporairement du mode asynchrone au mode synchrone. Pendant le processus de basculement :  
  
1.  La base de données primaire cesse d’accepter les nouvelles transactions.  
  
2.  Toutes les transactions en attente sont envoyées vers la base de données secondaire.  
  
3.  La base de données secondaire devient primaire, et commence la géoréplication asynchrone avec l’ancienne primaire/nouvelle secondaire.  
  
 Cette séquence garantit qu’aucune perte de données ne se produit. Lorsque les rôles sont permutés, la période pendant laquelle les deux bases de données sont indisponibles est d’environ 0 à 25 secondes. Au total, l’opération prend environ une minute. Si la base de données primaire n’est pas disponible lorsque cette commande est émise, la commande échoue et un message d’erreur indique que la base de données primaire n’est pas disponible. Si le processus de basculement ne se termine pas et semble bloqué, vous pouvez utiliser la commande de basculement forcé et accepter la perte de données. Ensuite, si vous avez besoin de récupérer les données perdues, adressez-vous à l’équipe DevOps (CSS).  
  
> [!IMPORTANT]  
>  L’utilisateur qui exécute la commande FAILOVER doit avoir le rôle de DBManager pour le serveur principal et le serveur secondaire.  
  
 FORCE_FAILOVER_ALLOW_DATA_LOSS  
 Promeut la base de données secondaire du partenariat de géoréplication sur laquelle est exécutée la commande, pour qu’elle devienne la base de données primaire et que la base de données primaire actuelle devienne secondaire. Utilisez cette commande uniquement lorsque la base de données primaire actuelle n’est plus disponible. Elle ne doit être utilisée qu’en cas de récupération d’urgence, lorsque la restauration de la disponibilité est critique, et qu’une petite perte de données est acceptable.  
  
 Pendant un basculement forcé :  
  
1.  La base de données secondaire spécifiée devient immédiatement la base de données primaire et commence à accepter les nouvelles transactions.  
  
2.  Lorsque la base de données primaire d’origine peut se reconnecter à la nouvelle base de données primaire, une sauvegarde incrémentielle est effectuée à partir de la base de données primaire d’origine et celle-ci devient la nouvelle base de données secondaire.  
  
3.  Pour récupérer des données à partir de cette sauvegarde incrémentielle de l’ancienne base de données primaire, l’utilisateur s’adresse à l’équipe DevOps/CSS.  
  
4.  S’il existe d’autres bases de données secondaires, celles-ci sont automatiquement reconfigurées pour devenir des bases de données secondaires de la nouvelle primaire. Ce processus est asynchrone et peut prendre un certain temps. Tant que la reconfiguration n’est pas terminée, les bases de données secondaires continuent d’être associées à l’ancienne base de données primaire.  
  
> [!IMPORTANT]  
>  L’utilisateur qui exécute la commande FORCE_FAILOVER_ALLOW_DATA_LOSS doit avoir le rôle de DBManager pour le serveur principal et le serveur secondaire.  
  
## <a name="remarks"></a>Notes   
 Pour supprimer une base de données, utilisez [DROP DATABASE](../../t-sql/statements/drop-database-transact-sql.md).  
  
 Pour diminuer la taille d'une base de données, utilisez [DBCC SHRINKDATABASE](../../t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql.md).  
  
 L'instruction ALTER DATABASE doit être exécutée en mode de validation automatique (mode de gestion des transactions par défaut) et n'est pas autorisée dans une transaction explicite ou implicite.  
  
 Cette opération entraîne la recompilation de tous les plans d'exécution ultérieurs et peut entraîner une baisse temporaire et brutale des performances des requêtes. Pour chaque mémoire cache effacée dans le cache de plan, le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contient le message d'information suivant : « [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a rencontré %d occurrence(s) de vidages de mémoire cache pour la mémoire cache '%s' (partie du cache du plan) en raison d'opérations de maintenance ou de reconfiguration de base de données ». Ce message est enregistré toutes les cinq minutes si le cache est vidé au cours de cet intervalle de temps.  
  
 Le cache de procédures est également vidé dans les scénarios suivants :  
  
-   L'option de base de données AUTO_CLOSE est activée (ON). Lorsqu'aucune connexion utilisateur ne fait référence ou n'utilise la base de données, la tâche en arrière-plan essaie de fermer et d'arrêter la base de données automatiquement.  
  
-   Vous exécutez plusieurs requêtes sur une base de données dont les options par défaut sont activées. Puis, la base de données est supprimée.  
  
-   Vous reconstruisez avec succès le journal des transactions d'une base de données.  
  
-   Vous restaurez une sauvegarde de base de données.  
  
-   Vous détachez une base de données.  
  
## <a name="viewing-database-information"></a>Affichage des informations de bases de données  
 Vous pouvez utiliser les affichages catalogue, les fonctions système et les procédures stockées du système pour retourner des informations sur les bases de données, les fichiers et les groupes de fichiers.  
  
## <a name="permissions"></a>Autorisations  
 Seule la connexion principale au niveau du serveur (créée par le processus de configuration) ou les membres du rôle de base de données `dbmanager` peuvent modifier une base de données.  
  
> [!IMPORTANT]  
>  Le propriétaire de la base de données ne peut pas modifier la base de données à moins d'être membre du rôle `dbmanager`.  
  
## <a name="examples"></a>Exemples  
  
### <a name="a-check-the-edition-options-and-change-them"></a>A. Vérifier et modifier les options d’édition :

```
SELECT Edition = DATABASEPROPERTYEX('db1', 'EDITION'),
        ServiceObjective = DATABASEPROPERTYEX('db1', 'ServiceObjective'),
        MaxSizeInBytes =  DATABASEPROPERTYEX('db1', 'MaxSizeInBytes');

ALTER DATABASE [db1] MODIFY (EDITION = 'Premium', MAXSIZE = 1024 GB, SERVICE_OBJECTIVE = 'P15');
```

### <a name="b-moving-a-database-to-a-different-elastic-pool"></a>B. Déplacer une base de données vers un autre pool élastique  
 Déplace une base de données existante dans un pool nommé pool1 :  
  
```  
ALTER DATABASE db1   
MODIFY ( SERVICE_OBJECTIVE = ELASTIC_POOL ( name = pool1 ) ) ;  
```  
  
### <a name="c-add-a-geo-replication-secondary"></a>C. Ajouter une base de données secondaire de géoréplication  
 Crée une base de données secondaire accessible en lecture db1 sur le serveur `secondaryserver`, qui est associée à la base de données db1 du serveur local.  
  
```  
ALTER DATABASE db1   
ADD SECONDARY ON SERVER secondaryserver   
WITH ( ALLOW_CONNECTIONS = ALL )  
```  
  
### <a name="d-remove-a-geo-replication-secondary"></a>D. Supprimer une base de données secondaire de géoréplication  
 Supprime la base de données secondaire db1 du serveur `secondaryserver`.  
  
```  
ALTER DATABASE db1   
REMOVE SECONDARY ON SERVER testsecondaryserver   
```  
  
### <a name="e-failover-to-a-geo-replication-secondary"></a>E. Basculer vers une base de données secondaire de géoréplication  
 Promeut la base de données secondaire db1 sur le serveur `secondaryserver` pour qu’elle devienne la nouvelle base de données primaire lorsqu’elle est exécutée sur le serveur `secondaryserver`.  
  
```  
ALTER DATABASE db1 FAILOVER  
```  
  
## <a name="see-also"></a>Voir aussi  
 [CREATE DATABASE &#40;Azure SQL Database&#41;](../../t-sql/statements/create-database-azure-sql-database.md)   
 [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](../../t-sql/functions/databasepropertyex-transact-sql.md)   
 [DROP DATABASE &#40;Transact-SQL&#41;](../../t-sql/statements/drop-database-transact-sql.md)   
 [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](../../t-sql/statements/set-transaction-isolation-level-transact-sql.md)   
 [EVENTDATA &#40;Transact-SQL&#41;](../../t-sql/functions/eventdata-transact-sql.md)   
 [sp_configure &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)   
 [sp_spaceused &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-spaceused-transact-sql.md)   
 [sys.databases &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-databases-transact-sql.md)   
 [sys.database_files &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-database-files-transact-sql.md)   
 [sys.database_mirroring_witnesses &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/database-mirroring-witness-catalog-views-sys-database-mirroring-witnesses.md)   
 [sys.data_spaces &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-data-spaces-transact-sql.md)   
 [sys.filegroups &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-filegroups-transact-sql.md)   
 [sys.master_files &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-master-files-transact-sql.md)   
 [Bases de données système](../../relational-databases/databases/system-databases.md)  
  
  
