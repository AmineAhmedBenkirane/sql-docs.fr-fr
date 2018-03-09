---
title: Sys.database_role_members (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 01/31/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.database_role_members_TSQL
- sys.database_role_members
- database_role_members_TSQL
- database_role_members
dev_langs:
- TSQL
helpviewer_keywords:
- sys.database_role_members catalog view
ms.assetid: ed1b019d-ca48-4db3-85df-cf6d2db591cf
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: abe12465ae80a9373475a0158cdacc663b8f00fa
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="sysdatabaserolemembers-transact-sql"></a>sys.database_role_members (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Retourne une ligne pour chaque membre de chaque rôle de base de données.  Les utilisateurs de base de données, les rôles d’application et les autres rôles de base de données peuvent être des membres d’un rôle de base de données. Pour ajouter des membres à un rôle, utilisez la [ALTER ROLE](../../t-sql/statements/alter-role-transact-sql.md) instruction avec la `ADD MEMBER` option. Joindre avec [sys.database_principals](../../relational-databases/system-catalog-views/sys-database-principals-transact-sql.md) pour retourner les noms de la `principal_id` valeurs.
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**role_principal_id**|**int**|ID du principal de base de données du rôle.|  
|**member_principal_id**|**int**|ID du principal de base de données du membre.|  
  
## <a name="permissions"></a>Permissions  
 Tout utilisateur peut consulter sa propre appartenance au rôle. Pour afficher d’autres rôles appartenances nécessite l’appartenance dans le `db_securityadmin` rôle de base de données fixe ou `VIEW DEFINITION` sur la base de données.  
  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Pour plus d'informations, consultez [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="example"></a>Exemple  
 La requête suivante retourne les membres des rôles de base de données.  
  
```  
SELECT DP1.name AS DatabaseRoleName,   
   isnull (DP2.name, 'No members') AS DatabaseUserName   
 FROM sys.database_role_members AS DRM  
 RIGHT OUTER JOIN sys.database_principals AS DP1  
   ON DRM.role_principal_id = DP1.principal_id  
 LEFT OUTER JOIN sys.database_principals AS DP2  
   ON DRM.member_principal_id = DP2.principal_id  
WHERE DP1.type = 'R'
ORDER BY DP1.name;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Affichages catalogue de sécurité &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/security-catalog-views-transact-sql.md)   
 [Principaux &#40;moteur de base de données&#41;](../../relational-databases/security/authentication-access/principals-database-engine.md)   
 [Affichages catalogue &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
[ALTER ROLE (Transact-RÉALISE)](../../t-sql/statements/alter-role-transact-sql.md)      
[Sys.server_role_members (Transact-SQL)](../../relational-databases/system-catalog-views/sys-server-role-members-transact-sql.md)   
  


