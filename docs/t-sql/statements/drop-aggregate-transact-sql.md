---
title: DROP AGGREGATE (Transact-SQL) | Documents Microsoft
ms.custom:
- SQL2016_New_Updated
ms.date: 05/10/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DROP_AGGREGATE_TSQL
- DROP AGGREGATE
dev_langs:
- TSQL
helpviewer_keywords:
- aggregate functions [SQL Server], removing
- removing user-defined functions
- dropping user-defined functions
- user-defined functions [CLR integration]
- deleting user-defined functions
- DROP AGGREGATE statement
ms.assetid: 84ffc4e7-c451-4f1f-9a67-7fc3a120e53f
caps.latest.revision: 31
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: a9fcab3dc576f15110bed8c1c82271731f326280
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="drop-aggregate-transact-sql"></a>DROP AGGREGATE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Supprime une fonction d'agrégation définie par l'utilisateur de la base de données active. Fonctions d’agrégation définies par l’utilisateur sont créées à l’aide de [CREATE AGGREGATE](../../t-sql/statements/create-aggregate-transact-sql.md).  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
DROP AGGREGATE [ IF EXISTS ] [ schema_name . ] aggregate_name  
```  
  
## <a name="arguments"></a>Arguments  
 *S’IL EXISTE*  
 **S’applique à**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] jusqu’à [version actuelle](http://go.microsoft.com/fwlink/p/?LinkId=299658)).  
  
 Conditionnellement supprime l’agrégat uniquement s’il existe déjà.  
  
 *schema_name*  
 Nom du schéma auquel appartient la fonction d'agrégation définie par l'utilisateur.  
  
 *aggregate_name*  
 Nom de la fonction d'agrégation définie par l'utilisateur à supprimer.  
  
## <a name="remarks"></a>Notes  
 DROP AGGREGATE ne s'exécute pas si des vues, fonctions ou procédures stockées créées avec une liaison de schéma référencent la fonction d'agrégation définie par l'utilisateur à supprimer.  
  
## <a name="permissions"></a>Permissions  
 Pour exécuter DROP AGGREGATE, un utilisateur doit, au minimum, posséder l'autorisation ALTER sur le schéma auquel appartient l'agrégation définie par l'utilisateur ou l'autorisation CONTROL sur l'agrégation.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant supprime l'agrégation `Concatenate`.  
  
```  
DROP AGGREGATE dbo.Concatenate;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [CRÉER un agrégat &#40; Transact-SQL &#41;](../../t-sql/statements/create-aggregate-transact-sql.md)   
 [Créer des agrégats définis par l’utilisateur](../../relational-databases/user-defined-functions/create-user-defined-aggregates.md)  
  
  

