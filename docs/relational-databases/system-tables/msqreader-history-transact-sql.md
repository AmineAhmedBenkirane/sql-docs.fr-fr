---
title: MSqreader_history (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-tables
ms.reviewer: 
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- MSqreader_history
- MSqreader_history_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSqreader_history system table
ms.assetid: c5c91d39-513c-4a77-870b-c8ef74a1cd6b
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 7c9615bb702c89d8b2a5be0087671df9d8a6a910
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="msqreaderhistory-transact-sql"></a>MSqreader_history (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Le **MSqreader_history** table contient des lignes d’historique des Agents de lecture de file d’attente associé au serveur de distribution local. Cette table est stockée dans la base de données de distribution.  
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**éléments agent_id**|**int**|ID de l'Agent de lecture de la file d'attente.|  
|**id_de_la_publication**|**int**|ID de la publication.|  
|**runstatus**|**int**|État d'exécution de l'agent :<br /><br /> **1** = démarrage.<br /><br /> **2** = réussisse.<br /><br /> **3** = en cours d’exécution.<br /><br /> **4** = inactif.<br /><br /> **5** = nouvelle tentative.<br /><br /> **6** = échec.|  
|**heure_début**|**datetime**|Date et heure du début de la session de l'Agent.|  
|**time**|**datetime**|Date et heure du dernier message enregistré.|  
|**duration**|**int**|Durée de l'activité enregistrée de la session, en secondes.|  
|**commentaires**|**nvarchar(255)**|Texte descriptif.|  
|**Identificateur transaction_id :**|**nvarchar (40)**|ID de transaction stocké avec le message, le cas échéant.|  
|**transaction_status**|**int**|L’état de la transaction.|  
|**transactions_processed**|**int**|Nombre total de transactions traitées pendant la session.|  
|**commands_processed**|**int**|Nombre total de commandes traitées pendant la session.|  
|**delivery_rate**|**float(53)**|Nombre moyen de commandes livrées par seconde.|  
|**transaction_rate**|**float(53)**|Taux des transactions traitées.|  
|**subscriber** (Abonné)|**sysname**|Nom de l'Abonné.|  
|**SubscriberDB**|**sysname**|Le nom de la base de données d’abonnement.|  
|**ID_erreur**|**int**|Si pas zéro, le nombre représente un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] message d’erreur.|  
|**timestamp**|**timestamp**|Colonne timestamp de cette table.|  
  
## <a name="see-also"></a>Voir aussi  
 [Tables de réplication &#40; Transact-SQL &#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Vues de réplication &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
