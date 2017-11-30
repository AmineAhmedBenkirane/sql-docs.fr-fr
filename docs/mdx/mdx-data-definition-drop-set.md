---
title: Instruction DROP SET (MDX) | Documents Microsoft
ms.custom: 
ms.date: 03/02/2016
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SET
- DROP
- DROP SET
- DROP_SET
dev_langs: kbMDX
helpviewer_keywords:
- DROP SET statement
- deleting named sets
- named sets [MDX]
- removing named sets
- dropping named sets
ms.assetid: bbc37afb-af8c-41df-ba81-12771beb1c41
caps.latest.revision: "35"
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: f2f8e2cb2db7f3ebc89e23f6b34e2bd85cd81c55
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/27/2017
---
# <a name="mdx-data-definition---drop-set"></a>Définition de données MDX - jeu de dépôt
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Supprime un jeu nommé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
DROP [SESSION] SET   
   <Cube_Reference>.Set_Name   
               [,<Cube_Reference>.Set_Name ...n]  
  
<Cube_Reference> ::= {CURRENTCUBE | Cube_Name}  
  
```  
  
## <a name="arguments"></a>Arguments  
 *Cube_Name*  
 Expression de chaîne valide qui précise le nom du cube.  
  
 *Set_Name*  
 Expression de chaîne valide qui précise le nom du jeu nommé à supprimer.  
  
## <a name="remarks"></a>Notes  
 Pour plus d’informations sur les jeux nommés, consultez [Création de jeux nommés à l’aide d’expressions MDX &#40;MDX&#41;](../analysis-services/multidimensional-models/mdx/mdx-named-sets-building-named-sets.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Instructions MDX de définition de données &#40; MDX &#41;](../mdx/mdx-data-definition-statements-mdx.md)  
  
  
