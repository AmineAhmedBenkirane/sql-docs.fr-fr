---
title: syscollector_execution_log (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- syscollector_execution_log_TSQL
- syscollector_execution_log
dev_langs: TSQL
helpviewer_keywords:
- data collector view
- syscollector_execution_log view
ms.assetid: 11554d64-0426-42ce-b7ce-5591f67864d2
caps.latest.revision: "18"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: df1ddcc6306078075821af7cfd1a1176a2e31861
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="syscollectorexecutionlog-transact-sql"></a>syscollector_execution_log (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Fournit des informations du journal des exécutions pour un jeu d'éléments de collecte ou package.   
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|log_id|**bigint**|Identifie chaque exécution de jeu d'éléments de collecte. Utilisé pour joindre cette vue à d'autres journaux détaillés. N'accepte pas la valeur NULL.|  
|parent_log_id|**bigint**|Identifie le package parent ou jeu d'éléments de collecte. N'accepte pas la valeur NULL. Les ID sont chaînés dans la relation parent-enfant, ce qui vous permet de déterminer quel package a été démarré par quel jeu d'éléments de collecte. Cette vue groupe les entrées de journal par leur chaînage parent-enfant et met en retrait les noms des packages, afin que la chaîne d'appel soit clairement visible.|  
|collection_set_id|**int**|Identifie le jeu d'éléments de collecte ou package que cette entrée de journal représente. N'accepte pas la valeur NULL.|  
|collection_item_id|**int**|Identifie un élément de collecte. Autorise la valeur NULL.|  
|start_time|**datetime**|Heure de démarrage du jeu d'éléments de collecte ou package. N'accepte pas la valeur NULL.|  
|last_iteration_time|**datetime**|Pour des packages exécutés en permanence, dernière fois où le package a effectué un instantané. Autorise la valeur NULL.|  
|finish_time|**datetime**|Heure de fin de l'exécution pour les packages et jeux d'éléments de collecte terminés. Autorise la valeur NULL.|  
|runtime_execution_mode|**smallint**|Indique si l'activité du jeu d'éléments de collecte consistait à collecter ou à télécharger des données. Autorise la valeur NULL.<br /><br /> Valeurs possibles :<br /><br /> 0 = Collecte<br /><br /> 1 = Téléchargement|  
|status|**smallint**|Indique l'état actuel du jeu d'éléments de collecte ou package. N'accepte pas la valeur NULL.<br /><br /> Valeurs possibles :<br /><br /> 0 = En cours d'exécution<br /><br /> 1 = Terminé<br /><br /> 2 = Échec|  
|operator|**nvarchar (128)**|Identifie la personne qui a démarré le jeu d'éléments de collecte ou package. N'accepte pas la valeur NULL.|  
|package_id|**uniqueidentifier**|Identifie le jeu d'éléments de collecte ou package qui a généré ce journal. Autorise la valeur NULL.|  
|package_name|**nvarchar(4000)**|Nom du package qui a généré ce journal. Autorise la valeur NULL.|  
|package_execution_id|**uniqueidentifier**|Fournit un lien vers la table de journal [!INCLUDE[ssIS](../../includes/ssis-md.md)]. Autorise la valeur NULL.|  
|failure_message|**nvarchar (2048)**|En cas d'échec du jeu d'éléments de collecte ou du package, message d'erreur le plus récent pour ce composant. Autorise la valeur NULL. Pour obtenir plus d’informations sur l’erreur, utilisez le [fn_syscollector_get_execution_details &#40; Transact-SQL &#41; ](../../relational-databases/system-functions/fn-syscollector-get-execution-details-transact-sql.md) (fonction).|  
  
## <a name="permissions"></a>Permissions  
 Requiert SELECT pour dc_operator.  
  
## <a name="see-also"></a>Voir aussi  
 [Procédures stockées du collecteur de données &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql.md)   
 [Vues du collecteur de données &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/data-collector-views-transact-sql.md)   
 [Collecte de données](../../relational-databases/data-collection/data-collection.md)  
  
  
