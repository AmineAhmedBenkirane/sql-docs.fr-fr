---
title: "Opérateurs arithmétiques | Documents Microsoft"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
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
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: bc3adf599f92a74dd996a0ef090f6f42ab1fba0d
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="arithmetic-operators"></a>Opérateurs arithmétiques
[!INCLUDE[tsql-appliesto-ss2008-all_md](../includes/tsql-appliesto-ss2008-all-md.md)]

  Vous pouvez utiliser des opérateurs arithmétiques dans la syntaxe MDX (Multidimensional Expressions) pour tout calcul arithmétique, notamment une addition, une soustraction, une multiplication et une division.  
  
 MDX prend en charge les opérateurs arithmétiques répertoriés dans le tableau suivant.  
  
|Opérateur| Description|  
|--------------|-----------------|  
|[+ (Addition)](../mdx/add-mdx.md)|Additionne deux nombres.|  
|[/ (Division)](../mdx/divide-mdx-operator-reference.md)|Divise un nombre par un autre.|  
|[* (Multiplication)](../mdx/multiply-mdx.md)|Multiplie deux nombres.|  
|[-(Soustraction)](../mdx/subtract-mdx.md)|Soustrait deux nombres.|  
|^ (Puissance) |Élève un nombre à une puissance égale à un autre nombre.|  
  
> [!NOTE]  
>  MDX n'inclut pas de fonction pour obtenir la racine carrée d'un nombre. Pour obtenir la racine carrée d'un nombre, élevez-le à la puissance 0.5 à l'aide de l'opérateur ^.  
  
## <a name="order-of-precedence"></a>Ordre de priorité  
 Les règles suivantes déterminent l'ordre de priorité des opérateurs arithmétiques dans une expression MDX :  
  
-   Lorsqu'une expression contient plusieurs opérateurs arithmétiques, MDX exécute d'abord la multiplication et la division, puis la soustraction et l'addition.  
  
-   Lorsque tous les opérateurs arithmétiques dans une expression ont le même niveau de priorité, l’ordre d’exécution est de gauche à droite.  
  
-   Les expressions entre parenthèses ont la priorité sur toutes les autres opérations.  
  
## <a name="see-also"></a>Voir aussi  
 [Référence des opérateurs MDX &#40; MDX &#41;](../mdx/mdx-operator-reference-mdx.md)   
 [Opérateurs &#40; La syntaxe MDX &#41;](../mdx/operators-mdx-syntax.md)  
  
  

