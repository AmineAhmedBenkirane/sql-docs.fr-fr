---
title: "GROUPE de disponibilité ALTER (Transact-SQL) | Documents Microsoft"
ms.custom: 
ms.date: 01/02/2018
ms.prod: sql-non-specified
ms.prod_service: sql-database
ms.service: 
ms.component: t-sql|statements
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ALTER_AVAILABILITY_GROUP_TSQL
- ALTER_AVAILABILITY_TSQL
- ALTER AVAILABILITY GROUP
- ALTER AVAILABILITY
dev_langs: TSQL
helpviewer_keywords:
- Availability Groups [SQL Server], availability replicas
- ALTER AVAILABILITY GROUP statement
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], Transact-SQL statements
ms.assetid: f039d0de-ade7-4aaf-8b7b-d207deb3371a
caps.latest.revision: "152"
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: d9f18ee709fde7c9f239b08f553eaf43fad6e9d2
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="alter-availability-group-transact-sql"></a>ALTER AVAILABILITY GROUP (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Modifie un groupe de disponibilité Always On existant dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. La plupart des arguments ALTER AVAILABILITY GROUP ne sont pris en charge que par le réplica principal actuel. Toutefois, les arguments JOIN, FAILOVER et FORCE_FAILOVER_ALLOW_DATA_LOSS, ne sont pris en charge que sur les réplicas secondaires.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```SQL  
  
ALTER AVAILABILITY GROUP group_name   
  {  
     SET ( <set_option_spec> )   
   | ADD DATABASE database_name   
   | REMOVE DATABASE database_name  
   | ADD REPLICA ON <add_replica_spec>   
   | MODIFY REPLICA ON <modify_replica_spec>  
   | REMOVE REPLICA ON <server_instance>  
   | JOIN  
   | JOIN AVAILABILITY GROUP ON <add_availability_group_spec> [ ,...2 ]  
   | MODIFY AVAILABILITY GROUP ON <modify_availability_group_spec> [ ,...2 ]  
   | GRANT CREATE ANY DATABASE  
   | DENY CREATE ANY DATABASE  
   | FAILOVER  
   | FORCE_FAILOVER_ALLOW_DATA_LOSS   | ADD LISTENER ‘dns_name’ ( <add_listener_option> )  
   | MODIFY LISTENER ‘dns_name’ ( <modify_listener_option> )  
   | RESTART LISTENER ‘dns_name’  
   | REMOVE LISTENER ‘dns_name’  
   | OFFLINE  
  }  
[ ; ]  
  
<set_option_spec> ::=   
    AUTOMATED_BACKUP_PREFERENCE = { PRIMARY | SECONDARY_ONLY| SECONDARY | NONE }  
  | FAILURE_CONDITION_LEVEL  = { 1 | 2 | 3 | 4 | 5 }   
  | HEALTH_CHECK_TIMEOUT = milliseconds  
  | DB_FAILOVER  = { ON | OFF }   
  | REQUIRED_SYNCHRONIZED_SECONDARIES_TO_COMMIT = { integer }
  
<server_instance> ::=   
 { 'system_name[\instance_name]' | 'FCI_network_name[\instance_name]' }  
  
<add_replica_spec>::=  
  <server_instance> WITH  
    (  
       ENDPOINT_URL = 'TCP://system-address:port',  
       AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT | CONFIGURATION_ONLY },  
       FAILOVER_MODE = { AUTOMATIC | MANUAL }   
       [ , <add_replica_option> [ ,...n ] ]  
    )   
  
  <add_replica_option>::=  
       SEEDING_MODE = { AUTOMATIC | MANUAL }   
     | BACKUP_PRIORITY = n  
     | SECONDARY_ROLE ( {   
          ALLOW_CONNECTIONS = { NO | READ_ONLY | ALL }   
        | READ_ONLY_ROUTING_URL = 'TCP://system-address:port'   
          } )  
     | PRIMARY_ROLE ( {   
          ALLOW_CONNECTIONS = { READ_WRITE | ALL }   
        | READ_ONLY_ROUTING_LIST = { ( ‘<server_instance>’ [ ,...n ] ) | NONE }   
          } )  
     | SESSION_TIMEOUT = seconds  
  
<modify_replica_spec>::=  
  <server_instance> WITH  
    (    
       ENDPOINT_URL = 'TCP://system-address:port'   
     | AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }   
     | FAILOVER_MODE = { AUTOMATIC | MANUAL }   
     | SEEDING_MODE = { AUTOMATIC | MANUAL }   
     | BACKUP_PRIORITY = n  
     | SECONDARY_ROLE ( {   
          ALLOW_CONNECTIONS = { NO | READ_ONLY | ALL }   
        | READ_ONLY_ROUTING_URL = 'TCP://system-address:port'   
          } )  
     | PRIMARY_ROLE ( {   
          ALLOW_CONNECTIONS = { READ_WRITE | ALL }   
        | READ_ONLY_ROUTING_LIST = { ( ‘<server_instance>’ [ ,...n ] ) | NONE }   
          } )  
     | SESSION_TIMEOUT = seconds  
    )   
  
<add_availability_group_spec>::=  
 <ag_name> WITH  
    (  
       LISTENER_URL = 'TCP://system-address:port',  
       AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT },  
       FAILOVER_MODE = MANUAL,  
       SEEDING_MODE = { AUTOMATIC | MANUAL }  
    )  
  
<modify_availability_group_spec>::=  
 <ag_name> WITH  
    (  
       LISTENER = 'TCP://system-address:port'  
       | AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }  
       | SEEDING_MODE = { AUTOMATIC | MANUAL }  
    )  
  
<add_listener_option> ::=  
   {  
      WITH DHCP [ ON ( <network_subnet_option> ) ]  
    | WITH IP ( { ( <ip_address_option> ) } [ , ...n ] ) [ , PORT = listener_port ]  
   }  
  
  <network_subnet_option> ::=  
     ‘four_part_ipv4_address’, ‘four_part_ipv4_mask’    
  
  <ip_address_option> ::=  
     {   
        ‘four_part_ipv4_address’, ‘four_part_ipv4_mask’  
      | ‘ipv6_address’  
     }  
  
<modify_listener_option>::=  
    {  
       ADD IP ( <ip_address_option> )   
     | PORT = listener_port  
    }  
  
```  
  
## <a name="arguments"></a>Arguments  
 *group_name*  
 Spécifie le nom du nouveau groupe de disponibilité. *nom_groupe* doit être valide [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] identificateur et il doit être unique parmi tous les groupes de disponibilité dans le cluster WSFC.  
  
 AUTOMATED_BACKUP_PREFERENCE  **=**  {PRINCIPAL | SECONDARY_ONLY | SECONDAIRE | AUCUN}  
 Spécifie une préférence sur la manière dont un travail de sauvegarde doit évaluer le réplica principal lorsqu'on choisit où effectuer des sauvegardes. Vous pouvez écrire un travail de sauvegarde donné pour prendre en compte la préférence de sauvegarde automatisée. Il est important de comprendre que la préférence n’est pas appliquée par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], donc il n’a aucun impact sur les sauvegardes ad hoc.  
  
 Pris en charge uniquement sur le réplica principal.  
  
 Les valeurs sont les suivantes :  
  
 PRIMARY  
 Spécifie que les sauvegardes doivent toujours avoir lieu sur le réplica principal. Cette option est utile si vous avez besoin de fonctionnalités de sauvegarde, telles que la création de sauvegardes différentielles, qui ne sont pas prises en charge lorsque la sauvegarde est exécutée sur un réplica secondaire.  
  
> [!IMPORTANT]  
>  Si vous envisagez d’utiliser la copie de journaux de transaction pour préparer des bases de données secondaires pour un groupe de disponibilité, définissez la préférence de sauvegarde automatisée sur **Principal** jusqu’à ce que toutes les bases de données secondaires aient été préparées et attachées au groupe de disponibilité.  
  
 SECONDARY_ONLY  
 Spécifie que les sauvegardes ne doivent jamais être effectuées sur le réplica principal. Si le réplica principal est le seul réplica en ligne, la sauvegarde ne doit pas avoir lieu.  
  
 SECONDARY  
 Spécifie que les sauvegardes doivent se produire sur un réplica secondaire sauf lorsque le réplica principal est le seul réplica en ligne. Dans ce cas, la sauvegarde doit se produire sur le réplica principal. Il s'agit du comportement par défaut.  
  
 Aucune  
 Spécifie que vous préférez que les travaux de sauvegarde ignorent le rôle des réplicas de disponibilité lorsque vous choisissez le réplica pour effectuer les sauvegardes. Notez que les travaux de sauvegarde peuvent évaluer d'autres facteurs tels que la priorité de sauvegarde de chaque réplica de disponibilité en association avec son état opérationnel et son état connecté.  
  
> [!IMPORTANT]  
>  Il n'y a aucune contrainte du paramètre AUTOMATED_BACKUP_PREFERENCE. La traduction de cette préférence dépend de la logique, le cas échéant, que vous avez écrite dans les travaux de sauvegarde pour les bases de données dans un groupe de disponibilité donné. Le paramètre de préférence de sauvegarde automatisée n’a aucun impact sur les sauvegardes ad hoc. Pour plus d’informations, consultez [configurer la sauvegarde sur les réplicas de disponibilité &#40; SQL Server &#41; ](../../database-engine/availability-groups/windows/configure-backup-on-availability-replicas-sql-server.md).  
  
> [!NOTE]  
>  Pour afficher la préférence de sauvegarde automatisée d’un groupe de disponibilité existant, sélectionnez le **automated_backup_preference** ou **automated_backup_preference_desc** colonne de la [sys.availability_groups](../../relational-databases/system-catalog-views/sys-availability-groups-transact-sql.md) affichage catalogue. En outre, [sys.fn_hadr_backup_is_preferred_replica &#40; Transact-SQL &#41; ](../../relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql.md) peut être utilisé pour déterminer le réplica de sauvegarde par défaut.  Cette fonction renverra toujours 1 pour au moins l'un des réplicas, même avec `AUTOMATED_BACKUP_PREFERENCE = NONE`.  
  
 FAILURE_CONDITION_LEVEL  **=**  {1 | 2 | **3** | 4 | 5}  
 Spécifie les conditions d'échec qui déclencheront un basculement automatique pour ce groupe de disponibilité. FAILURE_CONDITION_LEVEL est défini au niveau du groupe mais s’applique uniquement sur les réplicas de disponibilité qui sont configurés pour le mode de disponibilité à validation synchrone (AVAILIBILITY_MODE  **=**  SYNCHRONOUS_COMMIT). En outre, les conditions d’échec peuvent déclencher un basculement automatique, uniquement si les réplicas principales et secondaire sont configurés pour le mode de basculement automatique (FAILOVER_MODE  **=**  automatique) et le réplica secondaire est actuellement synchronisé avec le réplica principal.  
  
 Pris en charge uniquement sur le réplica principal.  
  
 Les niveaux de condition d'échec (1-5) s'étendent du moins restrictif, niveau 1, au plus restrictif, le niveau 5. Un niveau de condition donné comprend tous les niveaux moins restrictifs. Par conséquent, le niveau de condition le plus strict, le niveau 5, inclut les quatre niveaux de condition moins restrictifs (1 à 4), le niveau 4 inclut les niveaux 1 à 3, et ainsi de suite. Le tableau suivant décrit la condition d'échec qui correspond à chaque niveau.  
  
|Niveau|Condition d'échec|  
|-----------|-----------------------|  
|1|Spécifie qu'un basculement automatique doit être initialisé lorsque l'une des conditions suivantes se produit :<br /><br /> Le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est fermé.<br /><br /> Le bail du groupe de disponibilité pour la connexion au cluster WSFC expire car aucun accusé de réception n'est reçu de l'instance de serveur. Pour plus d’informations, consultez [Fonctionnement : délai d’expiration de bail Always On SQL Server](http://blogs.msdn.com/b/psssql/archive/2012/09/07/how-it-works-sql-server-Always%20On-lease-timeout.aspx).|  
|2|Spécifie qu'un basculement automatique doit être initialisé lorsque l'une des conditions suivantes se produit :<br /><br /> L'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne se connecte pas au cluster et le seuil du groupe de disponibilité HEALTH_CHECK_TIMEOUT spécifié par l'utilisateur est dépassé.<br /><br /> Le réplica de disponibilité est dans un état d'échec.|  
|3|Spécifie qu'un basculement automatique doit être initialisé sur les erreurs internes critiques [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], telles que les verrouillages spinlock orphelins, les violations graves d'accès en écriture, ou en cas de vidages trop importants.<br /><br /> Il s'agit du comportement par défaut.|  
|4|Spécifie qu'un basculement automatique doit être initialisé sur les erreurs internes modérées [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], telles qu'une condition persistante de mémoire insuffisante dans le pool de ressources interne [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].|  
|5|Spécifie qu'un basculement automatique doit être initialisé sur tous les états d'échec qualifiés, notamment :<br /><br /> Insuffisance des threads de travail du moteur SQL.<br /><br /> Détection d'un blocage insoluble.|  
  
> [!NOTE]  
>  Absence de réponse par une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client demandes ne s’applique pas aux groupes de disponibilité.  
  
 Les valeurs de FAILURE_CONDITION_LEVEL et de HEALTH_CHECK_TIMEOUT, définir un *stratégie de basculement flexible* pour un groupe donné. Cette stratégie de basculement souple vous offre un contrôle granulaire sur les conditions qui doivent entraîner un basculement automatique. Pour plus d’informations, consultez [stratégie de basculement Flexible pour le basculement automatique d’un groupe de disponibilité &#40; SQL Server &#41; ](../../database-engine/availability-groups/windows/flexible-automatic-failover-policy-availability-group.md).  
  
 HEALTH_CHECK_TIMEOUT  **=**  *millisecondes*  
 Spécifie le temps d’attente (en millisecondes) pour le [sp_server_diagnostics](../../relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql.md) procédures stockées système pour retourner les informations d’intégrité du serveur avant que le cluster WSFC suppose que l’instance de serveur est lente ou suspendue. HEALTH_CHECK_TIMEOUT est défini au niveau du groupe mais s’applique uniquement sur les réplicas de disponibilité qui sont configurés pour le mode de disponibilité à validation synchrone avec basculement automatique (AVAILIBILITY_MODE  **=**  SYNCHRONOUS_COMMIT).  En outre, d’un délai d’attente de contrôle d’intégrité peut déclencher un basculement automatique uniquement si les réplicas principales et secondaire sont configurés pour le mode de basculement automatique (FAILOVER_MODE  **=**  automatique) et le réplica secondaire est actuellement synchronisé avec le réplica principal.  
  
 La valeur par défaut de HEALTH_CHECK_TIMEOUT est de 30 000 millisecondes (30 secondes). La valeur minimale est 15 000 millisecondes (15 secondes), et la valeur maximale est 4 294 967 295 millisecondes.  
  
 Pris en charge uniquement sur le réplica principal.  
  
> [!IMPORTANT]  
>  **sp_server_diagnostics** n’exécute pas de vérifications d’intégrité au niveau de la base de données.  
  
 DB_FAILOVER  **=**  {ON | {OFF}  
 Indique l’action à entreprendre lorsqu’une base de données sur le réplica principal est hors connexion. Lorsque cette propriété a la valeur ON, n’importe quel état autre que ONLINE pour une base de données dans le groupe de disponibilité déclenche un basculement automatique. Lorsque cette option est définie sur OFF, uniquement l’intégrité de l’instance est utilisée pour déclencher un basculement automatique.  
 
 Pour plus d’informations sur ce paramètre, consultez [Option de détection de base de données au niveau d’intégrité](../../database-engine/availability-groups/windows/sql-server-always-on-database-health-detection-failover-option.md) 

 
 REQUIRED_SYNCHRONIZED_SECONDARIES_TO_COMMIT   
 Introduite dans SQL Server 2017. Utilisé pour définir un nombre minimal de réplicas secondaires synchrones requis pour valider avant que le réplica principal valide une transaction. Garantit que les transactions SQL Server attendra jusqu'à ce que les journaux des transactions sont mis à jour sur le nombre minimal de réplicas secondaires. La valeur par défaut est 0, ce qui donne le même comportement que SQL Server 2016. La valeur minimale est 0. La valeur maximale est le nombre de réplicas moins 1. Cette option se rapporte aux réplicas en mode de validation synchrone. Lorsque les réplicas sont en mode de validation synchrone, les écritures sur le réplica principal patienter jusqu'à ce que les écritures sur les réplicas secondaires synchrones sont validées dans le journal des transactions de base de données réplica. Si un serveur SQL Server qui héberge un réplica synchrone secondaire cesse de répondre, le serveur SQL qui héberge le réplica principal marque ce réplica secondaire non synchronisé et continuer. Lorsque la base de données ne répond pas revient en ligne doivent être dans un état « non synchronisé » et le réplica est marqué comme non intègre jusqu'à ce que le serveur principal peut rendre synchrones à nouveau. Ce paramètre garantit que le réplica principal ne va pas tant que le nombre minimal de réplicas ont validées à chaque transaction. Si le nombre minimal de réplicas n’est pas disponible, est validée sur le serveur principal échoue. Pour le type de cluster `EXTERNAL` le paramètre est modifié lorsque le groupe de disponibilité est ajouté à une ressource de cluster. Consultez [haute disponibilité et protection des données pour les configurations de groupe de disponibilité](../../linux/sql-server-linux-availability-group-ha.md).
  
 Ajouter une base de données *nom_base_de_données*  
 Spécifie une liste d'une ou de plusieurs bases de données utilisateur que vous souhaitez ajouter au groupe de disponibilité. Ces bases de données doivent résider sur l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui héberge le réplica principal actuel. Vous pouvez spécifier plusieurs bases de données pour un groupe de disponibilité, mais chaque base de données ne peut appartenir qu'à un seul groupe de disponibilité. Pour plus d’informations sur le type de bases de données prises en charge par un groupe de disponibilité, consultez [conditions préalables, Restrictions et recommandations pour les groupes de disponibilité AlwaysOn &#40; SQL Server &#41; ](../../database-engine/availability-groups/windows/prereqs-restrictions-recommendations-always-on-availability.md). Pour les bases de données locales appartient déjà à un groupe de disponibilité, consultez le **replica_id** colonne dans la [sys.databases](../../relational-databases/system-catalog-views/sys-databases-transact-sql.md) vue de catalogue.  
  
 Pris en charge uniquement sur le réplica principal.  
  
> [!NOTE]  
>  Après avoir créé le groupe de disponibilité, vous devez vous connecter à chaque instance de serveur qui héberge un réplica secondaire, puis préparer chaque base de données secondaire et la joindre au groupe de disponibilité. Pour plus d’informations, consultez [Démarrer un mouvement de données sur une base de données secondaire Always On &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/start-data-movement-on-an-always-on-secondary-database-sql-server.md).  
  
 SUPPRIMER la base de données *nom_base_de_données*  
 Supprime la base de données primaire spécifiée et les bases de données secondaires correspondantes du groupe de disponibilité. Pris en charge uniquement sur le réplica principal.  
  
 Pour plus d’informations sur le suivi recommandé après la suppression d’une base de données de disponibilité d’un groupe de disponibilité, consultez [supprimer une base de données principal à partir d’un groupe de disponibilité &#40; SQL Server &#41; ](../../database-engine/availability-groups/windows/remove-a-primary-database-from-an-availability-group-sql-server.md).  
  
 ADD REPLICA ON  
 Spécifie de une à huit instances SQL Server pour l'hébergement des réplicas secondaires dans un groupe de disponibilité.  Chaque réplica est spécifié par son adresse d'instance de serveur suivie d'une clause WITH (…).  
  
 Pris en charge uniquement sur le réplica principal.  
  
 Vous devez joindre chaque nouveau réplica secondaire au groupe de disponibilité. Pour plus d'informations, consultez la description de l'option JOIN ultérieurement dans cette section.  
  
 \<server_instance>  
 Spécifie l’adresse de l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui est l’hôte d’un réplica. Le format de l'adresse varie selon que l'instance est l'instance par défaut ou une instance nommée et s'il s'agit d'une instance autonome ou d'une instance de cluster de basculement (FCI). La syntaxe de base est la suivante :  
  
 { '*nom_système*[\\*nom_instance*]' | '*nom_réseau_FCI*[\\*nom_instance*]' }  
  
 Les composants de cette adresse sont les suivants :  
  
 *nom_système*  
 Nom NetBIOS du système informatique sur lequel réside l'instance cible de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Cet ordinateur doit être un nœud WSFC.  
  
 *nom_réseau_FCI*  
 Nom réseau utilisé pour accéder à un cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Utilisez ce nom si l'instance de serveur participe en tant que serveur partenaire de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. L’exécution de SELECT [@@SERVERNAME ](../../t-sql/functions/servername-transact-sql.md) sur une instance de cluster, instance de serveur renvoie son intégralité '*nom_réseau_fci*[\\*nom_instance*]' chaîne (qui est le nom du réplica complet).  
  
 *nom_instance*  
 Est le nom d’une instance d’un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui est hébergé par *nom_système* ou *nom_réseau_fci* et qui a toujours sur activé. Pour une instance de serveur par défaut, *nom_instance* est facultatif. Les noms d'instance ne respectent pas la casse. Sur une instance de serveur autonome, ce nom de la valeur est identique à la valeur retournée par l’exécution de SELECT [@@SERVERNAME](../../t-sql/functions/servername-transact-sql.md).  
  
 \  
 Séparateur utilisé uniquement lors de la spécification *nom_instance*, afin de séparer de *nom_système* ou *nom_réseau_fci*.  
  
 Pour plus d’informations sur la configuration requise pour les nœuds WSFC et les instances de serveur, consultez [conditions préalables, Restrictions et recommandations pour les groupes de disponibilité AlwaysOn &#40; SQL Server &#41; ](../../database-engine/availability-groups/windows/prereqs-restrictions-recommendations-always-on-availability.md).  
  
 ENDPOINT_URL ='TCP : / /*adresse-système*:*port*'  
 Spécifie le chemin d’accès d’URL pour le [point de terminaison de mise en miroir de base de données](../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md) sur l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui hébergera le réplica de disponibilité que vous ajoutez ou modifiez.  
  
 ENDPOINT_URL est requis dans la clause ADD REPLICA ON et est facultatif dans la clause MODIFY REPLICA ON.  Pour plus d’informations, consultez [Spécifiez l’URL du point de terminaison lors de l’ajout ou la modification d’un réplica de disponibilité &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/specify-endpoint-url-adding-or-modifying-availability-replica.md).  
  
 **'**TCP**://***system-address***:***port***'**  
 Spécifie une URL pour spécifier une URL de point de terminaison ou l'URL de routage en lecture seule. Les paramètres d'URL sont les suivants :  
  
 *system-address*  
 Chaîne, telle qu'un nom de système, un nom de domaine complet ou une adresse IP, qui identifie de manière unique l'ordinateur de destination.  
  
 *port*  
 Numéro de port associé au point de terminaison de mise en miroir de l'instance de serveur (pour l'option ENDPOINT_URL) ou numéro de port utilisé par le [!INCLUDE[ssDE](../../includes/ssde-md.md)] de l'instance de serveur (pour l'option READ_ONLY_ROUTING_URL).  
  
 AVAILABILITY_MODE  **=**  {SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT | CONFIGURATION_ONLY}  
 Spécifie si le réplica principal doit attendre le réplica secondaire pour accepter la sécurisation renforcée (écriture) des enregistrements de journal sur le disque avant que le réplica principal puisse valider la transaction sur une base de données principale donnée. Les transactions sur des bases de données différentes sur le même réplica principal peuvent être validées indépendamment.  
  
 SYNCHRONOUS_COMMIT  
 Spécifie que le réplica principal attendra que la sécurité soit renforcée sur les transactions de ce réplica secondaire (mode de validation synchrone) avant de les valider. Vous pouvez spécifier SYNCHRONOUS_COMMIT pour trois réplicas au maximum, y compris le réplica principal.  
  
 ASYNCHRONOUS_COMMIT  
 Spécifie que le réplica principal valide les transactions sans attendre que la sécurité du journal de ce réplica secondaire soit renforcée (mode de disponibilité de validation synchrone). Vous pouvez spécifier ASYNCHRONOUS_COMMIT pour cinq réplicas de disponibilité au maximum, y compris le réplica principal.  

 CONFIGURATION_ONLY Spécifie que le réplica principal synchrone valider les métadonnées de configuration de groupe de disponibilité pour la base de données master sur ce réplica. Le réplica ne contient pas de données utilisateur. Cette option :

- Peut être hébergé sur n’importe quelle édition de SQL Server, y compris Express Edition.
- Exige que les données du réplica CONFIGURATION_ONLY pour être le type de point de terminaison de mise en miroir `WITNESS`.
- Ne peut pas être modifié.
- N’est pas valide lorsque `CLUSTER_TYPE = WSFC`. 

   Pour plus d’informations, consultez [seul réplica de Configuration](../../linux/sql-server-linux-availability-group-ha.md).
    
 AVAILABILITY_MODE est requis dans la clause ADD REPLICA ON et est facultatif dans la clause MODIFY REPLICA ON. Pour plus d’informations, consultez [Modes de disponibilité &#40;groupes de disponibilité Always On&#41;](../../database-engine/availability-groups/windows/availability-modes-always-on-availability-groups.md).  
  
 FAILOVER_MODE  **=**  {AUTOMATIQUE | MANUEL}  
 Spécifie le mode de basculement du réplica de disponibilité que vous définissez.  
  
 AUTOMATIC  
 Active le basculement automatique. AUTOMATIC n'est pris en charge que si vous spécifiez également AVAILABILITY_MODE = SYNCHRONOUS_COMMIT. Vous pouvez spécifier AUTOMATIC pour deux réplicas de disponibilité, y compris le réplica principal.  
  
> [!NOTE]  
>  Les instances de cluster de basculement (FCI) SQL Server ne prennent pas en charge le basculement automatique par les groupes de disponibilité. Par conséquent, tout réplica de disponibilité hébergé par une instance de cluster de basculement ne peut être configuré que pour un basculement manuel.  
  
 MANUAL  
 Permet le basculement manuel ou forcé (*le basculement forcé*) par l’administrateur de base de données.  
  
 FAILOVER_MODE est requis dans la clause ADD REPLICA ON et est facultatif dans la clause MODIFY REPLICA ON. Deux types de basculement manuel existent, le basculement manuel sans perte de données et le basculement forcé (avec perte de données possible) et sont pris en charge dans différentes conditions.  Pour plus d’informations, consultez [Basculement et modes de basculement &#40;groupes de disponibilité Always On&#41;](../../database-engine/availability-groups/windows/failover-and-failover-modes-always-on-availability-groups.md).  
  
 SEEDING_MODE  **=**  {AUTOMATIQUE | MANUEL}  
 Spécifie comment le réplica secondaire est initialement amorcé.  
  
 AUTOMATIC  
 Permet à l’amorçage direct. Cette méthode amorcera le réplica secondaire sur le réseau. Cette méthode ne nécessite pas de sauvegarder et restaurer une copie de la base de données principal sur le réplica.  
  
> [!NOTE]  
>  Pour l’amorçage direct, vous devez autoriser la création de la base de données sur chaque réplica secondaire en appelant **ALTER AVAILABILITY GROUP** avec la **GRANT CREATE ANY DATABASE** option.  
  
 MANUAL  
 Spécifie l’amorçage manuel (par défaut). Cette méthode vous oblige à créer une sauvegarde de la base de données sur le réplica principal et restaurer manuellement cette sauvegarde sur le réplica secondaire.  
  
 BACKUP_PRIORITY **=***n*  
 Spécifie la priorité d'exécution des sauvegardes sur ce réplica par rapport aux autres réplicas dans le même groupe de disponibilité. La valeur est un entier compris entre 0 et 100. Ces valeurs ont les significations suivantes :  
  
-   1..100 indique que le réplica de disponibilité peut être choisi pour effectuer des sauvegardes. 1 indique la priorité la plus faible, 100 la priorité la plus élevée. Si BACKUP_PRIORITY = 1, le réplica de disponibilité est choisi pour l'exécution des sauvegardes uniquement si aucun réplica de disponibilité ayant une priorité plus élevée n'est actuellement disponible.  
  
-   0 indique que ce réplica de disponibilité ne sera jamais choisi pour effectuer des sauvegardes. Cela est utile, par exemple, pour un réplica de disponibilité distant sur lequel vous ne souhaitez jamais basculer de sauvegardes.  
  
 Pour plus d’informations, consultez [Secondaires actifs : sauvegarde sur les réplicas secondaires &#40;groupes de disponibilité Always On&#41;](../../database-engine/availability-groups/windows/active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md).  
  
 SECONDARY_ROLE **(** ... **)**  
 Spécifie des paramètres spécifiques au rôle qui entreront en vigueur si ce réplica de disponibilité a actuellement le rôle secondaire (autrement dit, chaque fois qu'il s'agit d'un réplica secondaire). Entre parenthèses, spécifiez le l'une ou l'autre, ou les deux options de rôle secondaire. Si vous spécifiez les deux, utilisez une liste séparée par des virgules.  
  
 Les options de rôle secondaire sont les suivantes :  
  
 ALLOW_CONNECTIONS  **=**  {NON | READ_ONLY | TOUS LES}  
 Spécifie si les bases de données d'un réplica de disponibilité donné qui joue le rôle secondaire (autrement dit, qui joue le rôle d'un réplica secondaire) peuvent accepter de clients, dont :  
  
 NO  
 Aucune connexion utilisateur n'est autorisée aux bases de données secondaires de ce réplica. Elles ne sont pas disponibles pour l'accès en lecture. Il s'agit du comportement par défaut.  
  
 READ_ONLY  
 Seules les connexions sont autorisées aux bases de données dans le réplica secondaire où la propriété d’intention de l’Application a la valeur **ReadOnly**. Pour plus d'informations sur cette propriété, consultez [Using Connection String Keywords with SQL Server Native Client](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).  
  
 ALL  
 Toutes les connexions sont autorisées aux bases de données dans le réplica secondaire pour un accès en lecture seule.  
  
 Pour plus d’informations, consultez [Secondaires actifs : réplicas secondaires lisibles &#40;groupes de disponibilité Always On&#41;](../../database-engine/availability-groups/windows/active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).  
  
 READ_ONLY_ROUTING_URL **='**TCP**://***system-address***:***port***'**  
 Spécifie l'URL à utiliser pour le routage des demandes de connexion de tentative de lecture à ce réplica de disponibilité. Il s'agit de l'URL sur laquelle le moteur de base de données SQL Server écoute. En général, l'instance par défaut du moteur de base de données SQL Server écoute le port TCP 1433.  
  
 Pour une instance nommée, vous pouvez obtenir le numéro de port en interrogeant le **port** et **type_desc** les colonnes de la [sys.dm_tcp_listener_states](../../relational-databases/system-dynamic-management-views/sys-dm-tcp-listener-states-transact-sql.md) vue de gestion dynamique. L’instance de serveur utilise l’écouteur Transact-SQL (**type_desc = 'TSQL'**).  
  
 Pour plus d’informations sur le calcul de l’URL de routage en lecture seule pour un réplica de disponibilité, consultez [read_only_routing_url de calcul pour Always On](http://blogs.msdn.com/b/mattn/archive/2012/04/25/calculating-read-only-routing-url-for-Always%20On.aspx).  
  
> [!NOTE]  
>  Pour une instance nommée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], l'écouteur Transact-SQL doit être configuré pour utiliser un port spécifique. Pour plus d’informations, consultez [Configurer un serveur pour écouter un port TCP spécifique &#40;Gestionnaire de configuration SQL Server&#41;](../../database-engine/configure-windows/configure-a-server-to-listen-on-a-specific-tcp-port.md).  
  
 PRIMARY_ROLE **(** ... **)**  
 Spécifie des paramètres spécifiques au rôle qui entreront en vigueur si ce réplica de disponibilité a actuellement le rôle principal (autrement dit, chaque fois qu'il s'agit d'un réplica principal). Entre parenthèses, spécifiez le l'une ou l'autre, ou les deux options de rôle principal. Si vous spécifiez les deux, utilisez une liste séparée par des virgules.  
  
 Les options de rôle principal sont les suivantes :  
  
 ALLOW_CONNECTIONS  **=**  {READ_WRITE | TOUS LES}  
 Spécifie le type de connexion que les bases de données d'un réplica de disponibilité donné qui joue le rôle principal (autrement dit, qui joue le rôle d'un réplica principal) peuvent accepter de clients, dont :  
  
 READ_WRITE  
 Les connexions où la propriété de connexion d’intention de l’application a la valeur **ReadOnly** ne sont pas autorisées.  Lorsque la propriété d'intention de l'application a la valeur **ReadWrite** ou si cette propriété n'est pas définie, la connexion est autorisée. Pour plus d'informations sur la propriété de connexion d'intention de l'application, consultez [Using Connection String Keywords with SQL Server Native Client](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).  
  
 ALL  
 Toutes les connexions aux bases de données sont autorisées dans le réplica principal. Il s'agit du comportement par défaut.  
  
 READ_ONLY_ROUTING_LIST  **=**  { **(«**\<instance_serveur >**'** [ **,**... *n* ] **)** | AUCUN}  
 Spécifie une liste séparée par des virgules des instances de serveur qui hébergent les réplicas de disponibilité pour ce groupe de disponibilité qui répondent aux conditions suivantes lors de l'exécution sous le rôle secondaire :  
  
-   Être configurés pour autoriser les connexions ou connexions en lecture seule (voir l'argument ALLOW_CONNECTIONS de l'option de SECONDARY_ROLE, ci-dessus).  
  
-   Disposer de leur URL de routage en lecture seule définie (voir l'argument READ_ONLY_ROUTING_URL de l'option SECONDARY_ROLE, ci-dessus).  
  
 Les valeurs de READ_ONLY_ROUTING_LIST sont les suivantes :  
  
 \<server_instance>  
 Spécifie l'adresse de l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui est l'hôte d'un réplica de disponibilité qui est un réplica secondaire lisible lors de l'exécution sous le rôle secondaire.  
  
 Utilisez une liste séparée par des virgules pour spécifier toutes les instances de serveur qui peuvent héberger un réplica secondaire lisible. Le routage en lecture seule suivra l'ordre dans lequel les instances de serveur sont spécifiées dans la liste. Si vous incluez l'instance de serveur hôte d'un réplica dans la liste de routage en lecture seule du réplica, il est généralement recommandé d'insérer cette instance de serveur à la fin de la liste, afin que les connexions de tentative de lecture soient dirigées vers un réplica secondaire (le cas échéant).  
  
 À partir de [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)], vous pouvez les demandes avec intention de lecture de l’équilibrage de charge entre les réplicas secondaires lisibles. Vous spécifiez cela en plaçant les réplicas dans un jeu imbriqué de parenthèses dans la liste de routage en lecture seule. Pour plus d’informations et d’exemples, consultez [configurer l’équilibrage de charge entre des réplicas en lecture seule](../../database-engine/availability-groups/windows/configure-read-only-routing-for-an-availability-group-sql-server.md#loadbalancing).  
  
 Aucune  
 Spécifie que lorsque ce réplica de disponibilité est le réplica principal, le routage en lecture seule ne sera pas pris en charge. Il s'agit du comportement par défaut. Lorsqu'elle est utilisée avec MODIFY REPLICA ON, cette valeur désactive une liste existante (le cas échéant).  
  
 SESSION_TIMEOUT **= *** secondes*  
 Spécifie le délai d'expiration de la session en secondes. Si vous ne précisez pas de valeur, le délai défini par défaut est 10 secondes. La valeur minimale est de 5 secondes.  
  
> [!IMPORTANT]  
>  Le temps d'attente recommandé est de 10 secondes minimum.  
  
 Pour plus d’informations sur la période d’expiration de session, consultez [vue d’ensemble de groupes de disponibilité AlwaysOn &#40; SQL Server &#41; ](../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md).  
  
 MODIFY REPLICA ON  
 Modifie un réplica du groupe de disponibilité. La liste des réplicas à modifier contient l'adresse de l'instance de serveur et une clause WITH (…) pour chaque réplica.  
  
 Pris en charge uniquement sur le réplica principal.  
  
 REMOVE REPLICA ON  
 Supprime le réplica secondaire spécifié du groupe de disponibilité. Le réplica principal actuel ne peut pas être supprimé d'un groupe de disponibilité. Lorsqu'il est supprimé, le réplica cesse de recevoir des données. Ses bases de données secondaires sont supprimées du groupe de disponibilité et passent à l'état RESTORING.  
  
 Pris en charge uniquement sur le réplica principal.  
  
> [!NOTE]  
>  Si vous supprimez un réplica alors qu'il n'est pas disponible ou qu'il a échoué, lorsqu'il revient en ligne, il n'appartient plus au groupe de disponibilité.  
  
 JOIN  
 Provoque l'hébergement par l'instance de serveur locale d'un réplica secondaire dans le groupe de disponibilité spécifié.  
  
 Pris en charge uniquement sur un réplica secondaire qui n'a pas encore été joint au groupe de disponibilité.  
  
 Pour plus d’informations, consultez [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/join-a-secondary-replica-to-an-availability-group-sql-server.md).  
  
 FAILOVER  
 Initialise un basculement manuel du groupe de disponibilité sur le réplica secondaire auquel vous êtes connecté, sans perte de données. Le réplica sur lequel vous entrez une commande de basculement cible est appelé le.  La cible de basculement assure le rôle principal, récupère sa copie de chaque base de données et les met en ligne en tant que nouvelles bases de données principales. Le réplica principal précédent joue simultanément le rôle secondaire, et ses bases de données deviennent des bases de données secondaires et sont immédiatement suspendues. Éventuellement, ces rôles peuvent être basculés par une série d'échecs.  
  
 Pris en charge uniquement sur un réplica secondaire de validation synchrone qui est actuellement synchronisé avec le réplica principal. Notez que pour qu'un réplica secondaire soit synchronisé, le réplica principal doit également d'exécuter en mode de validation synchrone.  
  
> [!NOTE]  
>  Une commande de basculement est retournée dès que la cible de basculement a accepté la commande. Toutefois, la récupération de la base de données est asynchrone après que le basculement du groupe de disponibilité est terminé.  
  
 Pour plus d’informations sur les limitations, les conditions préalables et recommandations à l’exécution d’un basculement manuel planifié, consultez [effectuer un basculement manuel planifié d’un groupe de disponibilité &#40; SQL Server &#41; ](../../database-engine/availability-groups/windows/perform-a-planned-manual-failover-of-an-availability-group-sql-server.md).  
  
 FORCE_FAILOVER_ALLOW_DATA_LOSS  
 > [!CAUTION]  
>  Forcer un basculement peut entraîner une perte de données et est à proprement parler une méthode de récupération après sinistre. Par conséquent, nous vous recommandons fortement de forcer le basculement uniquement si le réplica principal n'est plus exécuté, si vous êtes prêt à prendre le risque de perdre des données et si vous devez restaurer immédiatement le service dans le groupe de disponibilité.  
  
 Pris en chrage uniquement sur un réplica dont le rôle est dans l'état SECONDARY ou RESOLVING. Le réplica sur lequel vous entrez une commande de basculement est appelé le *cible de basculement*.  
  
 Force le basculement du groupe de disponibilité (avec possible perte de données) vers la cible de basculement. La cible de basculement assure le rôle principal, récupère sa copie de chaque base de données et les met en ligne en tant que nouvelles bases de données principales. Sur tous les réplicas secondaires restants, chaque base de données secondaire est suspendue jusqu'à ce qu'elle soit reprise manuellement. Lorsque le réplica principal précédent est disponible, il bascule sur le rôle secondaire, et ses bases de données deviennent des bases de données secondaires suspendues.  
  
> [!NOTE]  
>  Une commande de basculement est retournée dès que la cible de basculement a accepté la commande. Toutefois, la récupération de la base de données est asynchrone après que le basculement du groupe de disponibilité est terminé.  
  
 Pour plus d’informations sur les limitations, les conditions préalables et recommandations pour forcer le basculement et l’effet d’un basculement forcé sur les anciennes bases de données primaires dans le groupe de disponibilité, consultez [effectuer un basculement manuel forcé d’un groupe de disponibilité &#40; SQL Server &#41; ](../../database-engine/availability-groups/windows/perform-a-forced-manual-failover-of-an-availability-group-sql-server.md).  
  
 ADD LISTENER **‘***dns_name***’(** \<add_listener_option> **)**  
 Définit un nouvel écouteur de groupe de disponibilité pour ce groupe de disponibilité. Pris en charge uniquement sur le réplica principal.  
  
> [!IMPORTANT]  
>  Avant de créer votre premier écouteur, nous recommandons fortement de lire [créer ou configurer un écouteur de groupe de disponibilité &#40; SQL Server &#41; ](../../database-engine/availability-groups/windows/create-or-configure-an-availability-group-listener-sql-server.md).  
>   
>  Après avoir créé un écouteur pour un groupe de disponibilité spécifique, nous vous recommandons fortement de procéder comme suit :  
>   
>  -   Demandez à votre administrateur réseau de réserver l'adresse IP de l'écouteur pour son utilisation exclusive.  
> -   Fournissez le nom d'hôte DNS de l'écouteur aux développeurs d'applications pour qu'ils l'utilisent dans les chaînes de connexion lorsqu'ils demandent des connexions clientes vers ce groupe de disponibilité.  
  
 *dns_name*  
 Spécifie le nom d'hôte DNS de l'écouteur du groupe de disponibilité. Le nom DNS de l'écouteur doit être unique dans le domaine et dans NetBIOS.  
  
 *nom_DNS* est une valeur de chaîne. Ce nom ne peut contenir que des caractères alphanumériques, des tirets (-) et des caractères de soulignement (_), dans n'importe quel ordre. Les noms d'hôte DNS ne respectent pas la casse. La longueur maximale autorisée est de 63 caractères.  
  
 Nous vous recommandons de spécifier une chaîne explicite. Par exemple, pour un groupe de disponibilité nommé `AG1`, un nom d'hôte DNS explicite est `ag1-listener`.  
  
> [!IMPORTANT]  
>  NetBIOS identifie les 15 premiers caractères du nom_dns. Si vous avez deux clusters WSFC qui sont contrôlés par le même annuaire Active Directory et que vous tentez de créer des écouteurs de groupe de disponibilité dans les deux clusters à l'aide de noms contenant plus de 15 caractères et un préfixe identique de 15 caractères, vous obtenez une erreur signalant que la ressource de nom de réseau virtuel ne peut pas être mise en ligne. Pour plus d'informations sur les règles de préfixe des noms DNS, consultez [Attribution de noms de domaine](http://technet.microsoft.com/library/cc731265\(WS.10\).aspx).  
  
 JOINDRE UN GROUPE DE DISPONIBILITÉ  
 Joint à un *groupe de disponibilité distribué*. Lorsque vous créez un groupe de disponibilité distribué, le groupe de disponibilité sur le cluster sur lequel il est créé est le groupe de disponibilité principal. Le groupe de disponibilité qui rejoint le groupe de disponibilité distribué est le groupe de disponibilité secondaire.  
  
 \<ag_name>  
 Spécifie le nom du groupe de disponibilité qui constitue une partie du groupe de disponibilité distribués.  
  
 ÉCOUTEUR **='**TCP**://***adresse-système***:***port***'**  
 Spécifie le chemin d’accès de l’URL de l’écouteur associé au groupe de disponibilité.  
  
 La clause de l’écouteur est obligatoire.  
  
 **'**TCP**://***system-address***:***port***'**  
 Spécifie une URL de l’écouteur associé au groupe de disponibilité. Les paramètres d'URL sont les suivants :  
  
 *system-address*  
 Est une chaîne, comme un nom système, un nom de domaine complet ou une adresse IP, qui identifie sans ambiguïté l’écouteur.  
  
 *port*  
 Est un numéro de port qui est associé au point de terminaison de mise en miroir du groupe de disponibilité. Notez que cela n’est pas le port de l’écouteur.  
  
 AVAILABILITY_MODE  **=**  {SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT}  
 Spécifie si le réplica principal se trouve en attente pour le groupe de disponibilité secondaire accepter la sécurisation renforcée (écriture) des enregistrements de journal sur le disque avant que le réplica principal peut valider la transaction sur une base de données primaire.  
  
 SYNCHRONOUS_COMMIT  
 Spécifie que le réplica principal attend pour valider des transactions jusqu'à ce qu’ils ont été renforcés sur le groupe de disponibilité secondaire. Vous pouvez spécifier SYNCHRONOUS_COMMIT pour les deux groupes de disponibilité, y compris le groupe de disponibilité principal.  
  
 ASYNCHRONOUS_COMMIT  
 Spécifie que le réplica principal valide les transactions sans attendre que ce groupe de disponibilité secondaire renforce le journal. Vous pouvez spécifier ASYNCHRONOUS_COMMIT pour les deux groupes de disponibilité, y compris le groupe de disponibilité principal.  
  
 La clause AVAILABILITY_MODE est obligatoire.  
  
 FAILOVER_MODE  **=**  {MANUEL}  
 Spécifie le mode de basculement du groupe de disponibilité distribués.  
  
 MANUAL  
 Active le basculement manuel planifié ou le basculement manuel forcé (généralement appelé *le basculement forcé*) par l’administrateur de base de données.  
  
 Le basculement automatique vers le groupe de disponibilité secondaire n’est pas pris en charge.  
  
 SEEDING_MODE **=**  {AUTOMATIQUE | MANUEL}  
 Spécifie la façon dont le groupe de disponibilité secondaire est initialement amorcé.  
  
 AUTOMATIC  
 Active l’amorçage automatique. Cette méthode amorcera le groupe de disponibilité secondaire sur le réseau. Cette méthode ne nécessite pas de sauvegarder et restaurer une copie de la base de données principal sur les réplicas du groupe de disponibilité secondaire.  
  
 MANUAL  
 Spécifie un amorçage manuel. Cette méthode vous oblige à créer une sauvegarde de la base de données sur le réplica principal et restaurer manuellement cette sauvegarde sur l’ou les réplicas du groupe de disponibilité secondaire.  
  
 MODIFIER LE GROUPE DE DISPONIBILITÉ SUR  
 Modifie les paramètres de groupe de disponibilité d’un groupe de disponibilité distribué. La liste des groupes de disponibilité à modifier contient le nom de groupe de disponibilité et de WITH clause (...) pour chaque groupe de disponibilité.  
  
> [!IMPORTANT]  
>  Cette commande doit être répétée sur le groupe de disponibilité principal et les instances de groupe de disponibilité secondaire.  
  
 GRANT CREATE ANY DATABASE  
 Autorise le groupe de disponibilité pour créer des bases de données pour le compte du réplica principal, qui prend en charge l’amorçage direct (SEEDING_MODE = AUTOMATIC). Ce paramètre doit être exécuté sur chaque réplica secondaire qui prend en charge l’amorçage direct après que cette base de données secondaire joint le groupe de disponibilité.  Requiert l’autorisation CREATE ANY DATABASE.  
  
 REFUSER CRÉER UNE BASE DE DONNÉES  
 Supprime la possibilité de créer des bases de données pour le compte le réplica principal du groupe de disponibilité.  
  
 \<add_listener_option>  
 ADD LISTENER prend l'une des options suivantes :  
  
 AVEC le protocole DHCP [ON { **(«***four_part_ipv4_address***','***four_part_ipv4_mask***')** }]  
 Spécifie que l'écouteur du groupe de disponibilité utilise le protocole DHCP (Dynamic Host Configuration Protocol).  Utilisez éventuellement la clause ON pour identifier le réseau sur lequel cet écouteur sera créé. DHCP est limité à un seul sous-réseau utilisé pour chaque instance de serveur qui héberge un réplica de disponibilité dans le groupe de disponibilité.  
  
> [!IMPORTANT]  
>  Nous vous déconseillons d'utiliser DHCP dans un environnement de production. Lorsqu'un temps mort se produit et que le bail IP DHCP arrive à expiration, une période de temps supplémentaire est requise pour enregistrer la nouvelle adresse IP de réseau DHCP associée au nom DNS de l'écouteur et cela a un impact sur la connectivité client. Toutefois, DHCP peut tout à fait être utilisé pour configurer un environnement de développement et de test dans le but de vérifier les fonctions de base des groupes de disponibilité et l'intégration avec vos applications.  
  
 Par exemple :  
  
 `WITH DHCP ON ('10.120.19.0','255.255.254.0')`  
  
 AVEC IP **(** { **(«***four_part_ipv4_address***','***four_part_ipv4_mask***')** | **(«***ipv6_address***')** } [ **,** ...  *n*  ] **)** [ **,** PORT **= *** listener_port* ]  
 Spécifie que l'écouteur du groupe de disponibilité utilisera une ou plusieurs adresses IP statiques au lieu d'utiliser DHCP. Pour créer un groupe de service sur plusieurs sous-réseaux, chaque sous-réseau requiert une adresse IP statique dans la configuration de l'écouteur. Pour un sous-réseau donné, l'adresse IP statique peut être une adresse IPv4 ou une adresse IPv6. Contactez votre administrateur réseau pour obtenir une adresse IP statique pour chaque sous-réseau qui hébergera un réplica de disponibilité pour le nouveau groupe de disponibilité.  
  
 Par exemple :  
  
 `WITH IP ( ('10.120.19.155','255.255.254.0') )`  
  
 *four_part_ipv4_address*  
 Spécifie une adresse IPv4 en quatre parties pour un écouteur du groupe de disponibilité. Par exemple, `10.120.19.155`.  
  
 *four_part_ipv4_mask*  
 Spécifie un masque IPv4 en quatre parties pour un écouteur du groupe de disponibilité. Par exemple, `255.255.254.0`.  
  
 *ipv6_address*  
 Spécifie une adresse IPv6 pour un écouteur du groupe de disponibilité. Par exemple, `2001::4898:23:1002:20f:1fff:feff:b3a3`.  
  
 PORT **=** *listener_port*  
 Spécifie le numéro de port :*listener_port*: à utiliser par un écouteur de groupe de disponibilité qui est spécifié par la clause WITH IP. Le PORT est facultatif.  
  
 Le numéro de port par défaut est 1433. Toutefois, si vous avez des problèmes de sécurité, nous vous recommandons d'utiliser un numéro de port différent.  
  
 Par exemple : `WITH IP ( ('2001::4898:23:1002:20f:1fff:feff:b3a3') ) , PORT = 7777`  
  
 MODIFY LISTENER **‘***dns_name***’(** \<modify_listener_option> **)**  
 Modifie un écouteur du groupe de disponibilité existant pour ce groupe de disponibilité. Pris en charge uniquement sur le réplica principal.  
  
 \<modify_listener_option>  
 MODIFY LISTENER prend l'une des options suivantes :  
  
 Ajouter IP { **(«***four_part_ipv4_address***','***four_part_ipv4_mask***')** | **(«**nom_DNS*ipv6_ Address***')**}  
 Ajoute l’adresse IP spécifiée à l’écouteur de groupe de disponibilité spécifié par *nom_DNS*.  
  
 PORT **=** *listener_port*  
 Une description de cet argument est fournie plus haut dans cette section.  
  
 REDÉMARRER un écouteur **'***nom_DNS***'**  
 Redémarre l'écouteur associé au nom DNS spécifié. Pris en charge uniquement sur le réplica principal.  
  
 SUPPRIMER l’écouteur **'***nom_DNS***'**  
 Supprime l'écouteur associé au nom DNS spécifié. Pris en charge uniquement sur le réplica principal.  
  
 OFFLINE  
 Place un groupe de disponibilité hors connexion. Il n'y a aucune perte de données des bases de données avec validation synchrone.  
  
 Après qu'un groupe de disponibilité a été mis hors connexion, ses bases de données deviennent indisponibles pour les clients et vous ne pouvez pas remettre le groupe de disponibilité en ligne. Par conséquent, utilisez l'option OFFLINE uniquement pendant une migration entre clusters de [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], lorsque vous migrez des ressources du groupe de disponibilité vers un nouveau cluster WSFC.  
  
 Pour plus d’informations, consultez [placer un groupe de disponibilité hors connexion &#40; SQL Server &#41; ](../../database-engine/availability-groups/windows/take-an-availability-group-offline-sql-server.md).  
  
## <a name="prerequisites-and-restrictions"></a>Conditions préalables requises et restrictions  
 Pour plus d’informations sur les conditions préalables et restrictions sur les réplicas de disponibilité et sur leurs ordinateurs et les instances de serveur hôte, consultez [conditions préalables, Restrictions et recommandations pour les groupes de disponibilité AlwaysOn &#40; SQL Server &#41; ](../../database-engine/availability-groups/windows/prereqs-restrictions-recommendations-always-on-availability.md).  
  
 Pour plus d’informations sur les restrictions sur les instructions Transact-SQL AVAILABILITY GROUP, consultez [vue d’ensemble d’instructions Transact-SQL pour les groupes de disponibilité AlwaysOn &#40; SQL Server &#41; ](../../database-engine/availability-groups/windows/transact-sql-statements-for-always-on-availability-groups.md).  
  
## <a name="security"></a>Sécurité  
  
### <a name="permissions"></a>Autorisations  
 Requiert l'autorisation ALTER AVAILABILITY GROUP sur le groupe de disponibilité, l'autorisation CONTROL AVAILABILITY GROUP, l'autorisation ALTER ANY AVAILABILITY GROUP ou l'autorisation CONTROL SERVER.  Requiert également l’autorisation ALTER ANY DATABASE.   
  
## <a name="examples"></a>Exemples  
  
###  <a name="Join_Secondary_Replica"></a> A. Jointure d'un réplica secondaire à un groupe de disponibilité  
 L’exemple suivant joint un réplica secondaire auquel vous êtes connecté à le `AccountsAG` groupe de disponibilité.  
  
```SQL  
ALTER AVAILABILITY GROUP AccountsAG JOIN;  
GO  
```  
  
###  <a name="Force_Failover"></a> B. Forcer le basculement d'un groupe de disponibilité  
 L'exemple suivant force le basculement du groupe de disponibilité `AccountsAG` sur le réplica secondaire auquel vous êtes connecté.  
  
```SQL
ALTER AVAILABILITY GROUP AccountsAG FORCE_FAILOVER_ALLOW_DATA_LOSS;  
GO  
```  
  
## <a name="see-also"></a>Voir aussi  
 [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](../../t-sql/statements/create-availability-group-transact-sql.md)   
 [ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql-set-hadr.md)   
 [GROUPE de disponibilité &#40; Transact-SQL &#41;](../../t-sql/statements/drop-availability-group-transact-sql.md)   
 [sys.availability_replicas &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-availability-replicas-transact-sql.md)   
 [sys.availability_groups &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-availability-groups-transact-sql.md)   
 [Résoudre les problèmes toujours sur la Configuration des groupes de disponibilité &#40; SQL Server &#41;](../../database-engine/availability-groups/windows/troubleshoot-always-on-availability-groups-configuration-sql-server.md)   
 [Vue d’ensemble des groupes de disponibilité Always On &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)   
 [Écouteurs de groupe de disponibilité, connectivité Client et basculement d’Application &#40; SQL Server &#41;](../../database-engine/availability-groups/windows/listeners-client-connectivity-application-failover.md)  
  
  
