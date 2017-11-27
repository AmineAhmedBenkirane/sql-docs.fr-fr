---
title: Sys.server_event_notifications (Transact-SQL) | Documents Microsoft
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
- server_event_notifications
- sys.server_event_notifications
- sys.server_event_notifications_TSQL
- server_event_notifications_TSQL
dev_langs: TSQL
helpviewer_keywords: sys.server_event_notifications catalog view
ms.assetid: 1a83a044-3130-4551-95ca-162525846ff5
caps.latest.revision: "36"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 1bd455fe1fed954f3e6b4d81b8b5bd47121b6c97
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="sysservereventnotifications-transact-sql"></a>sys.server_event_notifications (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retourne une ligne pour chaque objet de notification d'événement au niveau du serveur.  
  
|Nom de colonne|Type de données|Description|  
|-----------------|---------------|-----------------|  
|**nom**|**sysname**|Nom de la notification d'événement serveur. Unique pour toutes les notifications d'événements serveur.|  
|**object_id**|**int**|Numéro d'identification de l'objet. Est unique dans le **master** base de données.|  
|**parent_class**|**tinyint**|Classe du parent. A toujours la valeur 100 = Serveur.|  
|**parent_class_desc**|**nvarchar (60)**|Description d'une classe de parent. A toujours la valeur SERVER.|  
|**parent_id**|**int**|A toujours la valeur 0.|  
|**create_date**|**datetime**|Date de création.|  
|**modify_date**|**datetime**|Date de la dernière modification de l'objet à l'aide d'une instruction ALTER.|  
|**SERVICE_NAME**|**nvarchar (256)**|Nom du service cible auquel la notification est envoyée.|  
|**BROKER_INSTANCE**|**nvarchar (128)**|Service Broker sur lequel le service cible nommé est défini.|  
|**creator_sid**|**varbinary(85)**|ID de sécurité de la connexion exécutant l'instruction qui crée la notification d'événement. La valeur est NULL si WITH FAN_IN n'est pas spécifié dans la définition de la notification d'événement.|  
|**principal_id**|**int**|ID du principal de serveur propriétaire.|  
  
## <a name="permissions"></a>Permissions  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Pour plus d'informations, consultez [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Affichages catalogue d’objets &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [Affichages catalogue &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
