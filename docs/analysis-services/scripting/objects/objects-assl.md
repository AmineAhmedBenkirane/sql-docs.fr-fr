---
title: Objets (ASSL) | Documents Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
applies_to: SQL Server 2016 Preview
helpviewer_keywords:
- ASSL, objects
- objects [Analysis Services Scripting Language]
- Analysis Services Scripting Language, objects
ms.assetid: 0f672b93-c317-47e5-b44d-ecea9b587c98
caps.latest.revision: "21"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: ea027aba8d0d49c752bd31569f84d0f0cec022bd
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2018
---
# <a name="objects-assl"></a>Objets (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Cette section de référence contient des informations de syntaxe et d’utilisation pour chaque élément qui agit en tant qu’objet dans le schéma d’Analysis Services Scripting Language (ASSL).  
  
 Bien que le schéma ASSL renferme uniquement des éléments XML à partir du point de vue d’un développeur, les éléments décrits dans cette section correspondent aux objets, tels que **base de données**, **Cube**, et **Dimension** objets, dans la hiérarchie des objets contenus dans une instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].  
  
 Les objets ne sont jamais des éléments de niveau feuille au sein du schéma ASSL mais disposent d'éléments enfants et d'éléments qui correspondent à des propriétés d'objet.  
  
 Dans certains cas, un élément de niveau feuille susceptible d'apparaître comme une propriété dans le schéma est classé en tant qu'objet puisque le type de l'élément est un type d'objet. Par exemple, le **Source** d’un **Dimension** objet est de type **DimensionBinding**.  
  
## <a name="in-this-section"></a>Dans cette section  
  
