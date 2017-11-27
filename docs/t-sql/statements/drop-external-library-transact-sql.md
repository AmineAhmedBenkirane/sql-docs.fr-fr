---
title: "SUPPRIMER la bibliothèque externe (Transact-SQL) | Documents Microsoft"
ms.custom: 
ms.date: 08/17/2017
ms.prod: sql-non-specified
ms.prod_service: sql-database
ms.service: 
ms.component: t-sql|statements
ms.reviewer: 
ms.suite: sql
ms.technology: r-services
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DROP EXTERNAL LIBRARY
- DROP_EXTERNAL_LIBRARY_TSQL
dev_langs: TSQL
helpviewer_keywords: DROP EXTERNAL LIBRARY
author: jeannt
ms.author: jeannt
manager: jhubbard
ms.openlocfilehash: c157270e83ccfd3277356863b26c49222691e9e3
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="drop-external-library-transact-sql"></a>SUPPRIMER la bibliothèque externe (Transact-SQL)  
[!INCLUDE[tsql-appliesto-ss2017-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2017-xxxx-xxxx-xxx-md.md)]

Supprime une bibliothèque de package existante.

## <a name="syntax"></a>Syntaxe  

```
DROP EXTERNAL LIBRARY library_name  
[ AUTHORIZATION owner_name ];  
```

### <a name="arguments"></a>Arguments

**nom_librairie**

Spécifie le nom d’une bibliothèque de package existante.

Les bibliothèques sont limités à l’utilisateur. Autrement dit, les noms de bibliothèque sont considérées comme uniques dans le contexte d’un utilisateur spécifique ou un propriétaire.

**owner_name**

Spécifie le nom de l’utilisateur ou le rôle de propriétaire de la bibliothèque externe.

Les propriétaires de base de données peuvent supprimer des bibliothèques créées par d’autres utilisateurs.

### <a name="return-values"></a>Valeurs retournées

Un message d’information est retourné si l’instruction a réussi.

## <a name="remarks"></a>Notes

Contrairement à d’autres `DROP` instructions dans SQL Server, cette instruction prend en charge la spécification d’une clause authorization facultatif. Cela permet de **dbo** ou des utilisateurs dans le **db_owner** rôle pour supprimer une bibliothèque de package téléchargé par un utilisateur standard dans la base de données.

## <a name="examples"></a>Exemples

Ajouter un package R personnalisé, nommé `customPackage`, à une base de données :

```sql
CREATE EXTERNAL LIBRARY customPackage 
FROM 'C:\Users\Username\CustomPackages\customPackage.zip';
```

Supprimer le `customPackage` bibliothèque.

```sql
DROP EXTERNAL LIBRARY customPackage <user_name>;
```

## <a name="see-also"></a>Voir aussi  
[CRÉER la bibliothèque externe (Transact-SQL)](create-external-library-transact-sql.md)  
[ALTER bibliothèque externe (Transact-SQL)](alter-external-library-transact-sql.md)  
[sys.external_library_files](../../relational-databases/system-catalog-views/sys-external-library-files-transact-sql.md)  
[sys.external_libraries](../../relational-databases/system-catalog-views/sys-external-libraries-transact-sql.md)  

