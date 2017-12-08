---
title: Ensemble de lignes DISCOVER_PROPERTIES | Documents Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: schema-rowsets
ms.reviewer: 
ms.suite: sql
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname: DISCOVER_PROPERTIES
apitype: NA
applies_to: SQL Server 2016 Preview
helpviewer_keywords: DISCOVER_PROPERTIES rowset
ms.assetid: 3e2b50e2-3855-4091-8b02-4968e8e57d4c
caps.latest.revision: "32"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: b695d3affd1783782e1eb8bde27d6c90157e4bab
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="discoverproperties-rowset"></a>Ensemble de lignes DISCOVER_PROPERTIES
  Retourne une liste d'informations et de valeurs sur les propriétés standard et spécifiques au fournisseur prises en charge par le fournisseur XML for Analysis (XMLA) [!INCLUDE[msCoName](../../../includes/msconame-md.md)] pour la source de données spécifiée. Les propriétés non prises en charge ne sont pas répertoriées dans le jeu de résultats retourné.  
  
 Si vous appelez le [Discover](../../../analysis-services/xmla/xml-elements-methods-discover.md) méthode avec la **DISCOVER_PROPERTIES** valeur d’énumération dans le [RequestType](../../../analysis-services/xmla/xml-elements-properties/requesttype-element-xmla.md) élément, le **Discover** méthode retourne la **DISCOVER_PROPERTIES** ensemble de lignes...  
  
## <a name="rowset-columns"></a>Colonnes de l'ensemble de lignes  
 L'ensemble de lignes **DISCOVER_PROPERTIES** contient les colonnes suivantes.  
  
|Nom de colonne|Type|Longueur| Description|  
|-----------------|----------|------------|-----------------|  
|**PropertyName**|**DBTYPE_WSTR**||Nom de la propriété.|  
|**PropertyDescription**|**DBTYPE_WSTR**||Description (texte) localisable de la propriété. Peut retourner **NULL**.|  
|**PropertyType**|**DBTYPE_WSTR**||Type de données XML de la propriété.<br /><br /> Peut retourner **NULL**.|  
|**PropertyAccessType**|**DBTYPE_WSTR**||Accès pour la propriété. La valeur peut être **Read**, **Write**ou **ReadWrite**.|  
|**IsRequired**|**DBTYPE_BOOL**||Valeur booléenne qui indique si une propriété est obligatoire.<br /><br /> True si une propriété est obligatoire ; false dans le cas contraire.<br /><br /> Peut retourner **NULL**.|  
|**Valeur**|**DBTYPE_WSTR**||Valeur actuelle de la propriété.<br /><br /> Peut retourner **NULL**.|  
  
 Cet ensemble de lignes de schéma n'est pas trié.  
  
## <a name="restriction-columns"></a>Colonnes de restriction  
 L'ensemble de lignes **DISCOVER_PROPERTIES** peut être restreint sur la colonne répertoriée dans le tableau suivant.  
  
|Nom de colonne|Indicateur de type|État de la restriction|  
|-----------------|--------------------|-----------------------|  
|**PropertyName**|**DBTYPE_WSTR**||  
  
## <a name="see-also"></a>Voir aussi  
 [Ensembles de lignes de schéma XML for Analysis](../../../analysis-services/schema-rowsets/xml/xml-for-analysis-schema-rowsets.md)  
  
  
