---
title: "Élément mode (XMLA) | Documents Microsoft"
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
- Mode Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- urn:schemas-microsoft-com:xml-analysis#Mode
- microsoft.xml.analysis.mode
- http://schemas.microsoft.com/analysisservices/2003/engine#Mode
helpviewer_keywords:
- Mode element
ms.assetid: 43a54181-6494-48c3-b14b-376d8939fa9f
caps.latest.revision: 13
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 57c3450e8928b24dc03e2d5915983f39330d0b0c
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="mode-element-xmla"></a>Élément Mode (XMLA)
  Identifie le mode à utiliser par le parent [verrou](../../../analysis-services/xmla/xml-elements-commands/lock-element-xmla.md) élément lors de la création d’un verrou sur un objet spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Lock>  
   ...  
   <Mode>...</Mode>  
   ...  
</Lock>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Chaîne (énumération)|  
|Valeur par défaut|Aucune|  
|Cardinalité|1-1 : élément requis qui apparaît une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|[Verrou](../../../analysis-services/xmla/xml-elements-commands/lock-element-xmla.md), [déverrouiller](../../../analysis-services/xmla/xml-elements-commands/unlock-element-xmla.md)|  
|Éléments enfants|Aucune|  
  
## <a name="remarks"></a>Notes  
 Le parent **verrou** élément utilise le **Mode** élément afin de déterminer le type de verrou à créer sur un objet. La valeur de cet élément est limitée à l'une des chaînes répertoriées dans le tableau suivant.  
  
|Valeur| Description|  
|-----------|-----------------|  
|*CommitShared*|Un verrou partagé est établi sur l'objet spécifié. D'autres verrous partagés peuvent être créés pour le même objet.<br /><br /> Un verrou partagé empêche les transactions contenant des opérations d’écriture, telles qu’une [Execute](../../../analysis-services/xmla/xml-elements-methods-execute.md) appel de méthode en cours d’exécution un [Alter](../../../analysis-services/xmla/xml-elements-commands/alter-element-xmla.md) commande sur un objet spécifié, à partir de la validation jusqu'à ce que le verrou partagé est supprimé. Un verrou partagé n’empêche pas les transactions contenant des opérations de lecture, comme un [Discover](../../../analysis-services/xmla/xml-elements-methods-discover.md) appel de méthode ou un **Execute** appel de méthode en cours d’exécution un [instruction](../../../analysis-services/xmla/xml-elements-commands/statement-element-xmla.md) commande à partir de la validation.|  
|*CommitExclusive*|Un verrou exclusif est établi sur l'objet spécifié. Aucun autre verrou partagé ou exclusif ne peut être créé pour le même objet.<br /><br /> Jusqu'à sa suppression, un verrou exclusif empêche la validation des transactions contenant des opérations de lecture ou d'écriture sur un objet spécifié.|  
  
## <a name="see-also"></a>Voir aussi  
 [ID, élément &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/id-element-xmla.md)   
 [Objet, élément &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/object-element-xmla.md)   
 [Propriétés &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  

