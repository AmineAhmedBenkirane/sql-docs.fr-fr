---
title: Nouvel élément (XMLA) | Documents Microsoft
ms.custom: ''
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- New Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- http://schemas.microsoft.com/analysisservices/2003/engine#New
- microsoft.xml.analysis.new
- urn:schemas-microsoft-com:xml-analysis#New
helpviewer_keywords:
- New element
ms.assetid: 1321adcb-67f7-40f0-8f20-b17c1d3e3f17
caps.latest.revision: 11
author: Minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: cfb645f7e64ddc004da4a4b42203d48d484dcf69
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="new-element-xmla"></a>Élément New (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]
  Contient le nouvel emplacement de stockage de système fichier utilisé par un [dossier](../../../analysis-services/xmla/xml-elements-properties/folder-element-xmla.md) élément.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Folder>  
   ...  
   <New>...</New>  
   ...  
</Folder>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Chaîne|  
|Valeur par défaut|Aucune|  
|Cardinalité|1-1 : élément requis qui apparaît une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|[Dossier](../../../analysis-services/xmla/xml-elements-properties/folder-element-xmla.md)|  
|Éléments enfants|Aucune|  
  
## <a name="remarks"></a>Notes  
 Le **nouveau** élément contient un chemin d’accès UNC qui remplace la valeur de la **d’origine** élément contenu dans le parent **dossier** élément pour tous les objets restaurés ou synchronisés, respectivement, pendant un **restaurer** ou **synchroniser** commande. La valeur de la **d’origine** élément est comparé à la valeur de la **StorageLocation** , élément pour chaque cube, groupe de mesures ou partition et, si une correspondance est trouvée, la valeur de cet élément est utilisée pour mettre à jour le **%{storagelocation/}** de l’objet pendant la restauration ou la synchronisation.  
  
 Pour plus d’informations sur la sauvegarde et restauration des objets, consultez [sauvegarde et restauration des objets (XMLA)](../../../analysis-services/multidimensional-models-scripting-language-assl-xmla/backing-up-restoring-and-synchronizing-databases-xmla.md).  
  
## <a name="see-also"></a>Voir aussi  
 [D’origine, élément & #40 ; XMLA & #41 ;](../../../analysis-services/xmla/xml-elements-properties/original-element-xmla.md)   
 [Restaurer l’élément & #40 ; XMLA & #41 ;](../../../analysis-services/xmla/xml-elements-commands/restore-element-xmla.md)   
 [Élément StorageLocation & #40 ; ASSL & #41 ;](../../../analysis-services/scripting/properties/storagelocation-element-assl.md)   
 [Synchroniser, élément & #40 ; XMLA & #41 ;](../../../analysis-services/xmla/xml-elements-commands/synchronize-element-xmla.md)   
 [Propriétés & #40 ; XMLA & #41 ;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
