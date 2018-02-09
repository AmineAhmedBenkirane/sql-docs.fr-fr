---
title: Dimension, objet (ADO MD) | Documents Microsoft
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- Dimension
helpviewer_keywords:
- Dimension object [ADO MD]
ms.assetid: 66adbbd2-23a3-4c19-a91b-84c31309aa1b
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 9a222c6495302f06e5fa2b8dd0e0d355869e3d40
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2018
---
# <a name="dimension-object-ado-md"></a>Objet de dimension (ADO MD)
Représente une des dimensions d’un cube multidimensionnel, contenant une ou plusieurs hiérarchies de membres.  
  
## <a name="remarks"></a>Notes  
 Les collections et les propriétés d’un **Dimension** de l’objet, vous pouvez procédez comme suit :  
  
-   Identifier les **Dimension** avec la [nom](../../../ado/reference/ado-md-api/name-property-ado-md.md) et [UniqueName](../../../ado/reference/ado-md-api/uniquename-property-ado-md.md) propriétés.  
  
-   Retourne une chaîne explicite qui décrit le **Dimension** avec la [Description](../../../ado/reference/ado-md-api/description-property-ado-md.md) propriété.  
  
-   Retourner le [hiérarchie](../../../ado/reference/ado-md-api/hierarchy-object-ado-md.md) objets qui composent le **Dimension** avec la [hiérarchies](../../../ado/reference/ado-md-api/hierarchies-collection-ado-md.md) collection.  
  
-   Utiliser ADO standard [propriétés](../../../ado/reference/ado-api/properties-collection-ado.md) collection pour obtenir des informations supplémentaires sur le **Dimension** objet.  
  
 Le **propriétés** collection contient des propriétés fournies par le fournisseur. Le tableau suivant répertorie les propriétés qui peuvent être disponibles. La liste réelle des propriétés peut varier en fonction de l’implémentation du fournisseur. Consultez la documentation de votre fournisseur pour obtenir une liste plus complète des propriétés disponibles.  
  
|Nom| Description|  
|----------|-----------------|  
|CatalogName|Le nom du catalogue auquel appartient ce cube.|  
|CubeName|Nom du cube.|  
|DefaultHierarchy|Le nom unique de la hiérarchie par défaut.|  
| Description|Description explicite du cube.|  
|DimensionCaption|Étiquette ou légende associée à la dimension.|  
|DimensionCardinality|Le nombre de membres dans la dimension.|  
|DimensionGUID|Le GUID de la dimension.|  
|DimensionName|Nom de la dimension.|  
|DimensionOrdinal|Le nombre ordinal de la dimension entre le groupe de dimensions qui forment le cube.|  
|DimensionType|Le type de dimension.|  
|DimensionUniqueName|Le nom non ambigu de la dimension.|  
|SchemaName|Le nom du schéma auquel appartient ce cube.|  
  
 Cette section contient les rubriques suivantes.  
  
-   [Propriétés, méthodes et événements](../../../ado/reference/ado-md-api/dimension-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>Voir aussi  
 [CubeDef, exemple (VBScript)](../../../ado/reference/ado-md-api/cubedef-example-vbscript.md)   
 [CubeDef, objet (ADO MD)](../../../ado/reference/ado-md-api/cubedef-object-ado-md.md)   
 [Collection de dimensions (ADO MD)](../../../ado/reference/ado-md-api/dimensions-collection-ado-md.md)   
 [Collection de hiérarchies (ADO MD)](../../../ado/reference/ado-md-api/hierarchies-collection-ado-md.md)   
 [Properties, collection (ADO)](../../../ado/reference/ado-api/properties-collection-ado.md)
