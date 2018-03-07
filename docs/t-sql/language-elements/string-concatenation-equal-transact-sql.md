---
title: "+= (Concaténation de chaînes et d’assignation) (Transact-SQL) | Documents Microsoft"
ms.custom: 
ms.date: 12/07/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: t-sql|language-elements
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- concatenate strings
- string concatenation
- += (concatenate operator)
ms.assetid: 4aaeaab7-9b2b-48e0-8487-04ed672ebcb1
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: a1e42125e49b0191b4ccdcc3628b75d025cccb6a
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="-string-concatenation-assignment-transact-sql"></a>+= (Affectation de concaténation de chaîne) (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Concatène deux chaînes et définit la chaîne obtenue à l'aide du résultat de l'opération. Par exemple, si une variable @x égal à « Adventure », puis @x += 'Works' prend la valeur d’origine de @x, ajoute « Works » à la chaîne et définit @x cette nouvelle valeur 'AdventureWorks'.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
expression += expression  
```  
  
## <a name="arguments"></a>Arguments  
 *expression*  
 Valide [expression](../../t-sql/language-elements/expressions-transact-sql.md) d’un des types de données caractères.  
  
## <a name="result-types"></a>Types des résultats  
 Retourne le type de données défini pour la variable.  
  
## <a name="remarks"></a>Notes  
 Définissez @v1 += 'expression' est équivalent au jeu @v1 = @v1 + ('expression'). En outre, définissez @v1 = @v2 + @v3 + @v4 est équivalent au jeu @v1 = (@v2 + @v3) + @v4.  
  
 L'opérateur += ne peut pas être utilisé sans une variable. Par exemple, le code suivant génère une erreur :  
  
```  
SELECT 'Adventure' += 'Works'  
```  
  
## <a name="examples"></a>Exemples  
### <a name="a-concatenation-using--operator"></a>A. Concaténation à l’aide de += (opérateur)
 L'exemple suivant est une concaténation basée sur l'opérateur `+=`.  
  
```  
DECLARE @v1 varchar(40);  
SET @v1 = 'This is the original.';  
SET @v1 += ' More text.';  
PRINT @v1;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `This is the original. More text.`  
  
### <a name="b-order-of-evaluation-while-concatenating-using--operator"></a>B. Ordre d’évaluation lors de la concaténation à l’aide de += (opérateur)
L’exemple suivant concatène plusieurs chaînes pour former une chaîne longue et tente ensuite de calculer la longueur de la chaîne finale. Cet exemple illustre les règles de commande et la troncature d’évaluation, lors de l’utilisation de l’opérateur de concaténation. 

```
DECLARE @x varchar(4000) = replicate('x', 4000)
DECLARE @z varchar(8000) = replicate('z',8000)
DECLARE @y varchar(max);
 
SET @y = '';
SET @y += @x + @z;
SELECT LEN(@y) AS Y; -- 8000
 
SET @y = '';
SET @y = @y + @x + @z;
SELECT LEN(@y) AS Y; -- 12000
 
SET @y = '';
SET @y = @y +(@x + @z);
SELECT LEN(@y) AS Y; -- 8000
-- or
SET @y = '';
SET @y = @x + @z + @y;
SELECT LEN(@y) AS Y; -- 8000
GO
```
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 ```
 Y       
 ------- 
 8000 
  
 (1 row(s) affected) 
  
    
 Y       
 ------- 
 12000 
  
 (1 row(s) affected) 

 Y       
 ------- 
 8000 
  
 (1 row(s) affected) 
  
 Y       
 ------- 
 8000 
  
 (1 row(s) affected)
  ```   
   
## <a name="see-also"></a>Voir aussi  
 [Operators &#40;Transact-SQL&#41;](../../t-sql/language-elements/operators-transact-sql.md)   
 [+= &#40;Add Assignment&#41; &#40;Transact-SQL&#41;](../../t-sql/language-elements/add-equals-transact-sql.md)   
 [+ &#40;String Concatenation&#41; &#40;Transact-SQL&#41;](../../t-sql/language-elements/string-concatenation-transact-sql.md)  
  
  
