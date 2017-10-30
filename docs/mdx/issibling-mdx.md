---
title: IsSibling (MDX) | Documents Microsoft
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
- ISSIBLING
dev_langs:
- kbMDX
helpviewer_keywords:
- IsSibling function
ms.assetid: 12f302f0-141e-4ec0-ad5f-329aade17a4d
caps.latest.revision: 31
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: bc48def38a353f94531aad4f56c659f959caffb2
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="issibling-mdx"></a>IsSibling (MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retourne une valeur indiquant si un membre spécifié est un frère d'un autre membre spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
IsSibling(Member_Expression1, Member_Expression2)   
```  
  
## <a name="arguments"></a>Arguments  
 *Expression_membre1*  
 Expression MDX (Multidimensional Expressions) valide qui retourne un membre.  
  
 *Expression_membre2*  
 Expression MDX (Multidimensional Expressions) valide qui retourne un membre.  
  
## <a name="remarks"></a>Notes  
 Le **IsSibling** fonction renvoie **true** si le premier membre spécifié est un frère du deuxième membre spécifié. Sinon, la fonction retourne **false**.  
  
## <a name="example"></a>Exemple  
 L'exemple suivant retourne TRUE si le membre actuel sur la hiérarchie Fiscal de la dimension Date est un frère de July 2002 :  
  
 `WITH MEMBER MEASURES.ISSIBLINGDEMO AS`  
  
 `IsSibling([Date].[Fiscal].CURRENTMEMBER, [Date].[Fiscal].[Month].&[2002]&[7])`  
  
 `SELECT {MEASURES.ISSIBLINGDEMO} ON 0,`  
  
 `[Date].[Fiscal].MEMBERS ON 1`  
  
 `FROM [Adventure Works]`  
  
## <a name="see-also"></a>Voir aussi  
 [Référence des fonctions MDX &#40; MDX &#41;](../mdx/mdx-function-reference-mdx.md)  
  
  

