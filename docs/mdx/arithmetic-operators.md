---
title: Opérateurs arithmétiques | Documents Microsoft
ms.custom: ''
ms.date: 03/02/2016
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- kbMDX
helpviewer_keywords:
- arithmetic operators
ms.assetid: 1dff3e20-fe9d-4155-bf06-27d6458188e9
caps.latest.revision: 27
author: Minewiskan
ms.author: owend
manager: erikre
ms.openlocfilehash: 6b1a3685a5a4fded7824feb270007ae385ad8f69
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="arithmetic-operators"></a>Opérateurs arithmétiques
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Vous pouvez utiliser des opérateurs arithmétiques dans la syntaxe MDX (Multidimensional Expressions) pour tout calcul arithmétique, notamment une addition, une soustraction, une multiplication et une division.  
  
 MDX prend en charge les opérateurs arithmétiques répertoriés dans le tableau suivant.  
  
|Opérateur| Description|  
|--------------|-----------------|  
|[+ (Additionner)](../mdx/add-mdx.md)|Additionne deux nombres.|  
|[/ (Diviser)](../mdx/divide-mdx-operator-reference.md)|Divise un nombre par un autre.|  
|[* (Multiplier)](../mdx/multiply-mdx.md)|Multiplie deux nombres.|  
|[- (Soustraire)](../mdx/subtract-mdx.md)|Soustrait deux nombres.|  
|^ (Puissance) |Élève un nombre à une puissance égale à un autre nombre.|  
  
> [!NOTE]  
>  MDX n'inclut pas de fonction pour obtenir la racine carrée d'un nombre. Pour obtenir la racine carrée d'un nombre, élevez-le à la puissance 0.5 à l'aide de l'opérateur ^.  
  
## <a name="order-of-precedence"></a>Ordre de priorité  
 Les règles suivantes déterminent l'ordre de priorité des opérateurs arithmétiques dans une expression MDX :  
  
-   Lorsqu'une expression contient plusieurs opérateurs arithmétiques, MDX exécute d'abord la multiplication et la division, puis la soustraction et l'addition.  
  
-   Lorsque tous les opérateurs arithmétiques dans une expression ont le même niveau de priorité, l’ordre d’exécution est de gauche à droite.  
  
-   Les expressions entre parenthèses ont la priorité sur toutes les autres opérations.  
  
## <a name="see-also"></a>Voir aussi  
 [Référence des opérateurs MDX &#40;MDX&#41;](../mdx/mdx-operator-reference-mdx.md)   
 [Opérateurs &#40;syntaxe MDX&#41;](../mdx/operators-mdx-syntax.md)  
  
  
