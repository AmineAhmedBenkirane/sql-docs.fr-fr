---
title: "Modification de données (MDX) | Documents Microsoft"
ms.custom: 
ms.date: 03/13/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- modifying data [MDX]
- Multidimensional Expressions [Analysis Services], data modifications
- MDX [Analysis Services], data modifications
- data modifications [MDX]
ms.assetid: 363b662c-b839-4971-bbd7-1842f73ce141
caps.latest.revision: "30"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 4c490f3998b148691f35328fe5543874be92f997
ms.sourcegitcommit: f1a6944f95dd015d3774a25c14a919421b09151b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2017
---
# <a name="mdx-data-modification---modifying-data"></a>Modification des données MDX - modification de données
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Outre l’utilisation de MDX (Multidimensional Expressions) pour extraire et gérer les données à partir des dimensions et des cubes, vous pouvez utiliser MDX pour mettre à jour ou *l’écriture différée* les données de dimension et le cube. Ces mises à jour peuvent être temporaires (comme pour l'analyse spéculative, du type « Que se passe-t-il si ») ou permanentes (comme lorsque des modifications doivent être apportées en fonction de l'analyse de données).  
  
 Les mises à jour de données se produisent au niveau de la dimension ou du cube :  
  
 **Écriture différée de dimensions**  
 L’instruction [ALTER CUBE Statement (MDX)](../../../mdx/mdx-data-definition-alter-cube.md) permet de modifier les données d’une dimension activée en écriture, tandis que l’instruction [REFRESH CUBE Statement (MDX)](../../../mdx/mdx-data-definition-refresh-cube.md) sert à illustrer les processus de suppression, création et mise à jour des valeurs d’attributs. Il est également possible d'utiliser l'instruction ALTER CUBE pour effectuer des opérations complexes, notamment la suppression de l'intégralité d'une sous-arborescence dans une hiérarchie et la promotion des enfants d'un membre supprimé.  
  
 **Écriture différée de cubes**  
 Pour effectuer des mises à jour d’un cube activé en écriture, vous devez utiliser l’instruction [UPDATE CUBE](../../../mdx/mdx-data-manipulation-update-cube.md) . L’instruction UPDATE CUBE permet de mettre à jour un tuple avec une valeur spécifique. L’instruction [REFRESH CUBE (MDX)](../../../mdx/mdx-data-definition-refresh-cube.md) permet d’actualiser les données d’une session client avec les données mises à jour du serveur.  
  
 Pour plus d’informations, consultez [Utilisation de l’écriture différée de cubes à l’aide de &#40;MDX&#41;](../../../analysis-services/multidimensional-models/mdx/mdx-data-modification-using-cube-writebacks.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Principes de base des requêtes MDX &#40;Analysis Services&#41;](../../../analysis-services/multidimensional-models/mdx/mdx-query-fundamentals-analysis-services.md)  
  
  
