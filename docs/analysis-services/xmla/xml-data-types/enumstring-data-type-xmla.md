---
title: Type de données EnumString (XMLA) | Documents Microsoft
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.component: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: bf85868a2dbaa9926ea824e7643fe498c58b7115
ms.sourcegitcommit: 38f8824abb6760a9dc6953f10a6c91f97fa48432
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2018
---
# <a name="enumstring-data-type-xmla"></a>Type de données EnumString (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]
  Définit un type de données dérivé qui représente un jeu de constantes nommées pour un énumérateur donné.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<EnumString>...</EnumString>  
```  
  
## <a name="data-type-characteristics"></a>Caractéristiques du type de données  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Types de données de base|**chaîne**|  
|Types de données dérivés|Aucune|  
  
## <a name="data-type-relationships"></a>Relations du type de données  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|Aucune|  
|Éléments enfants|Aucune|  
|Éléments dérivés|Aucune|  
  
## <a name="remarks"></a>Notes  
 XML for Analysis (XMLA) utilise des énumérations pour limiter les valeurs de chaîne à un ensemble de paramètres vérifiables. **EnumString** utilise le type de données XML **string** standard. Les valeurs propres à chacune des constantes nommées sont spécifiées avec la définition de l'énumérateur. Les énumérateurs sont définies en les ajoutant à la [DISCOVER_ENUMERATORS](../../../analysis-services/schema-rowsets/xml/discover-enumerators-rowset.md) de lignes du schéma et peut être récupéré à l’aide de la [Discover](../../../analysis-services/xmla/xml-elements-methods-discover.md) type de demande de méthode avec le DISCOVER_ENUMERATORS.  
  
 Le tableau suivant décrit les énumérateurs pris en charge par une instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].  
  
|Énumérateur| Description|  
|----------------|-----------------|  
|ProviderType|Prend en charge de la colonne ProviderType dans le [DISCOVER_DATASOURCES](../../../analysis-services/schema-rowsets/xml/discover-datasources-rowset.md) de lignes du schéma, qui détermine le type de données qui peuvent être retournées par une [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance.<br /><br /> Cette énumération prend également en charge la propriété XMLA **ProviderType**, qui détermine les types de fournisseurs pris en charge par un [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance. Cette énumération est également utilisée dans l'ensemble de lignes du schéma DISCOVER_DATASOURCES.<br /><br /> Pour plus d’informations sur **ProviderType**, consultez [pris en charge les propriétés XMLA &#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties.md).|  
|AuthenticationMode|Prend en charge la colonne AuthenticationMode dans l'ensemble de lignes du schéma DISCOVER_DATASOURCES qui détermine les informations d'identification de sécurité à transmettre pour accéder à une instance [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].|  
|PropertyAccessType|Prend en charge de la colonne PropertyAccessType dans le [DISCOVER_PROPERTIES](../../../analysis-services/schema-rowsets/xml/discover-properties-rowset.md) de lignes du schéma, qui détermine le type d’accès disponibles pour une propriété XMLA.|  
|StateSupport|Prend en charge la propriété XMLA **StateSupport**, qui détermine le niveau d’état pris en charge par un [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance.<br /><br /> Pour plus d’informations sur **StateSupport**, consultez [pris en charge les propriétés XMLA &#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties.md).|  
|StateActionVerb|Contient une liste de verbes pris en charge par XMLA dans les en-têtes SOAP et utilisés pour démarrer, identifier et achever une session.<br /><br /> Pour plus d’informations sur les sessions, consultez [gestion des connexions et Sessions &#40;XMLA&#41;](../../../analysis-services/multidimensional-models-scripting-language-assl-xmla/managing-connections-and-sessions-xmla.md).|  
|ResultsetFormat|Prend en charge la propriété XMLA **Format**, qui détermine le type de données retournées dans un [racine](../../../analysis-services/xmla/xml-elements-properties/root-element-xmla.md) élément.<br /><br /> Pour plus d’informations sur **Format**, consultez [pris en charge les propriétés XMLA &#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties.md).|  
|ResultsetAxisFormat|Prend en charge la propriété XMLA **AxisFormat**qui détermine le format des informations d'axe que retourne un élément **root** contenant des données multidimensionnelles.<br /><br /> Pour plus d’informations sur **AxisFormat**, consultez [pris en charge les propriétés XMLA &#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties.md).|  
|ResultsetContents|Prend en charge la propriété XMLA **Content**qui détermine si les données ou les métadonnées sont retournées dans un élément **root** .<br /><br /> Pour plus d’informations sur **contenu**, consultez [pris en charge les propriétés XMLA &#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties.md).|  
|MDXSupportLevel|Prend en charge la propriété XMLA **MDXSupport**, ce qui indique le niveau de prise en charge de MDX (Multidimensional Expressions) disponible sur un [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance.<br /><br /> Pour plus d’informations sur **MDXSupport**, consultez [pris en charge les propriétés XMLA &#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties.md).|  
  
## <a name="see-also"></a>Voir aussi  
 [Types de données XML &#40;XMLA&#41;](../../../analysis-services/xmla/xml-data-types/xml-data-types-xmla.md)  
  
  
