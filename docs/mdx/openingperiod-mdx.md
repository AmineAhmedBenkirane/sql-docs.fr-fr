---
title: OpeningPeriod (MDX) | Documents Microsoft
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
- OPENINGPERIOD
dev_langs:
- kbMDX
helpviewer_keywords:
- OpeningPeriod function
ms.assetid: bebf55cf-e5c6-42b1-98f2-1d6e54093d4c
caps.latest.revision: 33
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 30100b2762d3365c1599e665db54e2446e392fb3
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="openingperiod-mdx"></a>OpeningPeriod (MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retourne le premier frère parmi les descendants d'un niveau spécifié, éventuellement à un membre spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
OpeningPeriod( [ Level_Expression [ , Member_Expression ] ] )  
```  
  
## <a name="arguments"></a>Arguments  
 *Level_Expression*  
 Expression MDX (Multidimensional Expressions) valide qui retourne un niveau.  
  
 *Argument*  
 Expression MDX (Multidimensional Expressions) valide qui retourne un membre.  
  
## <a name="remarks"></a>Notes  
 Cette fonction a principalement été conçue pour être exploitée avec la dimension Time (dimension de temps) mais peut également être utilisée avec n'importe quelle dimension.  
  
-   Si une expression de niveau est spécifiée, la **OpeningPeriod** fonction utilise la hiérarchie qui contient le niveau spécifié et retourne le premier frère parmi les descendants du membre par défaut au niveau spécifié.  
  
-   Si une expression de niveau et une expression de membre sont spécifiés, la **OpeningPeriod** fonction retourne le premier frère parmi les descendants du membre spécifié au niveau spécifié dans la hiérarchie contenant le niveau spécifié.  
  
-   Si une expression de niveau, ni une expression de membre est spécifiée, la **OpeningPeriod** fonction utilise le niveau par défaut et le membre de la dimension avec un type de temps.  
  
> [!NOTE]  
>  Le [ClosingPeriod](../mdx/closingperiod-mdx.md) fonction est similaire à la **OpeningPeriod** de fonction, à ceci près que le **ClosingPeriod** fonction retourne le dernier frère et non le premier.  
  
## <a name="examples"></a>Exemples  
 L'exemple ci-dessous retourne la valeur de la mesure par défaut pour le membre FY2002 de la dimension Date (dimension de type Time). Ce membre est retourné parce que le niveau Fiscal Year (année fiscale) est le premier descendant du niveau [All], la hiérarchie Fiscal est la hiérarchie par défaut parce qu'elle est la première hiérarchie définie par l'utilisateur dans la collection des hiérarchies, et le membre FY2002 est le premier frère de cette hiérarchie à ce niveau.  
  
```  
SELECT OpeningPeriod() ON 0  
FROM [Adventure Works]  
  
```  
  
 L'exemple suivant retourne la valeur de la mesure par défaut pour le membre July 1, 2001 (1er juillet 2001) au niveau Date.Date.Date de la hiérarchie d'attribut Date.Date. Ce membre est le premier frère du descendant du niveau [All] dans la hiérarchie d'attribut Date.Date.  
  
```  
SELECT OpeningPeriod([Date].[Date].[Date]) ON 0  
FROM [Adventure Works]  
  
```  
  
 L'exemple ci-après retourne la valeur de la mesure par défaut pour le membre January, 2003 (janvier 2003) qui est le premier frère du descendant du membre 2003 au niveau Year (année) dans la hiérarchie définie par l'utilisateur Calendar (calendrier).  
  
```  
SELECT OpeningPeriod([Date].[Calendar].[Month],[Date].[Calendar].[Calendar Year].&[2003]) ON 0  
FROM [Adventure Works]  
  
```  
  
 L'exemple ci-après retourne la valeur de la mesure par défaut pour le membre July, 2002 (juillet 2002) qui est le premier frère du descendant du membre 2003 au niveau Year (année) dans la hiérarchie définie par l'utilisateur Fiscal.  
  
```  
SELECT OpeningPeriod([Date].[Fiscal].[Month],[Date].[Fiscal].[Fiscal Year].&[2003]) ON 0  
FROM [Adventure Works]  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [TopCount &#40; MDX &#41;](../mdx/topcount-mdx.md)   
 [Référence des fonctions MDX &#40; MDX &#41;](../mdx/mdx-function-reference-mdx.md)   
 [FirstSibling &#40; MDX &#41;](../mdx/firstsibling-mdx.md)  
  
  

