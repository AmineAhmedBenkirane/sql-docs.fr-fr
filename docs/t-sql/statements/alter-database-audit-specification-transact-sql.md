---
title: ALTER DATABASE AUDIT SPECIFICATION (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: sql-database
ms.service: 
ms.component: t-sql|statements
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ALTER_DATABASE_AUDIT_SPECIFICATION_TSQL
- ALTER DATABASE AUDIT SPECIFICATION
- ALTER_DATABASE_AUDIT_TSQL
- ALTER DATABASE AUDIT
dev_langs:
- TSQL
helpviewer_keywords:
- ALTER DATABASE AUDIT SPECIFICATION statement
ms.assetid: 85f4e7e6-a330-4de0-9048-64f386ccc314
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 1fc9148b05ca5b7b77d149e19e937502450ea0d3
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="alter-database-audit-specification-transact-sql"></a>ALTER DATABASE AUDIT SPECIFICATION (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Modifie un objet de spécification d'audit de base de données à l'aide de la fonctionnalité [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Audit. Pour plus d’informations, consultez [SQL Server Audit &#40moteur de base de données&#41;](../../relational-databases/security/auditing/sql-server-audit-database-engine.md).  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
ALTER DATABASE AUDIT SPECIFICATION audit_specification_name  
{  
    [ FOR SERVER AUDIT audit_name ]  
    [ { { ADD | DROP } (   
           { <audit_action_specification> | audit_action_group_name }   
                )   
      } [, ...n] ]  
    [ WITH ( STATE = { ON | OFF } ) ]  
}  
[ ; ]  
<audit_action_specification>::=  
{  
      <action_specification>[ ,...n ] ON [ class :: ] securable   
     BY principal [ ,...n ]   
}  
  
```  
  
## <a name="arguments"></a>Arguments  
 *audit_specification_name*  
 Nom de la spécification de l'audit.  
  
 *audit_name*  
 Nom de l'audit auquel cette spécification est appliquée.  
  
 *audit_action_specification*  
 Nom d'une ou plusieurs actions pouvant être auditées au niveau de la base de données. Pour obtenir la liste de groupes d’actions d’audit, consultez [groupes d’actions d’Audit SQL Server et les Actions](../../relational-databases/security/auditing/sql-server-audit-action-groups-and-actions.md).  
  
 *audit_action_group_name*  
 Nom d'un ou plusieurs groupes d'actions pouvant être audités au niveau de la base de données. Pour obtenir la liste de groupes d’actions d’audit, consultez [groupes d’actions d’Audit SQL Server et les Actions](../../relational-databases/security/auditing/sql-server-audit-action-groups-and-actions.md).  
  
 *classe*  
 Nom de classe (si applicable) sur l'élément sécurisable.  
  
 *élément sécurisable*  
 Table, vue ou un autre objet sécurisable dans la base de données sur lequel appliquer l’action d’audit ou le groupe d’actions d’audit. Pour plus d'informations, consultez [Securables](../../relational-databases/security/securables.md).  
  
 *colonne*  
 Nom de la colonne (si applicable) sur l'élément sécurisable.  
  
 *principal*  
 Nom de principal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur lequel appliquer l'action d'audit ou le groupe d'actions d'audit. Pour plus d’informations, consultez [principaux &#40; moteur de base de données &#41;](../../relational-databases/security/authentication-access/principals-database-engine.md).  
  
 AVEC **(** ÉTAT  **=**  {ON | {OFF} **)**  
 Active ou désactive la collecte d'enregistrements d'audit pour cette spécification d'audit. Les modifications de l'état de la spécification d'audit doivent être effectuées à l'extérieur d'une transaction utilisateur et elles ne peuvent pas comporter d'autres modifications dans la même instruction lorsque la transition passe de ON à OFF.  
  
## <a name="remarks"></a>Notes  
 Les spécifications d'audit de base de données sont des objets non sécurisables qui résident dans une base de données spécifiée. Vous devez définir l’état d’une spécification d’audit sur Off pour apporter des modifications à une base de données de spécification d’audit. Si ALTER DATABASE AUDIT SPECIFICATION est exécuté alors qu'un audit est activé avec des options autres que STATE=OFF, vous recevez un message d'erreur. Pour plus d'informations, consultez [tempdb Database](../../relational-databases/databases/tempdb-database.md).  
  
## <a name="permissions"></a>Permissions  
 Les utilisateurs disposant de l'autorisation ALTER ANY DATABASE AUDIT peuvent modifier des spécifications d'audit de la base de données et les lier à un audit quelconque.  
  
 Après la création d’une spécification d’audit de base de données, elle peut être affichée par les principaux avec le serveur de contrôle, ou des autorisations ALTER ANY DATABASE AUDIT, le compte sysadmin ou principaux ayant un accès explicit à l’audit.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant modifie une spécification d'audit de la base de données nommée `HIPPA_Audit_DB_Specification` qui audite les instructions `SELECT` par l'utilisateur `dbo`, pour un audit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nommé `HIPPA_Audit`.  
  
```  
ALTER DATABASE AUDIT SPECIFICATION HIPPA_Audit_DB_Specification  
FOR SERVER AUDIT HIPPA_Audit  
    ADD (SELECT  
         ON OBJECT::dbo.Table1  
         BY dbo)  
    WITH (STATE = ON);  
GO  
```  
  
 Pour obtenir un exemple complet sur la création d’un audit, consultez [SQL Server Audit &#40; moteur de base de données &#41;](../../relational-databases/security/auditing/sql-server-audit-database-engine.md).  
  
## <a name="see-also"></a>Voir aussi  
 [CREATE SERVER AUDIT &#40; Transact-SQL &#41;](../../t-sql/statements/create-server-audit-transact-sql.md)   
 [ALTER SERVER AUDIT &#40; Transact-SQL &#41;](../../t-sql/statements/alter-server-audit-transact-sql.md)   
 [DROP SERVER AUDIT &#40; Transact-SQL &#41;](../../t-sql/statements/drop-server-audit-transact-sql.md)   
 [CREATE SERVER AUDIT SPECIFICATION &#40; Transact-SQL &#41;](../../t-sql/statements/create-server-audit-specification-transact-sql.md)   
 [ALTER SERVER AUDIT SPECIFICATION &#40; Transact-SQL &#41;](../../t-sql/statements/alter-server-audit-specification-transact-sql.md)   
 [DROP SERVER AUDIT SPECIFICATION &#40; Transact-SQL &#41;](../../t-sql/statements/drop-server-audit-specification-transact-sql.md)   
 [CRÉER une spécification d’AUDIT de base de données &#40; Transact-SQL &#41;](../../t-sql/statements/create-database-audit-specification-transact-sql.md)   
 [DROP DATABASE AUDIT SPECIFICATION &#40; Transact-SQL &#41;](../../t-sql/statements/drop-database-audit-specification-transact-sql.md)   
 [ALTER AUTHORIZATION &#40; Transact-SQL &#41;](../../t-sql/statements/alter-authorization-transact-sql.md)   
 [Sys.fn_get_audit_file &#40; Transact-SQL &#41;](../../relational-databases/system-functions/sys-fn-get-audit-file-transact-sql.md)   
 [Sys.server_audits &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-server-audits-transact-sql.md)   
 [Sys.server_file_audits &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-server-file-audits-transact-sql.md)   
 [Sys.server_audit_specifications &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-server-audit-specifications-transact-sql.md)   
 [Sys.server_audit_specification_details &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-server-audit-specification-details-transact-sql.md)   
 [Sys.Database audit_specifications &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-database-audit-specifications-transact-sql.md)   
 [Sys.database_audit_specification_details &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-database-audit-specification-details-transact-sql.md)   
 [Sys.dm_server_audit_status &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-server-audit-status-transact-sql.md)   
 [Sys.dm_audit_actions &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-audit-actions-transact-sql.md)   
 [Créer un audit du serveur et une spécification d’audit du serveur](../../relational-databases/security/auditing/create-a-server-audit-and-server-audit-specification.md)  
  
  
