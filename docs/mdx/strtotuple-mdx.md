---
title: StrToTuple (MDX) | Documents Microsoft
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
- STRTOTUPLE
dev_langs:
- kbMDX
helpviewer_keywords:
- StrToTuple function
ms.assetid: e162cc01-cddd-4654-baab-d73abdc33b80
caps.latest.revision: 32
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: e2ca9d105bf04c91fd2c65bea74f92a0d0ef1edd
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="strtotuple-mdx"></a>StrToTuple (MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retourne le tuple spécifié par une chaîne au format MDX (Multidimensional Expressions).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
StrToTuple(Tuple_Specification [,CONSTRAINED] )   
```  
  
## <a name="arguments"></a>Arguments  
 *Tuple_Specification*  
 Expression de chaîne valide qui spécifie, directement ou indirectement, un tuple.  
  
## <a name="remarks"></a>Notes  
 Le **StrToTuple** fonction retourne le jeu spécifié. Le **StrToTuple** fonction est généralement utilisée avec les fonctions définies par l’utilisateur pour retourner un tuple spécifié à partir d’une fonction externe vers une instruction MDX.  
  
-   En cas d'utilisation de l'indicateur CONSTRAINED, le tuple spécifié doit contenir des noms de membres qualifiés ou non qualifiés. Cet indicateur est employé pour réduire les risques d'attaques par injection au travers de la chaîne spécifiée. Si une chaîne qui ne peut être directement résolue à des noms de membres qualifiés ou non qualifiés est fournie, l'erreur suivante s'affiche : « Les restrictions imposées par l'indicateur CONSTRAINED dans la fonction STRTOTUPLE n'ont pas été respectées. »  
  
-   Si l'indicateur CONSTRAINED n'est pas utilisé, vous pouvez résoudre le tuple spécifié à une expression MDX valide qui retourne un tuple.  
  
## <a name="examples"></a>Exemples  
 L'exemple ci-dessous retourne la mesure Reseller Sales Amount du membre Bayern à l'aide de la fonction pour l'année civile 2004. Le tuple spécifié fourni contient une expression de tuple MDX valide.  
  
```  
SELECT StrToTuple ('([Geography].[State-Province].[Bayern],[Date].[Calendar Year].[CY 2004], [Measures].[Reseller Sales Amount])')  
ON 0  
FROM [Adventure Works]  
  
```  
  
 L'exemple ci-dessous retourne la mesure Reseller Sales Amount du membre Bayern à l'aide de la fonction pour l'année civile 2004. Le tuple spécifié fourni contient des noms de membres qualifiés, conformément aux exigences de l'indicateur CONSTRAINED.  
  
```  
SELECT StrToTuple ('([Geography].[State-Province].[Bayern],[Date].[Calendar Year].[CY 2004], [Measures].[Reseller Sales Amount])', CONSTRAINED)  
ON 0  
FROM [Adventure Works]  
  
```  
  
 L'exemple ci-dessous retourne la mesure Reseller Sales Amount du membre Bayern à l'aide de la fonction pour l'année civile 2004. Le tuple spécifié fourni contient une expression de tuple MDX valide.  
  
```  
SELECT StrToTuple ('([Geography].[State-Province].[Bayern],[Date].[Calendar Year].&[2003].NEXTMEMBER, [Measures].[Reseller Sales Amount])')  
ON 0  
FROM [Adventure Works]  
  
```  
  
 L'exemple ci-dessous retourne une erreur liée à l'indicateur CONSTRAINED. Tandis que le tuple spécifié fournit une expression de tuple MDX valide, l'indicateur CONSTRAINED exige l'usage de noms de membres qualifiés ou non qualifiés dans le tuple spécifié.  
  
```  
SELECT StrToTuple ('([Geography].[State-Province].[Bayern],[Date].[Calendar Year].&[2003].NEXTMEMBER, [Measures].[Reseller Sales Amount])', CONSTRAINED)  
ON 0  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Référence des fonctions MDX &#40; MDX &#41;](../mdx/mdx-function-reference-mdx.md)  
  
  

