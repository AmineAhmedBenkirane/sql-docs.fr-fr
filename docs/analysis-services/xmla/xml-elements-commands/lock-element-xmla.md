---
title: "Verrouiller l’élément (XMLA) | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- Lock Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- urn:schemas-microsoft-com:xml-analysis#Lock
- microsoft.xml.analysis.lock
- http://schemas.microsoft.com/analysisservices/2003/engine#Lock
helpviewer_keywords:
- Lock command
ms.assetid: a819e805-4793-43bb-8af3-16a19f8bdab3
caps.latest.revision: 14
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: df377150443acf63e4f67cd4f8f4952f36277a32
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="lock-element-xmla"></a>Élément Lock (XMLA)
  Verrouille un objet spécifié sur un [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Command>  
   <Lock>  
      <ID>...</ID>  
      <Object>...</Object>  
      <Mode>...</Mode>  
   </Lock>  
</Command>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Aucune|  
|Valeur par défaut|Aucune|  
|Cardinalité|0-n : élément facultatif pouvant apparaître plusieurs fois.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|[Command](../../../analysis-services/xmla/xml-elements-properties/command-element-xmla.md)|  
|Éléments enfants|[ID](../../../analysis-services/xmla/xml-elements-properties/id-element-xmla.md), [Mode](../../../analysis-services/xmla/xml-elements-properties/mode-element-xmla.md), [objet](../../../analysis-services/xmla/xml-elements-properties/object-element-xmla.md)|  
  
## <a name="remarks"></a>Notes  
 La commande **Lock** verrouille un objet, pour un usage partagé ou exclusif, dans le contexte de la transaction actuellement active. Seuls les administrateurs de bases de données ou de serveurs peuvent émettre une commande **Lock** de manière explicite. Un verrou sur un objet empêche la validation des transactions aussi longtemps que le verrou n'est pas supprimé. [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] prend en charge deux types de verrous : les verrous partagés et les verrous exclusifs. Pour plus d’informations sur les types de verrous pris en charge par [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], consultez [élément Mode &#40; XMLA &#41; ](../../../analysis-services/xmla/xml-elements-properties/mode-element-xmla.md).  
  
 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] autorise uniquement le verrouillage des bases de données. Le **objet** élément doit contenir une référence d’objet une [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] base de données. Si l'élément **Object** n'est pas spécifié ou si cet élément **Object** fait référence à un objet autre qu'une base de données, une erreur survient.  
  
 Autres commandes implicitement problème un **verrou** commande sur une [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] base de données. Toutes les opérations permettant de lire les données ou les métadonnées d'une base de données (par exemple, n'importe quelle méthode **Discover** ou une méthode **Execute** exécutant une commande **Statement** ) émettent implicitement un verrou partagé dans la base de données. Toute transaction qui valide les modifications de données ou les métadonnées pour un objet sur un [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] de base de données, comme un **Execute** méthode en cours d’exécution un **Alter** command, émettent implicitement un verrou exclusif sur la base de données.  
  
 Tous les verrous sont conservés dans le contexte de la transaction en cours. Lors de la validation ou de la restauration de la transaction en cours, tous les verrous définis dans celle-ci sont libérés automatiquement.  
  
## <a name="see-also"></a>Voir aussi  
 [Déverrouiller l’élément &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/unlock-element-xmla.md)   
 [Commandes &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/xml-elements-commands.md)  
  
  

