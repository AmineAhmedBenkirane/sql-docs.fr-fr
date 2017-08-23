---
title: ParallelPeriod (MDX) | Documents Microsoft
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- PARALLELPERIOD
dev_langs:
- kbMDX
helpviewer_keywords:
- ParallelPeriod function
ms.assetid: 9c87f5a6-5694-46f1-9890-bd9705190ea7
caps.latest.revision: 31
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 294bab2d1403b6f6195a0888c731c95cfd938df8
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="parallelperiod-mdx"></a>ParallelPeriod (MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retourne un membre d'une période antérieure dans la même position relative que le membre spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
ParallelPeriod( [ Level_Expression [ ,Index [ , Member_Expression ] ] ] )  
```  
  
## <a name="arguments"></a>Arguments  
 *Level_Expression*  
 Expression MDX (Multidimensional Expressions) valide qui retourne un niveau.  
  
 *Index*  
 Expression numérique valide qui spécifie le nombre de périodes parallèles à décaler.  
  
 *Argument*  
 Expression MDX (Multidimensional Expressions) valide qui retourne un membre.  
  
## <a name="remarks"></a>Notes  
 Bien que similaire à la [Cousin](../mdx/cousin-mdx.md) (fonction), la **ParallelPeriod** fonction est davantage liée à la série chronologique. Le **ParallelPeriod** fonction prend l’ancêtre du membre spécifié au niveau spécifié, recherche le frère de l’ancêtre avec le décalage spécifié et enfin retourne la période parallèle du membre spécifié parmi les descendants du frère.  
  
 Le **ParallelPeriod** fonction a les valeurs par défaut suivantes :  
  
-   Si une expression de niveau, ni une expression de membre est spécifiée, la valeur du membre par défaut est le membre actuel de la première hiérarchie sur la première dimension avec un type de *temps* dans le groupe de mesures.  
  
-   Si une expression de niveau est spécifiée, mais une expression de membre n’est pas spécifiée, la valeur du membre par défaut est *Level_Expression*. **Hierarchy.CurrentMember**.  
  
-   La valeur d'index par défaut est 1.  
  
-   Le niveau par défaut est celui du parent du membre spécifié.  
  
 Le **ParallelPeriod** fonction est équivalente à l’instruction MDX suivante :  
  
 `Cousin(Member_Expression, Ancestor(Member_Expression, Level_Expression) .Lag(Numeric_Expression))`  
  
## <a name="example"></a>Exemple  
 L'exemple ci-dessous retourne la période parallèle du mois d'octobre 2003 avec un décalage de trois périodes en se basant sur le niveau du trimestre, ce qui retourne le mois de janvier 2003.  
  
```  
SELECT ParallelPeriod ([Date].[Calendar].[Calendar Quarter]  
   , 3  
   , [Date].[Calendar].[Month].[October 2003])  
   ON 0  
   FROM [Adventure Works]  
```  
  
 L'exemple ci-dessous retourne la période parallèle du mois d'octobre 2003 avec un décalage de trois périodes en se basant sur le niveau du semestre, ce qui retourne le mois d'avril 2002.  
  
```  
SELECT ParallelPeriod ([Date].[Calendar].[Calendar Semester]  
   , 3  
   , [Date].[Calendar].[Month].[October 2003])  
   ON 0  
   FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Référence des fonctions MDX &#40; MDX &#41;](../mdx/mdx-function-reference-mdx.md)  
  
  

