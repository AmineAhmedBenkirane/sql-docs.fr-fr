---
title: SQL Server, objet Resource Pool Stats | Microsoft Docs
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Reosurce Pool Stats object
- 'SQLServer: Resource Pool Stats object'
ms.assetid: bb46e029-fcf9-4aeb-a066-be41e7668fb9
caps.latest.revision: 14
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 1ccd649e92cd416ff086758005f3b5df728dfe1d
ms.contentlocale: fr-fr
ms.lasthandoff: 06/22/2017

---
# <a name="sql-server-resource-pool-stats-object"></a>SQLServer, objet Statistiques des pools de ressources
  L'objet SQLServer:Resource Pool Stat contient des compteurs de performance qui créent des rapports d'information sur les statistiques du pool des ressources de Resource Governor.  
  
 Chaque pool de ressources actif crée une instance de l'objet de performance SQLServer : Statistiques des pools de ressources (SQLServer:Resource Pool Stats) ayant le même nom d'instance que le nom du pool de ressources de Resource Governor. Le tableau suivant décrit les compteurs pris en charge sur cette instance.  
  
|Nom du compteur|Description|  
|------------------|-----------------|  
|**Quantité d'allocation de mémoire active (Ko)**|Quantité totale de mémoire actuellement allouée, en kilo-octets (Ko). Ces informations sont également disponibles dans [sys.dm_exec_query_resource_semaphores](../../relational-databases/system-dynamic-management-views/sys-dm-exec-query-resource-semaphores-transact-sql.md).| 
|**Nombre d'allocations de mémoire actives**|Nombre total actuel d'allocations de mémoire. Ces informations sont également disponibles dans [sys.dm_exec_query_memory_grants](../../relational-databases/system-dynamic-management-views/sys-dm-exec-query-memory-grants-transact-sql.md).|  
|**Millisecondes moyennes par lecture depuis le disque**|Durée moyenne, en millisecondes, d'une opération de lecture sur le disque.|  
|**Base d’E/S de lecture sur le disque moy. (ms)**|À usage interne uniquement|
|**Millisecondes moyennes par écriture sur le disque**|Durée moyenne, en millisecondes, d'une opération d'écriture sur le disque.|  
|**Base d’E/S d’écriture sur le disque moy. (ms)**|À usage interne uniquement|
|**Cible mémoire pour le cache (Ko)**|Cible gestionnaire d'allocation mémoire actuelle, en kilo-octets (Ko), pour le cache.|  
|**Cible mémoire pour la compilation (Ko)**|Cible gestionnaire d'allocation mémoire actuelle, en kilo-octets (Ko), pour les compilations de requête.|  
|**% d'effet de contrôle de l'UC**|Effet de Resource Governor sur le pool de ressources. Calculé selon la formule (% d'utilisation de l'UC) / (% d'utilisation de l'UC sans Resource Governor).|  
|**% processeur retardé**|UC du système retardée pour toutes les demandes dans l’instance spécifiée de l’objet de performance, en pourcentage de la durée active totale.|
|**Base de % processeur retardé**|À usage interne uniquement|
|**% processeur effectif**|Utilisation de l’UC système par toutes les demandes dans l’instance spécifiée de l’objet de performance, en pourcentage de la durée active totale.|
|**Base de % processeur effectif**|À usage interne uniquement|
|**% d'utilisation de l'UC**|Utilisation de la bande passante de l'UC sur toutes les demandes dans tous les groupes de charges de travail qui appartiennent à ce pool. Elle est mesurée en fonction de l'ordinateur et normalisée à tous les processeurs du système. Cette valeur se modifie selon la quantité d'UC disponible pour le processus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Elle n'est pas normalisée par rapport à ce que reçoit le processus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .|  
|**Base de % utilisation processeur**|À usage interne uniquement|
|**% cible de l'utilisation de l'UC**|Valeur cible du pourcentage d'utilisation de l'UC pour le pool de ressources basée sur les paramètres de configuration du pool de ressources et de la charge du système.|  
|**% non respecté**|Différence entre la réservation de l’UC et le pourcentage de planification effective.|
|**Octets lus depuis le disque par seconde**|Nombre d'octets lus à partir du disque au cours de la dernière seconde.|  
|**E/S de lecture sur le disque limitées par seconde**|Nombre d'opérations de lecture limitées au cours de la dernière seconde.|  
|**E/S de lecture sur le disque par seconde**|Nombre d'opérations de lecture à partir du disque au cours de la dernière seconde.| 
|**Octets écrits sur le disque par seconde**|Nombre d'octets écrits sur le disque au cours de la dernière seconde.|  
|**E/S d'écriture sur le disque limitées par seconde**|Nombre d'opérations d'écriture limitées au cours de la dernière seconde.| 
|**E/S d'écriture sur le disque par seconde**|Nombre d'opérations d'écriture sur le disque au cours de la dernière seconde.|
|**Mémoire max. (Ko)**|Quantité maximale, en kilo-octets (Ko), de mémoire dont peut disposer le pool de ressources selon les paramètres du pool de ressources et l'état du serveur.| 
|**Délais d'expiration des allocations de mémoire/s**|Nombre de délais d'expiration des allocations de mémoire par seconde.|
|**Allocations de mémoire/s**|Nombre d'allocations de mémoire qui se produisent dans ce pool de ressources par seconde.| 
|**Nombre d'allocations de mémoire en attente**|Nombre de demandes pour les allocations de mémoire en attente dans les files d'attente. Ces informations sont également disponibles dans [sys.dm_exec_query_resource_semaphores](../../relational-databases/system-dynamic-management-views/sys-dm-exec-query-resource-semaphores-transact-sql.md).|
|**Cible mémoire pour l'exécution de requêtes (Ko)**|Cible gestionnaire d'allocation mémoire actuelle, en kilo-octets (Ko), pour l'allocation mémoire de l'exécution de requête. Ces informations sont également disponibles dans [sys.dm_exec_query_memory_grants](../../relational-databases/system-dynamic-management-views/sys-dm-exec-query-memory-grants-transact-sql.md).|  
|**Mémoire cible (Ko)**|Quantité cible, en kilo-octets (Ko), de mémoire que le pool de ressources tente d'obtenir selon les paramètres du pool de ressources et l'état du serveur.|   
|**Mémoire utilisée (Ko)**|Quantité de mémoire utilisée, en kilo-octets (Ko), pour le pool de ressources.|  

  
## <a name="see-also"></a>Voir aussi  
 [Analyser l’utilisation des ressources &#40;Moniteur système&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md)   
 [SQLServer, objet Statistiques des groupes de charges de travail](../../relational-databases/performance-monitor/sql-server-workload-group-stats-object.md)   
 [Resource Governor](../../relational-databases/resource-governor/resource-governor.md)  
  
  
