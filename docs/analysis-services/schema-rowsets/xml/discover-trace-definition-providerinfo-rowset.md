---
title: Ensemble de lignes DISCOVER_TRACE_DEFINITION_PROVIDERINFO | Documents Microsoft
ms.custom: ''
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
ms.assetid: 8dda2ef7-202a-454b-93f9-a2b29c2d277c
caps.latest.revision: 6
author: Minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 37b44f2959141204a9f524ff4edb8c5c2b9a6102
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="discovertracedefinitionproviderinfo-rowset"></a>DISCOVER_TRACE_DEFINITION_PROVIDERINFO, ensemble de lignes
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Retourne des informations de base sur le fournisseur de trace, telles que son nom et sa description.  
  
 **S'applique à :** modèles tabulaires, modèles multidimensionnels  
  
## <a name="rowset-columns"></a>Colonnes de l'ensemble de lignes  
 L'ensemble de lignes **DISCOVER_TRACE_DEFINITION_PROVIDERINFO** contient les colonnes suivantes.  
  
|Nom de colonne|Indicateur de type|Restriction| Description|  
|-----------------|--------------------|-----------------|-----------------|  
|**Données**|**DBTYPE_WSTR**|Oui|Contient une chaîne XML encodée décrivant le fournisseur de trace, y compris le nom du fournisseur, la version, le numéro de build et la description.|  
  
 Cet ensemble de lignes de schéma n'est pas trié.  
  
## <a name="using-adomdnet-to-return-the-rowset"></a>Utilisation d'ADOMD.NET pour retourner l'ensemble de lignes  
 Lorsque vous utilisez ADOMD.NET et l'ensemble de lignes de schéma pour récupérer des métadonnées, vous pouvez utiliser un GUID ou une chaîne pour référencer un objet d'ensemble de lignes de schéma dans la méthode GetSchemaDataSet. Pour plus d'informations, consultez [Working with Schema Rowsets in ADOMD.NET](../../../analysis-services/multidimensional-models-adomd-net-client/retrieving-metadata-working-with-schema-rowsets.md).  
  
 Le tableau suivant fournit le GUID et les valeurs de chaîne qui identifient cet ensemble de lignes.  
  
|Argument|Valeur|  
|--------------|-----------|  
|GUID|A07CCD1B-8148-11D0-87BB-00C04FC33942|  
|ADOMDNAME|TraceDefinitionProviderInfo|  
  
## <a name="see-also"></a>Voir aussi  
 [XML for Analysis ensembles de lignes de schéma](../../../analysis-services/schema-rowsets/xml/xml-for-analysis-schema-rowsets.md)  
  
  
