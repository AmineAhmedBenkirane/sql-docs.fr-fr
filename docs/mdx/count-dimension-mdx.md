---
title: Nombre (Dimension) (MDX) | Documents Microsoft
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
- COUNT
dev_langs:
- kbMDX
helpviewer_keywords:
- Count function [MDX]
ms.assetid: 4b9c52f6-5bb0-401a-947c-e14134558b4a
caps.latest.revision: 32
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 42c607f44e10c35c41e302b858406f0dafc57c9c
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="count-dimension-mdx"></a>Count (Dimension) (MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retourne le nombre de hiérarchies dans un cube.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Dimensions.Count   
```  
  
## <a name="remarks"></a>Notes  
 Retourne le nombre de hiérarchies d'un cube, notamment la hiérarchie `[Measures].[Measures]`.  
  
## <a name="example"></a>Exemple  
 L'exemple ci-dessous retourne le nombre de hiérarchies dans le cube Adventure Works.  
  
```  
WITH MEMBER measures.X AS  
  dimensions.count   
SELECT Measures.X ON 0  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Nombre &#40; Tuple &#41; &#40; MDX &#41;](../mdx/count-tuple-mdx.md)   
 [Nombre &#40; Niveaux de hiérarchie &#41; &#40; MDX &#41;](../mdx/count-hierarchy-levels-mdx.md)   
 [Nombre &#40; Définir le &#41; &#40; MDX &#41;](../mdx/count-set-mdx.md)   
 [Référence des fonctions MDX &#40; MDX &#41;](../mdx/mdx-function-reference-mdx.md)  
  
  

