---
title: "CRÉER le POOL de ressources (Transact-SQL) | Documents Microsoft"
ms.custom: 
ms.date: 08/10/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- CREATE RESOURCE POOL
- RESOURCE POOL
- CREATE_RESOURCE_POOL_TSQL
- RESOURCE_POOL_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- CREATE RESOURCE POOL
ms.assetid: 82712505-c6f9-4a65-a469-f029b5a2d6cd
caps.latest.revision: 42
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 5c6f9a6ae8f0f869eb5ddd32c0189fcbaab198d3
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="create-resource-pool-transact-sql"></a>CREATE RESOURCE POOL (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Crée un pool de ressources du gouverneur de ressources dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Un gouverneur de ressources représente un sous-ensemble des ressources physiques (mémoire, UC et E/S) d'une instance du moteur de base de données. Le Gouverneur de ressources permet à un administrateur de base de données de répartir des ressources serveur entre plusieurs pools de ressources (64 pools au maximum). Le gouverneur de ressources n'est pas disponible dans toutes les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Pour obtenir la liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [Fonctionnalités prise en charge par les éditions de SQL Server 2016](~/sql-server/editions-and-supported-features-for-sql-server-2016.md).  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "icône lien de rubrique") [Conventions de syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
CREATE RESOURCE POOL pool_name  
[ WITH  
    (  
        [ MIN_CPU_PERCENT = value ]  
        [ [ , ] MAX_CPU_PERCENT = value ]   
        [ [ , ] CAP_CPU_PERCENT = value ]   
        [ [ , ] AFFINITY {SCHEDULER =  
                  AUTO 
                | ( <scheduler_range_spec> )   
                | NUMANODE = ( <NUMA_node_range_spec> )
                } ]   
        [ [ , ] MIN_MEMORY_PERCENT = value ]  
        [ [ , ] MAX_MEMORY_PERCENT = value ]  
        [ [ , ] MIN_IOPS_PER_VOLUME = value ]  
        [ [ , ] MAX_IOPS_PER_VOLUME = value ]  
    )   
]  
[;]  
  
<scheduler_range_spec> ::=  
{ SCHED_ID | SCHED_ID TO SCHED_ID }[,…n]  
  
<NUMA_node_range_spec> ::=  
{ NUMA_node_ID | NUMA_node_ID TO NUMA_node_ID }[,…n]  
```  
  
## <a name="arguments"></a>Arguments  
 *nom du pool*  
 Nom défini par l'utilisateur du pool de ressources. *pool_name* est alphanumérique, peut contenir jusqu'à 128 caractères, doit être unique au sein d’une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]et doivent respecter les règles pour [identificateurs](../../relational-databases/databases/database-identifiers.md).  
  
 MIN_CPU_PERCENT =*valeur*  
 Spécifie la bande passante de l'UC moyenne garantie pour toutes les demandes dans le pool de ressources en cas de contention de l'UC. *valeur* est un entier dont la valeur par défaut 0. La plage autorisée pour *valeur* est comprise entre 0 et 100.  
  
 MAX_CPU_PERCENT =*valeur*  
 Spécifie la processeur bande passante moyenne maximale que toutes les demandes dans le pool de ressources recevront en cas de contention du processeur. *valeur* est un entier dont le paramètre par défaut est 100. La plage autorisée pour *valeur* est comprise entre 1 et 100.  
  
 CAP_CPU_PERCENT =*valeur*  
 **S'applique à**: [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] et [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 Spécifie une limite maximale d'utilisation fixe sur la bande passante de l'UC que toutes les demandes dans le pool de ressources recevront. Limite le niveau de la bande passante maximum de l'UC pour qu'il soit identique à la valeur spécifiée. *valeur* est un entier dont le paramètre par défaut est 100. La plage autorisée pour *valeur* est comprise entre 1 et 100.  
  
 AFFINITÉ {PLANIFICATEUR = AUTO | ( \<scheduler_range_spec >) | NUMANODE = (\<NUMA_node_range_spec >)} **s’applique aux**: [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] via [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 Attache le pool de ressources aux planificateurs spécifiques. La valeur par défaut est AUTO.  
  
 AFFINITY SCHEDULER = **(** \<scheduler_range_spec > **)** mappe le pool de ressources pour le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] planifications identifiées par l’ID donnés. Ces ID mappage aux valeurs dans la colonne scheduler_id [sys.dm_os_schedulers &#40; Transact-SQL &#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-os-schedulers-transact-sql.md). 
  
 Lorsque vous utilisez AFFINITY NUMANODE = **(** \<NUMA_node_range_spec > **)**, le pool de ressources est possède une affinité avec le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] planificateurs qui mappent aux UC physiques correspondant au nœud NUMA donné ou de la plage de nœuds. Vous pouvez utiliser la requête [!INCLUDE[tsql](../../includes/tsql-md.md)] ci-après pour découvrir le mappage entre la configuration NUMA physique et les ID du planificateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. 
  
```  
SELECT osn.memory_node_id AS [numa_node_id], sc.cpu_id, sc.scheduler_id  
FROM sys.dm_os_nodes AS osn  
INNER JOIN sys.dm_os_schedulers AS sc   
    ON osn.node_id = sc.parent_node_id   
    AND sc.scheduler_id < 1048576;  
```  
  
 MIN_MEMORY_PERCENT =*valeur*  
 Spécifie la quantité de mémoire minimale réservée à ce pool de ressources qui ne peut pas être partagée avec d'autres pools de ressources. *valeur* est un entier dont la valeur par défaut 0 la plage autorisée pour *valeur* est comprise entre 0 et 100.  
  
 MAX_MEMORY_PERCENT =*valeur*  
 Spécifie la mémoire totale du serveur qui peut être utilisée par les demandes dans ce pool de ressources. *valeur* est un entier dont le paramètre par défaut est 100. La plage autorisée pour *valeur* est comprise entre 1 et 100.  
  
 MIN_IOPS_PER_VOLUME =*valeur*  
 **S'applique à**: [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] et [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 Spécifie les opérations d'E/S minimales par seconde (IOPS) par volume disque à réserver au pool de ressources. La plage autorisée pour *valeur* est comprise entre 0 et 2 ^ 31-1 (2 147 483 647). Spécifiez 0 pour indiquer l'absence de seuil minimal pour le pool. La valeur par défaut est 0.  
  
 MAX_IOPS_PER_VOLUME =*valeur*  
 **S'applique à**: [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] et [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 Spécifie les opérations d'E/S maximales par seconde (IOPS) par volume disque à autoriser pour le pool de ressources. La plage autorisée pour *valeur* est comprise entre 0 et 2 ^ 31-1 (2 147 483 647). Spécifiez 0 pour définir un seuil illimité pour le pool. La valeur par défaut est 0.  
  
 Si le MAX_IOPS_PER_VOLUME pour un pool a la valeur 0, le pool n'est pas régi du tout et peut prendre toutes les E/S par seconde dans le système même si MIN_IOPS_PER_VOLUME est défini pour d'autres pools. Dans ce cas, nous vous recommandons de définir la valeur MAX_IOPS_PER_VOLUME de ce pool sur un nombre élevé (par exemple, la valeur maximale 2^31-1) si vous voulez que ce pool soit régi pour les E/S.  
  
## <a name="remarks"></a>Notes  
 MIN_IOPS_PER_VOLUME et MAX_IOPS_PER_VOLUME spécifie les lectures ou écritures minimales et maximales par seconde. Ces lectures ou écritures peuvent être de toute taille et n'indiquent pas un débit minimal ou maximal.  
  
 Les valeurs de MAX_CPU_PERCENT et MAX_MEMORY_PERCENT doivent être supérieures ou égales aux valeurs de MIN_CPU_PERCENT et MIN_MEMORY_PERCENT, respectivement.  
  
 CAP_CPU_PERCENT diffère de MAX_CPU_PERCENT car les charges de travail associées au pool peuvent utiliser la capacité de l'UC au-dessus de la valeur MAX_CPU_PERCENT si elle est disponible, mais pas au-dessus de la valeur CAP_CPU_PERCENT.  
  
 Le pourcentage de l'UC total pour chaque composant d'affinité (planificateur(s) ou nœud(s) NUMA) ne doit pas dépasser 100 %.  
  
## <a name="permissions"></a>Permissions  
 Requiert l'autorisation CONTROL SERVER.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant montre comment créer un pool de ressources appelé `bigPool`. Ce pool utilise les paramètres par défaut du gouverneur de ressources.  
  
```  
CREATE RESOURCE POOL bigPool;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
 Dans l'exemple suivant, `CAP_CPU_PERCENT` est défini avec une limite maximale d'utilisation fixe de 30 % et `AFFINITY SCHEDULER` a pour valeur une plage de 0 à 63 et de 128 à 191. 
  
**S'applique à**: [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] et [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
```  
CREATE RESOURCE POOL PoolAdmin  
WITH (  
     MIN_CPU_PERCENT = 10,  
     MAX_CPU_PERCENT = 20,  
     CAP_CPU_PERCENT = 30,  
     AFFINITY SCHEDULER = (0 TO 63, 128 TO 191),  
     MIN_MEMORY_PERCENT = 5,  
     MAX_MEMORY_PERCENT = 15  
      );  
  
```  
  
 L’exemple suivant définit `MIN_IOPS_PER_VOLUME` à \<une valeur > et `MAX_IOPS_PER_VOLUME` à \<une valeur >. Ces valeurs déterminent les opérations de lecture et d'écriture d'E/S physiques disponibles pour le pool de ressources.  
  
**S'applique à**: [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] et [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
```  
CREATE RESOURCE POOL PoolAdmin  
WITH (  
    MIN_IOPS_PER_VOLUME = 20,  
    MAX_IOPS_PER_VOLUME = 100  
      );  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [ALTER RESOURCE POOL &#40;Transact-SQL&#41;](../../t-sql/statements/alter-resource-pool-transact-sql.md)   
 [DROP RESOURCE POOL &#40;Transact-SQL&#41;](../../t-sql/statements/drop-resource-pool-transact-sql.md)   
 [CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](../../t-sql/statements/create-workload-group-transact-sql.md)   
 [ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](../../t-sql/statements/alter-workload-group-transact-sql.md)   
 [DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](../../t-sql/statements/drop-workload-group-transact-sql.md)   
 [ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](../../t-sql/statements/alter-resource-governor-transact-sql.md)   
 [Pool de ressources de Resource Governor](../../relational-databases/resource-governor/resource-governor-resource-pool.md)   
 [Créer un pool de ressources](../../relational-databases/resource-governor/create-a-resource-pool.md)  
  
  


