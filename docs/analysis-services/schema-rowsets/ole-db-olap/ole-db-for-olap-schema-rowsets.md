---
title: OLE DB pour OLAP Schema Rowsets | Documents Microsoft
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
applies_to: SQL Server 2016 Preview
helpviewer_keywords:
- schema rowsets [Analysis Services], OLE DB for OLAP
- OLE DB for OLAP schema rowsets
- schema rowsets [OLE DB for OLAP]
- rowsets [Analysis Services], OLE DB for OLAP
ms.assetid: 5fad3ecc-407c-4148-862e-ea6119cc7480
caps.latest.revision: "31"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: f06af3341034ccc9ddebe1ac6a130be705bdd0cd
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="ole-db-for-olap-schema-rowsets"></a>Ensembles de lignes de schéma OLE DB pour OLAP
  Le fournisseur XMLA ([!INCLUDE[msCoName](../../../includes/msconame-md.md)] XML for Analysis) prend en charge les ensembles de lignes de schéma OLE DB pour OLAP suivants.  
  
> [!NOTE]  
>  Pour vérifier si un fournisseur de source de données particulière prend en charge un ensemble de lignes, utilisez la **DISCOVER_ENUMERATIONS** ensemble de lignes avec le [Discover](../../../analysis-services/xmla/xml-elements-methods-discover.md) (méthode).  
  
 Vous trouverez également des informations détaillées sur ces ensembles de lignes en recherchant la rubrique « Ensembles de lignes schéma OLAP », dans la bibliothèque MSDN [site Web de Microsoft](http://go.microsoft.com/fwlink/?LinkId=15426).  
  
## <a name="in-this-section"></a>Dans cette section  
  
|Ensemble de lignes de schéma<sup>1</sup>| Description|  
|-------------------------------|-----------------|  
|[DISCOVER_INSTANCES, ensemble de lignes](../../../analysis-services/schema-rowsets/ole-db-olap/discover-instances-rowset.md)|Décrit les instances sur le serveur.|  
|[Ensemble de lignes DISCOVER_KEYWORDS &#40; OLE DB pour OLAP &#41;](../../../analysis-services/schema-rowsets/ole-db-olap/discover-keywords-rowset-ole-db-for-olap.md)|Énumère une liste de mots réservés par le fournisseur.|  
|[MDSCHEMA_ACTIONS, ensemble de lignes](../../../analysis-services/schema-rowsets/ole-db-olap/mdschema-actions-rowset.md)|Décrit les actions qui peuvent être disponibles pour les applications clientes.|  
|[MDSCHEMA_CUBES, ensemble de lignes](../../../analysis-services/schema-rowsets/ole-db-olap/mdschema-cubes-rowset.md)|Décrit la structure des cubes d'une base de données.|  
|[MDSCHEMA_DIMENSIONS, ensemble de lignes](../../../analysis-services/schema-rowsets/ole-db-olap/mdschema-dimensions-rowset.md)|Décrit les dimensions partagées et privées dans une base de données.|  
|[MDSCHEMA_FUNCTIONS, ensemble de lignes](../../../analysis-services/schema-rowsets/ole-db-olap/mdschema-functions-rowset.md)|Décrit les fonctions qui sont disponibles pour les applications clientes connectées à la base de données.|  
|[MDSCHEMA_HIERARCHIES, ensemble de lignes](../../../analysis-services/schema-rowsets/ole-db-olap/mdschema-hierarchies-rowset.md)|Décrit chaque hiérarchie contenue dans une dimension particulière.|  
|[MDSCHEMA_INPUT_DATASOURCES, ensemble de lignes](../../../analysis-services/schema-rowsets/ole-db-olap/mdschema-input-datasources-rowset.md)|Décrit les sources de données définies dans la base de données.|  
|[MDSCHEMA_KPIS, ensemble de lignes](../../../analysis-services/schema-rowsets/ole-db-olap/mdschema-kpis-rowset.md)|Décrit les indicateurs de performance clés (KPI) dans une base de données.|  
|[MDSCHEMA_LEVELS, ensemble de lignes](../../../analysis-services/schema-rowsets/ole-db-olap/mdschema-levels-rowset.md)|Décrit chaque niveau dans une hiérarchie particulière.|  
|[MDSCHEMA_MEASUREGROUP_DIMENSIONS, ensemble de lignes](../../../analysis-services/schema-rowsets/ole-db-olap/mdschema-measuregroup-dimensions-rowset.md)|Énumère les dimensions des groupes de mesures.|  
|[MDSCHEMA_MEASUREGROUPS, ensemble de lignes](../../../analysis-services/schema-rowsets/ole-db-olap/mdschema-measuregroups-rowset.md)|Décrit les groupes de mesures d'une base de données.|  
|[MDSCHEMA_MEASURES, ensemble de lignes](../../../analysis-services/schema-rowsets/ole-db-olap/mdschema-measures-rowset.md)|Décrit chaque mesure dans un cube.|  
|[MDSCHEMA_MEMBERS, ensemble de lignes](../../../analysis-services/schema-rowsets/ole-db-olap/mdschema-members-rowset.md)|Décrit les membres d'une base de données.|  
|[MDSCHEMA_PROPERTIES, ensemble de lignes](../../../analysis-services/schema-rowsets/ole-db-olap/mdschema-properties-rowset.md)|Décrit les propriétés des membres au sein d’une base de données.|  
|[MDSCHEMA_SETS, ensemble de lignes](../../../analysis-services/schema-rowsets/ole-db-olap/mdschema-sets-rowset.md)|Décrit les ensembles actuellement définis dans une base de données, y compris les ensembles de niveau session.|  
  
 <sup>1</sup> des ensembles de schéma répertoriés ici sont pris en charge par le fournisseur de source de données MSOLAP pour le [!INCLUDE[msCoName](../../../includes/msconame-md.md)] fournisseur XMLA.  
  
## <a name="see-also"></a>Voir aussi  
 [Ensemble de lignes DISCOVER_ENUMERATORS](../../../analysis-services/schema-rowsets/xml/discover-enumerators-rowset.md)   
 [Ensembles de lignes de schéma Analysis Services](../../../analysis-services/schema-rowsets/analysis-services-schema-rowsets.md)  
  
  
