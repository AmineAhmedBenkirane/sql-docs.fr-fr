---
title: "Autorisations d’objet GRANT système (Transact-SQL) | Documents Microsoft"
ms.custom: 
ms.date: 07/26/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- encryption [SQL Server], system objects
- system objects [SQL Server]
- GRANT statement, system objects
ms.assetid: 9d4e89f4-478f-419a-8b50-b096771e3880
caps.latest.revision: 26
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 3bd1f78212ef050c6610eab57f95cd44d51d9fbf
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="grant-system-object-permissions-transact-sql"></a>GRANT – octroi d'autorisations d'objet système (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Permet d'accorder des autorisations sur des objets système tels que des procédures stockées système, des procédures stockées étendues, des fonctions et des vues.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
GRANT { SELECT | EXECUTE } ON [ sys.]system_object TO principal   
```  
  
## <a name="arguments"></a>Arguments  
 [sys]. .  
 L'identificateur sys est requis uniquement lorsque vous faites référence à des affichages catalogue ou à des vues de gestion dynamique.  
  
 *system_object*  
 Spécifie l’objet sur lequel l’autorisation doit être accordée.  
  
 *principal*  
 Spécifie le principal auquel l'autorisation est accordée.  
  
## <a name="remarks"></a>Notes  
 Cette instruction permet d'accorder des autorisations sur des procédures stockées, procédures stockées étendues, fonctions table, fonctions scalaires, vues, affichages catalogue, vues de compatibilité, vues INFORMATION_SCHEMA, vues de gestion dynamique et tables système installées par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Chacun de ces objets système existe sous la forme d'un enregistrement unique dans la base de données des ressources du serveur (mssqlsystemresource). La base de données des ressources est en lecture seule. Un lien à l'objet est exposé comme un enregistrement dans le schéma sys de chaque base de données. L'autorisation d'exécuter ou de sélectionner un objet système peut être accordée, refusée ou révoquée.  
  
 L'octroi de l'autorisation d'exécuter ou de sélectionner un objet n'implique pas nécessairement toutes les autorisations requises pour utiliser l'objet. La plupart des objets effectuent des opérations qui nécessitent des autorisations supplémentaires. Par exemple, un utilisateur auquel est accordée l'autorisation EXECUTE sur sp_addlinkedserver ne peut pas créer un serveur lié, à moins que l'utilisateur soit également membre du rôle de serveur fixe sysadmin.  
  
 La résolution de noms par défaut permet de résoudre les noms de procédures non qualifiés dans la base de données des ressources. Par conséquent, l'identificateur sys est requis uniquement lorsque vous spécifiez des affichages catalogue ou des vues de gestion dynamique.  
  
 L'octroi d'autorisations sur des déclencheurs et sur des colonnes d'objets système n'est pas pris en charge.  
  
 Les autorisations sur les objets système sont conservées lors d'une mise à niveau de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 Les objets système sont consultables dans l’affichage catalogue [sys.system_objects](../../relational-databases/system-catalog-views/sys-system-objects-transact-sql.md) . Les autorisations sur les objets système sont visibles dans le [sys.database_permissions](../../relational-databases/system-catalog-views/sys-database-permissions-transact-sql.md) catalogue vue dans la base de données master.  
  
 La requête ci-dessous retourne des informations sur les autorisations des objets système :  
  
```  
SELECT * FROM master.sys.database_permissions AS dp   
    JOIN sys.system_objects AS so  
    ON dp.major_id = so.object_id  
    WHERE dp.class = 1 AND so.parent_object_id = 0 ;  
GO  
```  
  
## <a name="permissions"></a>Permissions  
 Requiert l'autorisation CONTROL SERVER.  
  
## <a name="examples"></a>Exemples  
  
### <a name="a-granting-select-permission-on-a-view"></a>A. Octroi d'une autorisation SELECT sur une vue  
 L’exemple suivant accorde la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connexion `Sylvester1` autorisé à sélectionner une vue qui répertorie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connexions. Le code accorde ensuite l'autorisation supplémentaire requise pour afficher les métadonnées sur les connexions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui n'appartiennent pas à l'utilisateur.  
  
```  
USE AdventureWorks2012;  
GRANT SELECT ON sys.sql_logins TO Sylvester1;  
GRANT VIEW SERVER STATE to Sylvester1;  
GO  
```  
  
### <a name="b-granting-execute-permission-on-an-extended-stored-procedure"></a>B. Octroi d'une autorisation EXECUTE sur une procédure stockée étendue  
 Dans l'exemple suivant, l'autorisation `EXECUTE` sur `xp_readmail` est accordée à `Sylvester1`.  
  
```  
GRANT EXECUTE ON xp_readmail TO Sylvester1;  
GO  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Sys.system_objects &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-system-objects-transact-sql.md)   
 [Sys.database_permissions &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-database-permissions-transact-sql.md)   
 [Autorisations d’objet système REVOKE &#40; Transact-SQL &#41;](../../t-sql/statements/revoke-system-object-permissions-transact-sql.md)   
 [REFUSER des autorisations d’objet système &#40; Transact-SQL &#41;](../../t-sql/statements/deny-system-object-permissions-transact-sql.md)  
  
  
