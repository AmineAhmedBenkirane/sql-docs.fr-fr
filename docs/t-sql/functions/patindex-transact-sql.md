---
title: PATINDEX (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/19/2016
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
- PATINDEX
- PATINDEX_TSQL
dev_langs: TSQL
helpviewer_keywords:
- first occurrence of pattern [SQL Server]
- searches [SQL Server], pattern starting position
- starting position of patten search
- pattern searching [SQL Server]
- PATINDEX function
ms.assetid: c0dfb17f-2230-4e36-98da-a9b630bab656
caps.latest.revision: "53"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Active
ms.openlocfilehash: 95a86e78aad7ea01a7f57a046b250825c9e37192
ms.sourcegitcommit: 6b4aae3706247ce9b311682774b13ac067f60a79
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/18/2018
---
# <a name="patindex-transact-sql"></a>PATINDEX (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Renvoie la position de début de la première occurrence d'un modèle dans une expression spécifiée, ou des zéros si le modèle est introuvable, pour tous les types de données texte et caractère valides.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
PATINDEX ( '%pattern%' , expression )  
```  
  
## <a name="arguments"></a>Arguments  
 *pattern*  
 Expression de caractères qui contient la séquence à rechercher. Caractères génériques peuvent être utilisés ; Toutefois, le caractère % doit précéder et suivre *modèle* (sauf lorsque vous recherchez des premiers ou derniers caractères). *modèle* est une expression de la catégorie de type données de chaîne de caractères. *modèle* est limité à 8 000 caractères.  
  
 *expression*  
 Est un [expression](../../t-sql/language-elements/expressions-transact-sql.md), généralement une colonne qui est recherchée dans le modèle spécifié. *expression* est de catégorie de type données de chaîne de caractères.  
  
## <a name="return-types"></a>Types de retour  
 **bigint** si *expression* est de le **varchar (max)** ou **nvarchar (max)** des types de données ; sinon **int**.  
  
## <a name="remarks"></a>Notes  
 Si le paramètre *modèle* ou *expression* est NULL, PATINDEX retourne NULL.  
  
 PATINDEX exécute ses comparaisons en se basant sur le classement de l'entrée. Pour exécuter une comparaison selon un classement spécifié, vous pouvez utiliser COLLATE pour appliquer à l'entrée un classement explicite.  
  
## <a name="supplementary-characters-surrogate-pairs"></a>Caractères supplémentaires (paires de substitution)  
 Lors de l’utilisation de classements SC, la valeur de retour compte toutes les paires de substitution UTF-16 les *expression* paramètre comme un caractère unique. Pour plus d’informations, consultez [Collation and Unicode Support](../../relational-databases/collations/collation-and-unicode-support.md).  
  
 0 x 0000 (**char(0)**) est un caractère indéfini dans les classements Windows et ne peut pas être inclus dans PATINDEX.  
  
## <a name="examples"></a>Exemples  
  
### <a name="a-simple-patindex-example"></a>A. Exemple simple de la fonction PATINDEX  
 L’exemple suivant montre une chaîne de caractères courte (`interesting data`) pour l’emplacement de départ des caractères `ter`.  
  
```  
SELECT PATINDEX('%ter%', 'interesting data');  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `3`  
  
### <a name="b-using-a-pattern-with-patindex"></a>B. Utilisation d'un modèle avec la fonction PATINDEX  
 L'exemple suivant recherche la position de début du modèle `ensure` dans une ligne spécifique de la colonne `DocumentSummary` de la table `Document` dans la base de données [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].  
  
```  
SELECT PATINDEX('%ensure%',DocumentSummary)  
FROM Production.Document  
WHERE DocumentNode = 0x7B40;  
GO   
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```
-----------  
64  
(1 row(s) affected)
```  
  
 Si vous ne limitez pas le nombre de lignes à explorer à l'aide d'une clause `WHERE`, la requête renvoie toutes les lignes de la table et fournit des valeurs différentes de 0 pour les lignes contenant le modèle et des valeurs égales à 0 pour toutes les lignes qui ne le contiennent pas.  
  
### <a name="c-using-wildcard-characters-with-patindex"></a>C. Utilisation de caractères génériques avec la fonction PATINDEX  
 L'exemple suivant utilise les caractères génériques % et _ pour rechercher la position de début du modèle `'en'`, suivi de tout caractère et `'ure'` dans la chaîne spécifiée (l'index démarre à 1) :  
  
```  
SELECT PATINDEX('%en_ure%', 'please ensure the door is locked');  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```
-----------  
8  
```  
  
 `PATINDEX` fonctionne comme `LIKE` ; vous pouvez donc utiliser chacun des caractères génériques. Il n'est pas nécessaire d'ajouter le modèle entre les pourcentages. `PATINDEX('a%', 'abc')` retourne 1 et `PATINDEX('%a', 'cba')` retourne 3.  
  
 Contrairement à `LIKE`, `PATINDEX` retourne une position, comme le fait `CHARINDEX`.  
  
### <a name="d-using-collate-with-patindex"></a>D. Utilisation de COLLATE avec PATINDEX  
 L'exemple qui suit utilise la fonction `COLLATE` pour spécifier explicitement le classement de l'expression recherchée.  
  
```  
USE tempdb;  
GO  
SELECT PATINDEX ( '%ein%', 'Das ist ein Test'  COLLATE Latin1_General_BIN) ;  
GO  
```  
  
### <a name="e-using-a-variable-to-specify-the-pattern"></a>E. Utilisation d'une variable pour spécifier le modèle  
 L’exemple suivant utilise une variable pour transmettre une valeur pour le *modèle* paramètre. Cet exemple utilise le [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] base de données.  
  
```  
DECLARE @MyValue varchar(10) = 'safety';   
SELECT PATINDEX('%' + @MyValue + '%', DocumentSummary)   
FROM Production.Document  
WHERE DocumentNode = 0x7B40;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 ```
 ------------  
 22
 ```  
  

  
## <a name="see-also"></a>Voir aussi  
 [CHARINDEX &#40;Transact-SQL&#41;](../../t-sql/functions/charindex-transact-sql.md)  
 [LEN &#40;Transact-SQL&#41;](../../t-sql/functions/len-transact-sql.md)  
 [Types de données &#40;Transact-SQL&#41;](../../t-sql/data-types/data-types-transact-sql.md)   
 [Fonctions de chaîne &#40; Transact-SQL &#41;](../../t-sql/functions/string-functions-transact-sql.md)   
 [&#40; Caractère générique - caractères &#40; s &#41; Correspondance &#41; &#40; Transact-SQL &#41;](../../t-sql/language-elements/wildcard-character-s-to-match-transact-sql.md)   
 [&#40; Caractère générique - caractères &#40; s &#41; Pas de correspondance &#41; &#40; Transact-SQL &#41;](../../t-sql/language-elements/wildcard-character-s-not-to-match-transact-sql.md)   
 [_ &#40;Wildcard - Match One Character&#41; &#40;Transact-SQL&#41;](../../t-sql/language-elements/wildcard-match-one-character-transact-sql.md)   
 [Caractère de pourcentage &#40; Caractère générique - caractères &#40; s &#41; Correspondance &#41; &#40; Transact-SQL &#41;](../../t-sql/language-elements/percent-character-wildcard-character-s-to-match-transact-sql.md)  
  
  


