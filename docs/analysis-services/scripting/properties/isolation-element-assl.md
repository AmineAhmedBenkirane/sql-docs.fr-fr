---
title: "Élément isolation (ASSL) | Documents Microsoft"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- Isolation Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- Isolation element
ms.assetid: 28c98c6f-668e-4547-8d25-127cc3995a7d
caps.latest.revision: 13
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: cc61e20927d2a547a8d86e80a61e53c60e523bb2
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="isolation-element-assl"></a>Élément Isolation (ASSL)
  Indique le niveau d’isolation d’un élément qui est dérivé de la [source de données](../../../analysis-services/scripting/data-type/datasource-data-type-assl.md) type de données.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<DataSource>  
   ...  
   <Isolation>...</Isolation>  
   ...  
</DataSource>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Chaîne (énumération)|  
|Valeur par défaut|*Lecture validée*|  
|Cardinalité|0-1: élément facultatif qui peut apparaître une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Élément parent|[Source de données](../../../analysis-services/scripting/data-type/datasource-data-type-assl.md)|  
|Éléments enfants|Aucune|  
  
## <a name="remarks"></a>Notes  
 La valeur de cet élément est limitée à l'une des chaînes du tableau suivant.  
  
|Valeur| Description|  
|-----------|-----------------|  
|*Lecture validée*|Spécifie que les instructions ne peuvent pas lire les données modifiées mais non validées par d'autres transactions. Cela permet d'éviter les lectures incorrectes. D'autres transactions peuvent modifier des données entre des instructions individuelles dans la transaction actuelle. Il en résulte des lectures non reproductibles ou des données fantômes. Il s'agit de la valeur par défaut de l'élément **Isolation** .|  
|*Snapshot*|Spécifie que les données lues par n'importe quelle instruction d'une transaction représenteront la version cohérente d'un point de vue transactionnel des données qui existaient au début de la transaction. La transaction ne peut détecter que les modifications de données qui ont été validées avant qu'elle ne commence. Les modifications de données effectuées par d'autres transactions après le démarrage de la transaction actuelle ne sont pas visibles pour les instructions qui s'exécutent dans la transaction actuelle. Tout se passe comme si les instructions d'une transaction obtenaient un instantané des données validées telles qu'elles existaient au début de cette transaction.|  
  
## <a name="see-also"></a>Voir aussi  
 [Propriétés &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  