|Élément|Description|  
|-------------|-----------------|  
|[Élément Account &#40; ASSL &#41;](../../../analysis-services/scripting/objects/account-element-assl.md)|Contient des détails sur un type de compte dans un [base de données](../../../analysis-services/scripting/objects/database-element-assl.md) élément.|  
|[Élément action &#40; ASSL &#41;](../../../analysis-services/scripting/objects/action-element-assl.md)|Contient des informations sur une action disponible dans un [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) élément ou un [Perspective](../../../analysis-services/scripting/objects/perspective-element-assl.md) élément.|  
|[Élément Aggregation &#40; ASSL &#41;](../../../analysis-services/scripting/objects/aggregation-element-assl.md)|Définit une agrégation unique pour un [Partition](../../../analysis-services/scripting/objects/partition-element-assl.md) élément.|  
|[Élément AggregationDesign &#40; ASSL &#41;](../../../analysis-services/scripting/objects/aggregationdesign-element-assl.md)|Définit un ensemble de définitions d'agrégation qu'il est possible de partager sur plusieurs partitions dans une base de données.|  
|[Élément AggregationInstance &#40; ASSL &#41;](../../../analysis-services/scripting/objects/aggregationinstance-element-assl.md)|Définit une instance d'agrégation pour une partition.|  
|[Élément AlgorithmParameter &#40; ASSL &#41;](../../../analysis-services/scripting/objects/algorithmparameter-element-assl.md)|Définit un paramètre pour l’algorithme utilisé par un [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md) élément.|  
|[Élément AllMemberTranslation &#40; ASSL &#41;](../../../analysis-services/scripting/objects/allmembertranslation-element-assl.md)|Contient une traduction de la légende du membre All d’un [hiérarchie](../../../analysis-services/scripting/objects/hierarchy-element-assl.md) élément.|  
|[Élément d’annotation &#40; ASSL &#41;](../../../analysis-services/scripting/objects/annotation-element-assl.md)|Contient des éléments utilisés pour étendre le schéma ASSL.|  
|[Assembly, élément &#40; ASSL &#41;](../../../analysis-services/scripting/objects/assembly-element-assl.md)|Représente un [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] assembly ou une bibliothèque de liens dynamiques (DLL) COM associée une [Server](../../../analysis-services/scripting/objects/server-element-assl.md) élément ou un [base de données](../../../analysis-services/scripting/objects/database-element-assl.md) élément.|  
|[Élément attribute &#40; ASSL &#41;](../../../analysis-services/scripting/objects/attribute-element-assl.md)|Contient la description d'un attribut.|  
|[Élément AttributeAllMemberTranslation &#40; ASSL &#41;](../../../analysis-services/scripting/objects/attributeallmembertranslation-element-assl.md)|Contient une traduction de la légende du membre All d’un [DimensionAttribute](../../../analysis-services/scripting/data-type/dimensionattribute-data-type-assl.md) élément.|  
|[Élément AttributePermission &#40; ASSL &#41;](../../../analysis-services/scripting/objects/attributepermission-element-assl.md)|Définit les autorisations que les membres d’un [rôle](../../../analysis-services/scripting/objects/role-element-assl.md) élément avoir sur les attributs d’une dimension individuelle dans un [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) élément.|  
|[Élément AttributeRelationship &#40; ASSL &#41;](../../../analysis-services/scripting/objects/attributerelationship-element-assl.md)|Fournit des détails sur la relation entre deux attributs.|  
|[Élément de bloc &#40; ASSL &#41;](../../../analysis-services/scripting/objects/block-element-assl.md)|Contient l’ensemble ou une partie du contenu binaire d’un [ClrAssemblyFile](../../../analysis-services/scripting/data-type/clrassemblyfile-data-type-assl.md) élément.|  
|[Élément Calculation &#40; ASSL &#41;](../../../analysis-services/scripting/objects/calculation-element-assl.md)|Associe un calcul à un [Perspective](../../../analysis-services/scripting/objects/perspective-element-assl.md) élément.|  
|[Élément CalculationProperty &#40; ASSL &#41;](../../../analysis-services/scripting/objects/calculationproperty-element-assl.md)|Contient une collection de propriétés d’interface utilisateur pour un calcul utilisé dans une [MdxScript](../../../analysis-services/scripting/objects/mdxscript-element-assl.md) élément.|  
|[Élément CaptionColumn &#40; ASSL &#41;](../../../analysis-services/scripting/objects/captioncolumn-element-assl.md)|Définit la colonne qui fournit la légende de l'attribut.|  
|[Élément CellPermission &#40; ASSL &#41;](../../../analysis-services/scripting/objects/cellpermission-element-assl.md)|Décrit les autorisations que les membres d’un [rôle](../../../analysis-services/scripting/objects/role-element-assl.md) élément avoir sur les cellules individuelles d’un [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) élément.|  
|[Column, élément &#40; ASSL &#41;](../../../analysis-services/scripting/objects/column-element-assl.md)|Décrit une colonne dans la collection de colonnes associée à l'élément parent.|  
|[Élément Command &#40; ASSL &#41;](../../../analysis-services/scripting/objects/command-element-assl.md)|Définit une commande qui est disponible dans le contexte de l'élément parent de la collection Commands.|  
|[Élément cube &#40; ASSL &#41;](../../../analysis-services/scripting/objects/cube-element-assl.md)|Définit un cube régulier, virtuel ou lié dans un [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] [base de données](../../../analysis-services/scripting/objects/database-element-assl.md) élément.|  
|[Élément CubePermission &#40; ASSL &#41;](../../../analysis-services/scripting/objects/cubepermission-element-assl.md)|Définit les autorisations des membres d’un particulier [rôle](../../../analysis-services/scripting/objects/role-element-assl.md) élément dans un spécifique [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) élément.|  
|[Élément CustomRollupColumn &#40; ASSL &#41;](../../../analysis-services/scripting/objects/customrollupcolumn-element-assl.md)|Définit les détails de la colonne qui fournissent une formule de cumul personnalisée.|  
|[Élément CustomRollupPropertiesColumn &#40; ASSL &#41;](../../../analysis-services/scripting/objects/customrolluppropertiescolumn-element-assl.md)|Définit les détails d'une colonne qui fournissent les propriétés d'une formule de cumul personnalisée.|  
|[Élément de données &#40; ASSL &#41;](../../../analysis-services/scripting/objects/data-element-assl.md)|Contient (dans la collection d’enfants **bloc** éléments) le contenu binaire d’un [ClrAssemblyFile](../../../analysis-services/scripting/data-type/clrassemblyfile-data-type-assl.md) élément.|  
|[Élément de la base de données &#40; ASSL &#41;](../../../analysis-services/scripting/objects/database-element-assl.md)|Définit une base de données [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].|  
|[Élément DatabasePermission &#40; ASSL &#41;](../../../analysis-services/scripting/objects/databasepermission-element-assl.md)|Définit les autorisations par défaut dans un [base de données](../../../analysis-services/scripting/objects/database-element-assl.md) élément pour un spécifique [rôle](../../../analysis-services/scripting/objects/role-element-assl.md) élément.|  
|[Élément de source de données &#40; ASSL &#41;](../../../analysis-services/scripting/objects/datasource-element-assl.md)|Définit une source de données dans un [base de données](../../../analysis-services/scripting/objects/database-element-assl.md) élément.|  
|[Élément DataSourcePermission &#40; ASSL &#41;](../../../analysis-services/scripting/objects/datasourcepermission-element-assl.md)|Définit les autorisations par défaut dans un [DataSource](../../../analysis-services/scripting/data-type/datasource-data-type-assl.md) type de données pour un spécifique [rôle](../../../analysis-services/scripting/objects/role-element-assl.md) élément.|  
|[Élément DataSourceView &#40; ASSL &#41;](../../../analysis-services/scripting/objects/datasourceview-element-assl.md)|Définit une vue de source de données utilisée par un [base de données](../../../analysis-services/scripting/objects/database-element-assl.md) élément.|  
|[Élément dimension &#40; ASSL &#41;](../../../analysis-services/scripting/objects/dimension-element-assl.md)|Définit une dimension.|  
|[Élément DimensionPermission &#40; ASSL &#41;](../../../analysis-services/scripting/objects/dimensionpermission-element-assl.md)|Définit les autorisations qui appartiennent à un particulier [rôle](../../../analysis-services/scripting/objects/role-element-assl.md) élément pour une dimension de base de données spécifique ou de la dimension de cube.|  
|[Élément ErrorConfiguration &#40; ASSL &#41;](../../../analysis-services/scripting/objects/errorconfiguration-element-assl.md)|Spécifie des paramètres pour gérer les erreurs qui peuvent se produire lors du traitement de l'élément parent.|  
|[Élément Event &#40; ASSL &#41;](../../../analysis-services/scripting/objects/event-element-assl.md)|Définit un événement à capturer dans le cadre d’un [Trace](../../../analysis-services/scripting/objects/trace-element-assl.md) élément.|  
|[Élément File &#40; ASSL &#41;](../../../analysis-services/scripting/objects/file-element-assl.md)|Définit un des fichiers qui composent un [ClrAssembly](../../../analysis-services/scripting/data-type/clrassembly-data-type-assl.md) élément.|  
|[Élément ForeignKeyColumn &#40; ASSL &#41;](../../../analysis-services/scripting/objects/foreignkeycolumn-element-assl.md)|Identifie la jointure à une table parente pour une source de données relationnelle.|  
|[Élément group &#40; ASSL &#41;](../../../analysis-services/scripting/objects/group-element-assl.md)|Définit un groupe de membres liés à un attribut.|  
|[Élément Hierarchy &#40; ASSL &#41;](../../../analysis-services/scripting/objects/hierarchy-element-assl.md)|Définit une hiérarchie dans une dimension|  
|[Élément IncrementalProcessingNotification &#40; ASSL &#41;](../../../analysis-services/scripting/objects/incrementalprocessingnotification-element-assl.md)|Contient des informations pour le [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) élément sur une requête à exécuter pour déterminer la progression du traitement incrémentiel.|  
|[Élément KeyColumn &#40; ASSL &#41;](../../../analysis-services/scripting/objects/keycolumn-element-assl.md)|Contient la définition d'une colonne qui est la clé d'un attribut ou en fait partie.|  
|[Élément KPI &#40; ASSL &#41;](../../../analysis-services/scripting/objects/kpi-element-assl.md)|Définit un indicateur de performance clé (KPI) dans un [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) élément ou un [Perspective](../../../analysis-services/scripting/objects/perspective-element-assl.md) élément.|  
|[Élément Level &#40; ASSL &#41;](../../../analysis-services/scripting/objects/level-element-assl.md)|Définit un niveau dans un [hiérarchie](../../../analysis-services/scripting/objects/hierarchy-element-assl.md) élément.|  
|[Élément MdxScript &#40; ASSL &#41;](../../../analysis-services/scripting/objects/mdxscript-element-assl.md)|Contient des informations sur un script MDX (Multidimensional Expressions) qui est associé à un [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) élément.|  
|[Élément Measure &#40; ASSL &#41;](../../../analysis-services/scripting/objects/measure-element-assl.md)|Définit une mesure.|  
|[Élément MeasureGroup &#40; ASSL &#41;](../../../analysis-services/scripting/objects/measuregroup-element-assl.md)|Définit un ensemble de mesures au même niveau de granularité.|  
|[Élément Member &#40; ASSL &#41;](../../../analysis-services/scripting/objects/member-element-assl.md)|Contient le nom d'un membre d'un élément [Group](../../../analysis-services/scripting/objects/group-element-assl.md) ou d'un élément [Role](../../../analysis-services/scripting/objects/role-element-assl.md) .|  
|[MiningModel, élément &#40; ASSL &#41;](../../../analysis-services/scripting/objects/miningmodel-element-assl.md)|Définit un modèle d'exploration de données unique.|  
|[Miningmodelpermission, élément &#40; ASSL &#41;](../../../analysis-services/scripting/objects/miningmodelpermission-element-assl.md)|Définit les autorisations de membres d’un [rôle](../../../analysis-services/scripting/objects/role-element-assl.md) élément avoir un individu [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md) élément.|  
|[Élément MiningStructure &#40; ASSL &#41;](../../../analysis-services/scripting/objects/miningstructure-element-assl.md)|Définit la structure d'un ensemble de modèles d'exploration de données.|  
|[Miningstructurepermission, élément &#40; ASSL &#41;](../../../analysis-services/scripting/objects/miningstructurepermission-element-assl.md)|Définit les autorisations que les membres d’un [rôle](../../../analysis-services/scripting/objects/role-element-assl.md) élément avoir un individu [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md) élément.|  
|[Élément ModelingFlag &#40; ASSL &#41;](../../../analysis-services/scripting/objects/modelingflag-element-assl.md)|Contient un indicateur de modélisation pour une colonne dans une structure d'exploration de données ou un modèle d'exploration de données.|  
|[Élément NameColumn &#40; ASSL &#41;](../../../analysis-services/scripting/objects/namecolumn-element-assl.md)|Identifie la colonne qui fournit le nom de l'élément parent.|  
|[Élément NamingTemplateTranslation &#40; ASSL &#41;](../../../analysis-services/scripting/objects/namingtemplatetranslation-element-assl.md)|Fournit une traduction localisée de la **NamingTemplate** élément un parent [DimensionAttribute](../../../analysis-services/scripting/data-type/dimensionattribute-data-type-assl.md) type de données.|  
|[Élément partition &#40; ASSL &#41;](../../../analysis-services/scripting/objects/partition-element-assl.md)|Définit une partition d’un [MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md) élément ou une liaison de partition dans une sortie de ligne [MeasureGroupBinding](../../../analysis-services/scripting/data-type/measuregroupbinding-data-type-out-of-line-assl.md)élément.|  
|[Élément perspective &#40; ASSL &#41;](../../../analysis-services/scripting/objects/perspective-element-assl.md)|Définit des détails pour un point de vue d’un [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) élément.|  
|[ProactiveCaching, élément &#40; ASSL &#41;](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md)|Définit des paramètres de mise en cache proactive pour l'élément parent.|  
|[Élément QueryNotification &#40; ASSL &#41;](../../../analysis-services/scripting/objects/querynotification-element-assl.md)|Contient des informations pour le [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) élément sur une requête à exécuter pour déterminer si une source de données a été modifiée.|  
|[Élément ReportFormatParameter &#40; ASSL &#41;](../../../analysis-services/scripting/objects/reportformatparameter-element-asl.md)|Contient le nom et la valeur d’un paramètre qui spécifie comment un [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] rapport est mis en forme au moment de l’exécution.|  
|[Élément ReportParameter &#40; ASSL &#41;](../../../analysis-services/scripting/objects/reportparameter-element-assl.md)|Contient le nom et la valeur d'un paramètre qui est transmis à un rapport [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] au moment de l'exécution.|  
|[Élément role &#40; ASSL &#41;](../../../analysis-services/scripting/objects/role-element-assl.md)|Contient des informations à propos d'un rôle de sécurité.|  
|[Server, élément &#40; ASSL &#41;](../../../analysis-services/scripting/objects/server-element-assl.md)|Décrit une instance de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].|  
|[Élément ServerProperty &#40; ASSL &#41;](../../../analysis-services/scripting/objects/serverproperty-element-assl.md)|Définit une propriété de serveur associée à un [Server](../../../analysis-services/scripting/objects/server-element-assl.md) élément.|  
|[Élément SkippedLevelsColumn &#40; ASSL &#41;](../../../analysis-services/scripting/objects/skippedlevelscolumn-element-assl.md)|Fournit les détails d'une colonne qui stocke le nombre de niveaux omis (vides) entre chaque membre et son parent.|  
|[Élément SourceMeasureGroup &#40; ASSL &#41;](../../../analysis-services/scripting/objects/sourcemeasuregroup-element-assl.md)|Identifie le groupe de mesures servant de source de données à une colonne de structure d'exploration de données.|  
|[Élément TableNotification &#40; ASSL &#41;](../../../analysis-services/scripting/objects/tablenotification-element-assl.md)|Contient des informations pour le [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) élément sur une table ou une vue dans une source de données qui a été modifiée.|  
|[Élément trace &#40; ASSL &#41;](../../../analysis-services/scripting/objects/trace-element-assl.md)|Définit une trace qui peut être interrogée.|  
|[Élément Translation &#40; ASSL &#41;](../../../analysis-services/scripting/objects/translation-element-assl.md)|Fournit une traduction localisée pour le parent de la collection [Translations](../../../analysis-services/scripting/collections/translations-element-assl.md) .|  
|[Élément UnaryOperatorColumn &#40; ASSL &#41;](../../../analysis-services/scripting/objects/unaryoperatorcolumn-element-assl.md)|Définit les détails d'une colonne qui fournit un opérateur unaire.|  
|[Élément UnknownMemberTranslation &#40; ASSL &#41;](../../../analysis-services/scripting/objects/unknownmembertranslation-element-assl.md)|Contient une traduction de la légende de la [UnknownMember](../../../analysis-services/scripting/properties/unknownmember-element-assl.md) , élément pour un [Dimension](../../../analysis-services/scripting/objects/dimension-element-assl.md) élément.|  
|[Élément ValueColumn &#40; ASSL &#41;](../../../analysis-services/scripting/objects/valuecolumn-element-assl.md)|Identifie la colonne qui fournit la valeur de l'élément parent.|  
  
## <a name="see-also"></a>Voir aussi  
 [Analysis Services Scripting Language hiérarchie des éléments XML &#40; ASSL &#41;](../../../analysis-services/scripting/analysis-services-scripting-language-xml-element-hierarchy-assl.md)  
  
  
