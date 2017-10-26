---
title: "Opérateurs de comparaison (DMX) | Documents Microsoft"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- DMX
helpviewer_keywords:
- comparison operators [DMX]
ms.assetid: eea3cf90-9683-4453-b1f3-da740f3a4885
caps.latest.revision: 17
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 92362f5158b23b0425030092fe7b9372a08b13ca
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="operators---comparison"></a>Opérateurs de comparaison-
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Vous pouvez utiliser des opérateurs de comparaison avec des données scalaires dans n’importe quelle expression Extensions DMX (Data Mining) dans [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]. Les opérateurs de comparaison sont évalués comme des booléens ; ils renvoient la valeur TRUE ou FALSE en fonction du résultat de la condition testée.  
  
 Le tableau ci-dessous identifie les opérateurs de comparaison pris en charge par DMX.  
  
|Opérateur| Description|  
|--------------|-----------------|  
|[&#60; &#40; Inférieur à &#41; &#40; DMX &#41;](../dmx/less-than-dmx.md)|Pour les arguments qui donnent comme résultat une valeur Non NULL, retourne TRUE si la valeur de l'argument de gauche est inférieure à la valeur de l'argument de droite ; dans le cas contraire, retourne FALSE. Si l'un ou l'autre ou les deux arguments donnent comme résultat une valeur NULL, l'opérateur retourne une valeur NULL.|  
|[&#62; &#40; Supérieur à &#41; &#40; DMX &#41;](../dmx/greater-than-dmx.md)|Pour les arguments qui donnent comme résultat une valeur Non NULL, retourne TRUE si la valeur de l'argument de gauche est supérieure à la valeur de l'argument de droite ; dans le cas contraire, retourne FALSE. Si l'un ou l'autre ou les deux arguments donnent comme résultat une valeur NULL, l'opérateur retourne une valeur NULL.|  
|[= &#40; Égal à &#41; &#40; DMX &#41;](../dmx/equal-to-dmx.md)|Pour les arguments qui donnent comme résultat une valeur Non NULL, retourne TRUE si la valeur de l'argument de gauche est égale à la valeur de l'argument de droite ; dans le cas contraire, retourne FALSE. Si l'un ou l'autre ou les deux arguments donnent comme résultat une valeur NULL, l'opérateur retourne une valeur NULL.|  
|[&#60; &#62; &#40; Non égal à &#41; &#40; DMX &#41;](../dmx/not-equal-to-dmx.md)|Pour les arguments qui donnent comme résultat une valeur Non NULL, retourne TRUE si la valeur de l'argument de gauche n'est pas égale à la valeur de l'argument de droite ; dans le cas contraire, retourne FALSE. Si l'un ou l'autre ou les deux arguments donnent comme résultat une valeur NULL, l'opérateur retourne une valeur NULL.|  
|[&#60; = &#40; Inférieur ou égal à &#41; &#40; DMX &#41;](../dmx/less-than-or-equal-to-dmx.md)|Pour les arguments qui donnent comme résultat une valeur Non NULL, retourne TRUE si la valeur de l'argument de gauche est inférieure ou égale à la valeur de l'argument de droite ; dans le cas contraire, retourne FALSE. Si l'un ou l'autre ou les deux arguments donnent comme résultat une valeur NULL, l'opérateur retourne une valeur NULL.|  
|[&#62; = &#40; Supérieur ou égal à &#41; &#40; DMX &#41;](../dmx/greater-than-or-equal-to-dmx.md)|Pour les arguments qui donnent comme résultat une valeur Non NULL, retourne TRUE si la valeur de l'argument de gauche est supérieure ou égale à la valeur de l'argument de droite ; dans le cas contraire, retourne FALSE. Si l'un ou l'autre ou les deux arguments donnent comme résultat une valeur NULL, l'opérateur retourne une valeur NULL.|  
  
 Vous pouvez également utiliser les opérateurs de comparaison dans les instructions et les fonctions DMX pour rechercher une condition.  
  
## <a name="see-also"></a>Voir aussi  
 [Les Extensions d’exploration de données &#40; DMX &#41; Référence](../dmx/data-mining-extensions-dmx-reference.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Référence de fonction](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Référence des opérateurs](../dmx/data-mining-extensions-dmx-operator-reference.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Référence des instructions](../dmx/data-mining-extensions-dmx-statements.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Conventions de syntaxe](../dmx/data-mining-extensions-dmx-syntax-conventions.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Éléments de syntaxe](../dmx/data-mining-extensions-dmx-syntax-elements.md)   
 [Expressions &#40; DMX &#41;](../dmx/expressions-dmx.md)   
 [Fonctions de prédiction générales &#40; DMX &#41;](../dmx/general-prediction-functions-dmx.md)   
 [Opérateurs &#40; DMX &#41;](../dmx/operators-dmx.md)   
 [Structure et utilisation des requêtes de prédiction DMX](../dmx/structure-and-usage-of-dmx-prediction-queries.md)   
 [Présentation de l’instruction DMX Select](../dmx/understanding-the-dmx-select-statement.md)  
  
  

