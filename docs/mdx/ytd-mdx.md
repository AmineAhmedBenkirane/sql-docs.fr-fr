---
title: YTD (MDX) | Documents Microsoft
ms.custom: ''
ms.date: 03/02/2016
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- YTD
dev_langs:
- kbMDX
helpviewer_keywords:
- Ytd function
ms.assetid: b77fdba2-d4a9-4271-8c21-c1f12eba526d
caps.latest.revision: 32
author: Minewiskan
ms.author: owend
manager: erikre
ms.openlocfilehash: b647c31febd5ef06b8cb2e6f808e296518f98af6
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="ytd-mdx"></a>Ytd (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Retourne un jeu de frères membres d’un même niveau qu’un membre donné, en commençant par le premier frère et se terminant par le membre donné, en tant que contrainte par la *année* au niveau de la dimension Time.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Ytd( [ Member_Expression ] )  
```  
  
## <a name="arguments"></a>Arguments  
 *Argument*  
 Expression MDX (Multidimensional Expressions) valide qui retourne un membre.  
  
## <a name="remarks"></a>Notes  
 Si une expression de membre n’est pas spécifiée, la valeur par défaut est le membre actuel de la première hiérarchie avec un niveau de type *ans* dans la première dimension de type *temps* dans le groupe de mesures.  
  
 Le **Ytd** fonction est un raccourci pour la [PeriodsToDate](../mdx/periodstodate-mdx.md) fonction où la propriété Type de la hiérarchie d’attribut sur lequel repose le niveau est définie à *ans*. Ce qui signifie que `Ytd(Member_Expression)` est équivalent à `PeriodsToDate(Year_Level_Expression,Member_Expression)`. Notez que cette fonction ne fonctionne pas lorsque la propriété Type a la valeur *FiscalYears*.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant retourne la somme de la `Measures.[Order Quantity]` membre, agrégé sur les huit premiers mois de l’année civile 2003 qui sont contenus dans le `Date` dimension, à partir de la **Adventure Works** cube.  
  
```  
WITH MEMBER [Date].[Calendar].[First8MonthsCY2003] AS  
    Aggregate(  
        YTD([Date].[Calendar].[Month].[August 2003])  
    )  
SELECT   
    [Date].[Calendar].[First8MonthsCY2003] ON COLUMNS,  
    [Product].[Category].Children ON ROWS  
FROM  
    [Adventure Works]  
WHERE  
    [Measures].[Order Quantity]  
```  
  
 **YTD** est fréquemment utilisé en association avec aucun paramètre spécifié, ce qui signifie que la [CurrentMember &#40;MDX&#41; ](../mdx/currentmember-mdx.md) fonction affichera un total cumulatif d’year-to-date dans un rapport, comme indiqué dans les requête suivante :  
  
 `WITH MEMBER MEASURES.YTDDEMO AS`  
  
 `AGGREGATE(YTD(), [Measures].[Internet Sales Amount])`  
  
 `SELECT {[Measures].[Internet Sales Amount], MEASURES.YTDDEMO} ON 0,`  
  
 `[Date].[Calendar].MEMBERS ON 1`  
  
 `FROM [Adventure Works]`  
  
## <a name="see-also"></a>Voir aussi  
 [Référence des fonctions MDX & #40 ; MDX & #41 ;](../mdx/mdx-function-reference-mdx.md)  
  
  
