---
title: Sys.parameter_xml_schema_collection_usages (Transact-SQL) | Documents Microsoft
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.service: ''
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.parameter_xml_schema_collection_usages
- parameter_xml_schema_collection_usages
- parameter_xml_schema_collection_usages_TSQL
- sys.parameter_xml_schema_collection_usages_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.parameter_xml_schema_collection_usages catalog view
ms.assetid: bffb91a3-492c-4375-bd2a-db8fc1a3ace4
caps.latest.revision: 14
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
monikerRange: = azuresqldb-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: 3d6ad0bd96aea11636bedab12dded02ef520063a
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="sysparameterxmlschemacollectionusages-transact-sql"></a>sys.parameter_xml_schema_collection_usages (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Retourne une ligne pour chaque paramètre qui est validé par un schéma XML.  
  
 |Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**object_id**|**int**|Identificateur de l'objet auquel ce paramètre appartient.|  
|**parameter_id**|**int**|ID du paramètre.  Unique dans l'objet.|  
|**xml_collection_id**|**int**|ID de la collection de schémas XML qui contient l'espace de noms de schéma XML de validation du paramètre.|  
  
## <a name="permissions"></a>Autorisations  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Pour plus d'informations, consultez [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Affichages catalogue &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Schémas XML &#40;système de Type XML&#41; affichages catalogue &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/xml-schemas-xml-type-system-catalog-views-transact-sql.md)  
  
  
