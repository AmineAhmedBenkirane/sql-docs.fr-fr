---
title: "Type de données synonymes (Transact-SQL) | Documents Microsoft"
ms.custom: 
ms.date: 07/23/2017
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
- data types [SQL Server], synonyms
- alternate names [SQL Server]
- synonyms [SQL Server], data types
ms.assetid: 390eef67-1a49-4185-a971-e07765be9717
caps.latest.revision: 18
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 1d9b1da2bdc7084268740cd7de2580e64ee9698b
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="data-type-synonyms-transact-sql"></a>Synonymes des types de données (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

Les synonymes des types de données sont inclus dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour la conformité aux normes ISO. Le tableau suivant répertorie les synonymes et les types de données système [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auxquels ils sont mappés.
  
|Synonyme|Type de données système SQL Server|  
|---|---|
|**Variable binaire**|**varbinary**|  
|**char varying**|**varchar**|  
|**caractère**|**char**|  
|**caractère**|**char (1)**|  
|**caractère (**  *n*  **)**|**char(n)**|  
|**variable de caractère (**  *n*  **)**|**varchar(n)**|  
|**DEC**|**decimal**|  
|**Double précision**|**float**|  
|**float**[**(***n***)**] pour  *n*  = 1 à 7|**real**|  
|**float**[**(***n***)**] pour  *n*  = 8 à 15|**float**|  
|**entier**|**int**|  
|**les caractères nationaux (**  *n*  **)**|**NCHAR (n)**|  
|**national char (**  *n*  **)**|**NCHAR (n)**|  
|**variable de caractères nationaux (**  *n*  **)**|**nvarchar (n)**|  
|**national char varying (**  *n*  **)**|**nvarchar (n)**|  
|**texte national**|**ntext**|  
|**timestamp**|rowversion|  
  
Synonymes des types de données peut être utilisés au lieu du nom de type de base de données correspondant dans les instructions data definition language (DDL), telles que CREATE TABLE, CREATE PROCEDURE ou DECLARE  *@variable* . Cependant, la visibilité des synonymes est nulle après la création de l'objet. Une fois l'objet créé, il reçoit le type de données de base associé au synonyme. La consignation ne spécifie pas que le synonyme a été utilisé dans l'instruction ayant créé l'objet.
  
Tous les objets issus de l'objet d'origine, tels que les expressions ou colonnes de l'ensemble de résultats, reçoivent le type de données de base. Toutes les fonctions de métadonnées ultérieurement appliquées à l'objet d'origine et tous les objets dérivés font état du type de données de base, non du synonyme. Ce comportement se produit avec les opérations de métadonnées, telles que **sp_help** et autre système les procédures stockées, les vues de schémas d’informations ou les différentes opérations de métadonnées d’API d’accès aux données qui signalent les types de données de table ou les colonnes du jeu de résultats.
  
Vous pouvez, par exemple, créer une table en spécifiant `national character varying` :
  
```sql
CREATE TABLE ExampleTable (PriKey int PRIMARY KEY, VarCharCol national character varying(10))  
```  
  
`VarCharCol`est en réalité attribué un **nvarchar (10)** type de données, et toutes les fonctions de métadonnées ultérieures signalent la colonne comme un **nvarchar (10)** colonne. Les fonctions de métadonnées les signaleront jamais comme un **VARYING (10) de caractères nationaux** colonne.
  
## <a name="see-also"></a>Voir aussi
[Types de données &#40;Transact-SQL&#41;](../../t-sql/data-types/data-types-transact-sql.md)
  
  

