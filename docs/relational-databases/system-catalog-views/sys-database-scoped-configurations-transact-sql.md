---
title: Sys.database_scoped_configurations (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 01/16/2018
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- database_scoped_configurations
- database_scoped_configurations_TSQL
- sys.database_scoped_configurations
- sys.database_scoped_configurations_TSQL
helpviewer_keywords:
- sys.database_scoped_configurations catalog view
ms.assetid: 8899310a-3464-4d38-9f2f-88396c4e7dc2
caps.latest.revision: 
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 84a4da130f637e85e4ebc950db5568f1fa8876f2
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2018
---
# <a name="sysdatabasescopedconfigurations-transact-sql"></a>sys.database_scoped_configurations (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  Contient une ligne par configuration. 
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**configuration_id**|**int**|ID de l’option de configuration.|  
|**nom**|**nvarchar(60)**|Le nom de l’option de configuration. Pour plus d’informations sur les configurations possibles, consultez [ALTER DATABASE SCOPED CONFIGURATION &#40; Transact-SQL &#41; ](../../t-sql/statements/alter-database-scoped-configuration-transact-sql.md).|  
|**valeur**|**sqlvariant**|La valeur définie pour cette option de configuration pour le réplica principal.|  
|**value_for_secondary**|**sqlvariant**|La valeur définie pour cette option de configuration pour les réplicas secondaires.|  
  
##  <a name="Permissions"></a> Autorisations  
 Nécessite l'appartenance au rôle **public** .  
  
## <a name="remarks"></a>Notes  
 Lorsque la valeur NULL est retournée en tant que la valeur de **value_for_secondary**, cela signifie que la base de données secondaire est définie au principal.  
 
 Paramètres seront reportés avec la base de données de configuration d’une étendue de base de données. Cela signifie que lorsqu’une base de données est restaurée ou attachée, les paramètres de configuration existants restent.
  
## <a name="see-also"></a>Voir aussi  
 [ALTER DATABASE SCOPED CONFIGURATION &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-scoped-configuration-transact-sql.md)  
  
  
