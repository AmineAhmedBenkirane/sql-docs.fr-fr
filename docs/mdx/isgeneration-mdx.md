---
title: IsGeneration (MDX) | Documents Microsoft
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
- ISGENERATION
dev_langs:
- kbMDX
helpviewer_keywords:
- IsGeneration function
ms.assetid: fd11d2e0-d81d-45af-ac45-c98634d05550
caps.latest.revision: 32
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: bdb02d424cb58aab2e8af8695b9751e495ba7175
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="isgeneration-mdx"></a>IsGeneration (MDX)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../includes/tsql-appliesto-ss2008-all-md.md)]

  Retourne une valeur indiquant si un membre spécifié est dans une génération spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
IsGeneration(Member_Expression, Generation_Number)   
```  
  
## <a name="arguments"></a>Arguments  
 *Argument*  
 Expression MDX (Multidimensional Expressions) valide qui retourne un membre.  
  
 *Generation_Number*  
 Expression numérique valide qui précise la génération par rapport à laquelle le membre spécifié est évalué.  
  
## <a name="remarks"></a>Notes  
 Le **IsGeneration** fonction renvoie **true** si le membre spécifié se trouve dans le numéro de génération spécifiée. Sinon, la fonction retourne **false**. Également, si le membre spécifié prend la valeur d’un membre vide, le **IsGeneration** fonction renvoie **false**.  
  
 Pour des besoins d'indexation des générations, les membres feuilles portent l'index de génération 0. Pour déterminer l'index de génération des membres non feuilles, prenez tout d'abord l'index de génération le plus élevé à partir de l'union de tous les membres enfants du membre spécifié, puis ajoutez 1 à cet index. En raison du mode de détermination de l'index de génération des membres non feuilles, un membre non feuille spécifique peut appartenir à plusieurs générations.  
  
## <a name="example"></a>Exemple  
 L'exemple ci-dessous retourne la valeur TRUE si [Date].[Fiscal].CurrentMember appartient à la deuxième génération :  
  
 `WITH MEMBER MEASURES.ISGENERATIONDEMO AS`  
  
 `IsGeneration([Date].[Fiscal].CURRENTMEMBER, 2)`  
  
 `SELECT {MEASURES.ISGENERATIONDEMO} ON 0,`  
  
 `[Date].[Fiscal].MEMBERS ON 1`  
  
 `FROM [Adventure Works]`  
  
## <a name="see-also"></a>Voir aussi  
 [Référence des fonctions MDX &#40; MDX &#41;](../mdx/mdx-function-reference-mdx.md)  
  
  

