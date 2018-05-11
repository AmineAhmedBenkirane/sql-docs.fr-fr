---
title: Élément Error (XMLA) | Documents Microsoft
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.component: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: a9903e86d5931d92222aec00f3896a2db78732f5
ms.sourcegitcommit: 38f8824abb6760a9dc6953f10a6c91f97fa48432
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2018
---
# <a name="error-element-xmla"></a>Élément Error (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]
  Contient des informations sur une erreur retournée par une instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<Message>  
   <Error   
      ErrorCode="unsignedint"   
      Severity="string"   
      Description="string"  
      Source="string"  
      HelpFile="string"  
   />  
</Message>  
<!-- or -->  
<Cell><!-- or row -->  
   <!-- A child element -->  
      <Error xmlns="urn:schemas-microsoft-com:xml-analysis:exception"  
         < ErrorCode>...</ErrorCode>  
         < Description>...</Description>  
         < Source>...</Source>  
         < HelpFile>...</HelpFile>  
      </Error>  
   <!-- /A child element -- >  
</Cell>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|Aucune|  
|Valeur par défaut|Aucune|  
|Cardinalité|0-1: élément facultatif qui peut apparaître une fois et une seule.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|[Boîte de](../../../analysis-services/xmla/xml-elements-properties/message-element-xmla.md)|  
|Éléments enfants|Consultez le tableau ci-dessous.|  
  
|Ancêtre|Éléments enfants|  
|--------------|--------------------|  
|[Message](../../../analysis-services/xmla/xml-elements-properties/message-element-xmla.md)|Aucune|  
|[Cell](../../../analysis-services/xmla/xml-elements-properties/cell-element-mddataset-xmla.md), [Row](../../../analysis-services/xmla/xml-elements-properties/message-element-xmla.md)|[Description](../../../analysis-services/xmla/xml-elements-properties/description-element-xmla.md), [ErrorCode](../../../analysis-services/xmla/xml-elements-properties/errorcode-element-xmla.md), [HelpFile](../../../analysis-services/xmla/xml-elements-properties/helpfile-element-xmla.md), [Source](../../../analysis-services/xmla/xml-elements-properties/source-element-error-xmla.md)|  
  
## <a name="attributes"></a>Attributs  
  
|Attribut|Description|  
|---------------|-----------------|  
|ErrorCode|Requis **UnsignedInt** attribut (uniquement lorsque **Message** est l’élément parent.) Contient le code de retour numérique de l'erreur.|  
|Severity|Facultatif **chaîne** attribut (uniquement lorsque **Message** est l’élément parent.) Affiche la gravité de l'erreur.|  
| Description|Facultatif **chaîne** attribut (uniquement lorsque **Message** est l’élément parent.) Contient le texte descriptif de l'erreur.|  
|Source|Facultatif **chaîne** attribut (uniquement lorsque **Message** est l’élément parent.) Contient le nom du composant qui a déclenché l'erreur.|  
|HelpFile|Facultatif **chaîne** attribut (uniquement lorsque **Message** est l’élément parent.) Contient le chemin d'accès ou l'URL menant au fichier ou à la rubrique d'aide qui décrit l'erreur.|  
  
## <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [Élément Warning & #40 ; XMLA & #41 ;](../../../analysis-services/xmla/xml-elements-properties/warning-element-xmla.md)   
 [Propriétés & #40 ; XMLA & #41 ;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
