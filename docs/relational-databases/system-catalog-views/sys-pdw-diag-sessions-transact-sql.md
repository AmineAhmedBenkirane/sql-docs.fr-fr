---
title: sys.pdw_diag_sessions (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.prod_service: pdw
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 4d23688a-cddb-4eed-8231-ecde2a0b0e65
caps.latest.revision: 
author: barbkess
ms.author: barbkess
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 91ad46c8f8bc0391bab933d2033d54e43626a6cc
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2018
---
# <a name="syspdwdiagsessions-transact-sql"></a>sys.pdw_diag_sessions (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md.md)]

  Contient des informations concernant les différentes sessions de diagnostic qui ont été créés sur le système.  
  
|Nom de la colonne|Type de données| Description|Plage|  
|-----------------|---------------|-----------------|-----------|  
|**nom**|**nvarchar(255)**|Nom de la session de diagnostic.<br /><br /> Clé pour cette vue.||  
|**xml_data**|**nvarchar(4000)**|Charge utile XML qui décrit la session.||  
|**is_active**|**bit**|Indicateur précisant si l’indicateur est actif.||  
|**host_address**|**nvarchar(255)**|Adresse de l’ordinateur qui héberge la définition de session (nœud de contrôle).||  
|**principal_id**|**int**|ID de l’utilisateur qui a créé la session au niveau de la base de données.||  
|**database_id**|**int**|ID de la base de données qui est la portée de la session de diagnostic.|  
  
## <a name="see-also"></a>Voir aussi  
 [Entrepôt de données SQL et les vues de catalogue de l’entrepôt de données en parallèle](../../relational-databases/system-catalog-views/sql-data-warehouse-and-parallel-data-warehouse-catalog-views.md)  
  
  
