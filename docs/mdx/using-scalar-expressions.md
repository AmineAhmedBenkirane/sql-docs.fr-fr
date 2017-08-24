---
title: "Utilisation d’Expressions scalaires | Documents Microsoft"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- kbMDX
helpviewer_keywords:
- scalar expressions
- expressions [MDX], scalar
ms.assetid: 4678b675-8fbd-4e5b-a519-d4cd1bb8c46a
caps.latest.revision: 25
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 67966680e10b35064c65a91f8b8da22a00fb17c4
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="using-scalar-expressions"></a>Utilisation d'expressions scalaires
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Dans la syntaxe MDX (Multidimensional Expressions), une expression scalaire est un élément qui, lorsqu'il est évalué, retourne une valeur unique au sein du contexte d'évaluation.  
  
 Dans la syntaxe MDX, les expressions scalaires comprennent des expressions de chaîne, numériques et de date.  
  
 Les expressions scalaires sont utilisées en général dans les définitions de membre calculé, étant donné que les membres calculés doivent renvoyer une valeur scalaire. La requête suivante affiche des exemples de membres calculés sur la dimension de mesures qui utilise différents types d'expression scalaire :  
  
 `WITH`  
  
 `MEMBER MEASURES.NumericValue AS 10`  
  
 `MEMBER MEASURES.NumericExpression AS 10 + 10`  
  
 `MEMBER MEASURES.NumericExpressionBasedOnMeasure AS [Measures].[Internet Sales Amount] + 10`  
  
 `MEMBER MEASURES.StringValue AS "10"`  
  
 `MEMBER MEASURES.ConcatenatedString AS "10" + "10"`  
  
 `MEMBER MEASURES.StringFunction AS MEASURES.CURRENTMEMBER.NAME`  
  
 `MEMBER MEASURES.TodaysDate AS NOW()`  
  
 `SELECT`  
  
 `{MEASURES.NumericValue,MEASURES.NumericExpression,MEASURES.NumericExpressionBasedOnMeasure,`  
  
 `MEASURES.StringValue, MEASURES.ConcatenatedString, MEASURES.StringFunction, MEASURES.TodaysDate}`  
  
 `ON COLUMNS`  
  
 `FROM [Adventure Works]`  
  
 Le seul type de données que peut retourne une mesure, calculée ou autre, est le type OLE Variant. Par conséquent, vous devrez parfois effectuer un cast d'une valeur de mesure en un type particulier pour obtenir le comportement attendu. La requête suivante en donne une illustration :  
  
```  
WITH  
//Two calculated measures that return strings  
MEMBER MEASURES.NumericString1 AS "10"  
MEMBER MEASURES.NumericString2 AS "10"  
//In this case, the + operator acts to concatenate the strings  
MEMBER MEASURES.Concatenation AS MEASURES.NumericString1 + MEASURES.NumericString2  
//Casting one value to an integer with the CINT function causes the second measure  
//to be treated as an integer too, so that the + operator now acts to add the values  
MEMBER MEASURES.Addition AS CINT(MEASURES.NumericString1) + MEASURES.NumericString2  
SELECT  
{MEASURES.NumericString1,MEASURES.NumericString2,MEASURES.Concatenation,MEASURES.Addition }  
ON COLUMNS  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions &#40; MDX &#41;](../mdx/expressions-mdx.md)  
  
  

