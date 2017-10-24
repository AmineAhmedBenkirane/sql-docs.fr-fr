---
title: "Compound, opérateurs (Transact-SQL) | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- Azure SQL Database
- SQL Server (starting with 2008)
dev_langs:
- TSQL
helpviewer_keywords:
- compound operators
- compound operators, described
ms.assetid: 5072fe91-02d3-42a7-831f-756eff714a17
caps.latest.revision: 9
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: On Demand
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 2e5fde8cd4265359722f33400d834b0a301718ef
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="compound-operators-transact-sql"></a>Opérateurs composés (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Les opérateurs composés exécutent une opération particulière et affectent une valeur d'origine au résultat de l'opération. Par exemple, si une variable @x égal à 35, puis @x += 2 prend la valeur d’origine de @x, ajouter 2 et des jeux @x cette nouvelle valeur (37).  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] fournit les types d'opérateurs composés suivants :  
  
|Opérateur|Lien vers des informations  supplémentaires|Action|  
|--------------|------------------------------|------------|  
|+=|[+= &#40; Ajouter égal &#41; &#40; Transact-SQL &#41;](../../t-sql/language-elements/add-equals-transact-sql.md)|Ajoute un montant à la valeur d'origine et affecte la valeur d'origine au résultat.|  
|-=|[-= &#40; Soustraire égal &#41; &#40; Transact-SQL &#41;](../../t-sql/language-elements/subtract-equals-transact-sql.md)|Soustrait un montant de la valeur d'origine et affecte la valeur d'origine au résultat.|  
|*=|[&#42; = &#40; Multiplier égal &#41; &#40; Transact-SQL &#41;](../../t-sql/language-elements/multiply-equals-transact-sql.md)|Multiplie par un montant et affecte la valeur d'origine au résultat.|  
|/=|[&#40; diviser égal &#41; &#40; Transact-SQL &#41;](../../t-sql/language-elements/divide-equals-transact-sql.md)|Divise par un montant et affecte la valeur d'origine au résultat.|  
|%=|[Modulo égal &#40; Transact-SQL &#41;](../../t-sql/language-elements/modulo-equals-transact-sql.md)|Divise par un montant et affecte la valeur d'origine au modulo.|  
|&=|[& = &#40; ÉGAL au niveau du bit AND &#41; &#40; Transact-SQL &#41;](../../t-sql/language-elements/bitwise-and-equals-transact-sql.md)|Effectue une opération de bits AND et affecte la valeur d'origine au résultat.|  
|^=|[^ = &#40; Opérateur de bits OR exclusif est égale à &#41; &#40; Transact-SQL &#41;](../../t-sql/language-elements/bitwise-exclusive-or-equals-transact-sql.md)|Effectue une opération de bits OR exclusive et affecte la valeur d'origine au résultat.|  
|&#124;=|[&#124; = &#40; OR au niveau du bit est égal à &#41; &#40; Transact-SQL &#41;](../../t-sql/language-elements/bitwise-or-equals-transact-sql.md)|Effectue une opération de bits OR et affecte la valeur d'origine au résultat.|  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
expression operator expression  
```  
  
## <a name="arguments"></a>Arguments  
 *expression*  
 Valide [expression](../../t-sql/language-elements/expressions-transact-sql.md) de tout des données de type de catégorie numérique.  
  
## <a name="result-types"></a>Types des résultats  
 Retourne le type de données de l'argument ayant la priorité la plus élevée. Pour plus d’informations, consultez [Priorités des types de données &#40;Transact-SQL&#41;](../../t-sql/data-types/data-type-precedence-transact-sql.md).  
  
## <a name="remarks"></a>Notes  
 Pour plus d'informations, consultez les rubriques relatives à chaque opérateur.  
  
## <a name="examples"></a>Exemples  
 Les exemples suivants illustrent des opérations composées.  
  
```  
DECLARE @x1 int = 27;  
SET @x1 += 2 ;  
SELECT @x1 AS Added_2;  
  
DECLARE @x2 int = 27;  
SET @x2 -= 2 ;  
SELECT @x2 AS Subtracted_2;  
  
DECLARE @x3 int = 27;  
SET @x3 *= 2 ;  
SELECT @x3 AS Multiplied_by_2;  
  
DECLARE @x4 int = 27;  
SET @x4 /= 2 ;  
SELECT @x4 AS Divided_by_2;  
  
DECLARE @x5 int = 27;  
SET @x5 %= 2 ;  
SELECT @x5 AS Modulo_of_27_divided_by_2;  
  
DECLARE @x6 int = 9;  
SET @x6 &= 13 ;  
SELECT @x6 AS Bitwise_AND;  
  
DECLARE @x7 int = 27;  
SET @x7 ^= 2 ;  
SELECT @x7 AS Bitwise_Exclusive_OR;  
  
DECLARE @x8 int = 27;  
SET @x8 |= 2 ;  
SELECT @x8 AS Bitwise_OR;  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Opérateurs &#40; Transact-SQL &#41;](../../t-sql/language-elements/operators-transact-sql.md)   
 [Opérateurs de bits &#40; Transact-SQL &#41;](../../t-sql/language-elements/bitwise-operators-transact-sql.md)  
  
  

