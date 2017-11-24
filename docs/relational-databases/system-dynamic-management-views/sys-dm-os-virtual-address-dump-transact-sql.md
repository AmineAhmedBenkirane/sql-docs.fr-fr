---
title: Sys.dm_os_virtual_address_dump (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- dm_os_virtual_address_dump
- sys.dm_os_virtual_address_dump_TSQL
- sys.dm_os_virtual_address_dump
- dm_os_virtual_address_dump_TSQL
dev_langs: TSQL
helpviewer_keywords: sys.dm_os_virtual_address_dump dynamic management view
ms.assetid: 7b24ea55-3873-42fd-a86c-441c92eb6175
caps.latest.revision: "23"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 7088f19776027b7e71d2a0519797c655d7632110
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmosvirtualaddressdump-transact-sql"></a>sys.dm_os_virtual_address_dump (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2008-xxxx-asdw-pdw-md.md)]

  Retourne des informations sur une série de pages dans l'espace d'adressage virtuel du processus appelant.  
  
> [!NOTE]  
>  Ces informations sont également retournées par la **VirtualQuery** API Windows.  
  
> [!NOTE]  
>  Pour appeler cette de [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] ou [!INCLUDE[ssPDW](../../includes/sspdw-md.md)], utilisez le nom **sys.dm_pdw_nodes_os_virtual_address_dump**.  
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**region_base_address**|**varbinary (8)**|Pointeur sur l'adresse de base de la région des pages. N'accepte pas la valeur NULL.|  
|**region_allocation_base_address**|**varbinary (8)**|Pointeur sur l'adresse de base d'une série de pages allouées par la fonction API Windows VirtualAlloc. La page sur laquelle pointe le membre BaseAddress se trouve dans cette plage d'allocation. N'accepte pas la valeur NULL.|  
|**region_allocation_protection**|**varbinary (8)**|Attributs de protection lors de l'allocation initiale de la région. Les valeurs possibles sont les suivantes :<br /><br /> -PAGE_READONLY<br />-PAGE_READWRITE<br />-PAGE_NOACCESS<br />-PAGE_WRITECOPY<br />-PAGE_EXECUTE<br />-PAGE_EXECUTE_READ<br />-PAGE_EXECUTE_READWRITE<br />-PAGE_EXECUTE_WRITECOPY<br />-PAGE_GUARD<br />-PAGE_NOCACHE<br /><br /> N'accepte pas la valeur NULL.|  
|**region_size_in_bytes**|**bigint**|Taille de la région, en octets, à partir de l'adresse de base dans laquelle toutes les pages ont les mêmes attributs. N'accepte pas la valeur NULL.|  
|**region_state**|**varbinary (8)**|État actuel de la région Il s’agit d’une des opérations suivantes :<br /><br /> -MEM_COMMIT<br />-MEM_RESERVE<br />-MEM_FREE<br /><br /> N'accepte pas la valeur NULL.|  
|**region_current_protection**|**varbinary (8)**|Attributs de protection. Les valeurs possibles sont les suivantes :<br /><br /> -PAGE_READONLY<br />-PAGE_READWRITE<br />-PAGE_NOACCESS<br />-PAGE_WRITECOPY<br />-PAGE_EXECUTE<br />-PAGE_EXECUTE_READ<br />-PAGE_EXECUTE_READWRITE<br />-PAGE_EXECUTE_WRITECOPY<br />-PAGE_GUARD<br />-PAGE_NOCACHE<br /><br /> N'accepte pas la valeur NULL.|  
|**region_type**|**varbinary (8)**|Identifie les types des pages dans cette région. Il peut s'agir de l'une des valeurs suivantes :<br /><br /> -MEM_PRIVATE<br />-MEM_MAPPED<br />-MEM_IMAGE<br /><br /> N'accepte pas la valeur NULL.|  
|**pdw_node_id**|**int**|**S’applique aux**: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)],[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]<br /><br /> L’identificateur du nœud qui se trouve sur cette distribution.|  
  
## <a name="permissions"></a>Permissions  
 requièrent l'autorisation VIEW SERVER STATE sur le serveur.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions et vues de gestion dynamique &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [Système d’exploitation de serveur SQL relatives des vues de gestion dynamique &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sql-server-operating-system-related-dynamic-management-views-transact-sql.md)  
  
  


