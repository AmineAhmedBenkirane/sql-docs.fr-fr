---
title: Sys.dm_pdw_component_health_active_alerts (Transact-SQL) | Documents Microsoft
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.prod_service: pdw
ms.service: ''
ms.component: dmv's
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c53e4a36-b841-424a-b8e2-255b1878deb6
caps.latest.revision: 8
author: barbkess
ms.author: barbkess
manager: craigg
ms.workload: Inactive
monikerRange: '>= aps-pdw-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: e9bbbbf8cd576bc387d4e5f59a91add0ae05044a
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="sysdmpdwcomponenthealthactivealerts-transact-sql"></a>Sys.dm_pdw_component_health_active_alerts (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md.md)]

  Stocke les alertes actives sur [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] composants.  
  
|Nom de la colonne|Type de données| Description|Plage|  
|-----------------|---------------|-----------------|-----------|  
|pdw_node_id|**int**|Identificateur unique d’un [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] nœud.<br /><br /> pdw_node_id id_composant, component_instance_id, id_alerte et alert_instance_id forment la clé pour cette vue.|NOT NULL|  
|id_composant|**int**|L’ID du composant. Consultez [sys.pdw_health_components &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-pdw-health-components-transact-sql.md).<br /><br /> pdw_node_id id_composant, component_instance_id, id_alerte et alert_instance_id forment la clé pour cette vue.|NOT NULL|  
|component_instance_id|**nvarchar(255)**|pdw_node_id id_composant, component_instance_id, id_alerte et alert_instance_id forment la clé pour cette vue.|NOT NULL|  
|alert_id|**int**|L’ID pour le type d’alerte. Consultez [sys.pdw_health_alerts &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-pdw-health-alerts-transact-sql.md).<br /><br /> pdw_node_id id_composant, component_instance_id, id_alerte et alert_instance_id forment la clé pour cette vue.|NOT NULL|  
|alert_instance_id|**nvarchar(36)**|Identifie une instance d’une alerte donnée.<br /><br /> pdw_node_id id_composant, component_instance_id, id_alerte et alert_instance_id forment la clé pour cette vue.|NOT NULL|  
|current_value|**nvarchar(255)**|Utilisé lorsque l’alerte est de type StatusChange. Il s’agit de l’état du composant actuel. Valeur est NULL pour les alertes de seuil de type. Consultez [sys.pdw_health_alerts &#40;Transact-SQL&#41; ](../../relational-databases/system-catalog-views/sys-pdw-health-alerts-transact-sql.md) pour obtenir la liste des types d’alerte.|NULL|  
|previous_value|**nvarchar(255)**|Utilisé lorsque l’alerte est de type StatusChange. Il s’agit de l’état du composant précédent. Valeur est NULL pour les alertes de seuil de type. Consultez [sys.pdw_health_alerts &#40;Transact-SQL&#41; ](../../relational-databases/system-catalog-views/sys-pdw-health-alerts-transact-sql.md) pour obtenir la liste des types d’alerte.|NULL|  
|create_time|**datetime**|Heure et date à laquelle l’alerte a été générée.|NOT NULL|  
  
 Pour plus d’informations sur le nombre maximal de lignes conservées par cette vue, consultez « Minimum et Maximum valeurs » dans le [!INCLUDE[pdw-product-documentation](../../includes/pdw-product-documentation-md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [Entrepôt de données SQL et les données en parallèle de l’entrepôt de vues de gestion dynamique &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
