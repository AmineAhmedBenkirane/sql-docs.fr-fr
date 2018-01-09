---
title: Mtd (MDX) | Documents Microsoft
ms.custom: 
ms.date: 03/02/2016
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: MTD
dev_langs: kbMDX
helpviewer_keywords: Mtd function
ms.assetid: 07d8fd65-f9e6-42d4-868d-fccfac6bdb70
caps.latest.revision: "30"
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: f6969649d0ac405aca0766219b0df52b1c1ee244
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2018
---
# <a name="mtd-mdx"></a>Mtd (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Retourne un jeu des membres frères de même niveau qu'un membre donné, commençant par le premier frère et se terminant par le membre donné, conformément à la contrainte du niveau Year de la dimension Time.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Mtd( [ Member_Expression ] )  
```  
  
## <a name="arguments"></a>Arguments  
 *Argument*  
 Expression MDX (Multidimensional Expressions) valide qui retourne un membre.  
  
## <a name="remarks"></a>Notes   
 Si une expression de membre n’est pas spécifiée, la valeur par défaut est le membre actuel de la première hiérarchie avec un niveau de type *mois* dans la première dimension de type *temps* dans le groupe de mesures.  
  
 Le **Mtd** fonction est un raccourci pour la [PeriodsToDate](../mdx/periodstodate-mdx.md) lorsque la propriété Type de la hiérarchie d’attribut sur lequel est basé un niveau est la valeur de la fonction *mois*. Ce qui signifie que `Mtd(Member_Expression)` est équivalent à `PeriodsToDate(Month_Level_Expression,Member_Expression)`.  
  
## <a name="example"></a> Exemple  
 L’exemple suivant retourne la somme du mois pour les coûts de fret date pour les ventes sur Internet pour le mois de juillet 2002 jusqu'à la date du 20 juillet.  
  
```  
WITH MEMBER Measures.x AS SUM   
   (  
      MTD([Date].[Calendar].[Date].[July 20, 2002])  
     , [Measures].[Internet Freight Cost]  
     )  
SELECT Measures.x ON 0  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Somme &#40; MDX &#41;](../mdx/sum-mdx.md)   
 [Référence des fonctions MDX &#40; MDX &#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
