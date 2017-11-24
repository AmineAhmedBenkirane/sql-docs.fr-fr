---
title: QUOTENAME (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- QUOTENAME_TSQL
- QUOTENAME
dev_langs: TSQL
helpviewer_keywords:
- delimited identifiers [SQL Server]
- input strings [SQL Server]
- Unicode [SQL Server], delimited identifiers
- QUOTENAME function
- valid identifiers [SQL Server]
ms.assetid: 34d47f1e-2ac7-4890-8c9c-5f60f115e076
caps.latest.revision: "35"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Active
ms.openlocfilehash: 650892048daea0a86dc357ebbe2dd08b7eea5184
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="quotename-transact-sql"></a>QUOTENAME (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Retourne une chaîne Unicode avec les délimiteurs ajoutés afin que la chaîne d'entrée soit un identificateur délimité [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valide.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
QUOTENAME ( 'character_string' [ , 'quote_character' ] )   
```  
  
## <a name="arguments"></a>Arguments  
 '*Chaîne_de_caractères*'  
 Représente une chaîne de caractères au format Unicode. *Chaîne_de_caractères* est **sysname** et est limité à 128 caractères. Les entrées de plus de 128 caractères retournent une valeur NULL.  
  
 '*caractère guillemet ne*'  
 Représente une chaîne d'un seul caractère à utiliser en tant que délimiteur. Peut être un guillemet simple ( **'** ), un crochet gauche ou droit ( **[]** ), ou un guillemet double ( **»** ). Si *caractère guillemet ne* n’est pas spécifié, les crochets sont utilisés.  
  
## <a name="return-types"></a>Types de retour  
 **nvarchar (258)**  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant prend la chaîne de caractères `abc[]def` et utilise les caractères `[` `]` pour créer un identificateur délimité [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valide.  
  
```  
SELECT QUOTENAME('abc[]def');  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
[abc[]]def]  
  
(1 row(s) affected)  
```  
  
 Vous remarquerez que dans la chaîne `abc[]def`, le crochet de droite est doublé pour indiquer un caractère d'échappement.  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Exemples : [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] et[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 L'exemple suivant prend la chaîne de caractères `abc def` et utilise les caractères `[` `]` pour créer un identificateur délimité [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valide.  
  
```  
SELECT QUOTENAME('abc def');   
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
[abc def]  
  
(1 row(s) affected)  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions de chaîne &#40; Transact-SQL &#41;](../../t-sql/functions/string-functions-transact-sql.md)  
  
  

