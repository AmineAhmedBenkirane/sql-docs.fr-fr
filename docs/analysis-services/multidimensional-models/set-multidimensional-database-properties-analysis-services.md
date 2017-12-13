---
title: "Définir les propriétés de base de données multidimensionnelle (Analysis Services) | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: properties [Analysis Services], databases
ms.assetid: a8be5b3f-3148-448a-976c-7222705155d9
caps.latest.revision: "24"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: bc30fcf0cf1aad8b9c27585913f0a5a8a4598374
ms.sourcegitcommit: f1a6944f95dd015d3774a25c14a919421b09151b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2017
---
# <a name="set-multidimensional-database-properties-analysis-services"></a>Définir les propriétés de base de données multidimensionnelle (Analysis Services)
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]Il existe un certain nombre de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] propriétés que vous pouvez configurer dans la base de données le [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] le Concepteur de base de données.  
  
 Ce concepteur vous permet d'effectuer les tâches suivantes :  
  
-   Si vous êtes connecté à la base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en mode en ligne, vous pouvez modifier le nom de la base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] . Si vous utilisez le mode projet, vous pouvez modifier le nom du prochain déploiement du projet. Pour plus d’informations, consultez [Renommer une base de données multidimensionnelle &#40;Analysis Services&#41;](../../analysis-services/multidimensional-models/rename-a-multidimensional-database-analysis-services.md) et [Configurer les propriétés d’un projet Analysis Services &#40;SSDT&#41;](../../analysis-services/multidimensional-models/configure-analysis-services-project-properties-ssdt.md).  
  
-   Vous pouvez fournir une description de la base de données pouvant être présentée aux utilisateurs. En outre, vous pouvez afficher le nom de la base de données, mais pas le modifier. Pour modifier le nom de la base de données, vous devez modifier les propriétés du projet.  
  
-   Vous pouvez fournir la traduction du nom et de la description de la base de données dans une ou plusieurs langues. Pour plus d’informations, consultez [Traductions de cube](../../analysis-services/multidimensional-models-olap-logical-cube-objects/cube-translations.md), [Traductions de dimension](../../analysis-services/multidimensional-models-olap-logical-dimension-objects/dimension-translations.md)et [Prise en charge des traductions dans Analysis Services](../../analysis-services/translation-support-in-analysis-services.md).  
  
-   Vous pouvez afficher et modifier les mappages de types de compte par défaut. Les mappages de type de compte sont utilisés quand une ou plusieurs mesures font appel à la fonction d’agrégation *ByAccount* . Pour chaque type de compte, vous pouvez spécifier un alias et modifier la fonction d'agrégation par défaut associé au type de compte. Pour plus d’informations sur la modification de l’agrégation par défaut, consultez [Définir le comportement semi-additif](../../analysis-services/multidimensional-models/define-semiadditive-behavior.md).  
  
## <a name="database-properties"></a>Propriétés de la base de données  
 Outre les éléments ci-dessus, vous pouvez configurer plusieurs propriétés d'une base de données dans la fenêtre Propriétés.  
  
|Propriété|Description|  
|--------------|-----------------|  
|Préfixe d'agrégation|Préfixe commun pouvant être utilisé pour les noms d'agrégation de toutes les partitions d'une base de données. Pour plus d’informations, consultez [Élément AggregationPrefix &#40;ASSL&#41;](../../analysis-services/scripting/properties/aggregationprefix-element-assl.md).|  
|Classement|Si le projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] est déployé sur une instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , la base de données hérite de la propriété de classement du serveur, sauf si une valeur différente est spécifiée ici.|  
|DataSourceImpersonationInfo|Indique le mode d'emprunt d'identité par défaut pour tous les objets de source de données dans la base de données. Il s’agit du mode utilisé par le service [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pendant le traitement des objets, la synchronisation des serveurs et l’exécution des instructions d’exploration de données OpenQuery et SystemOpenSchema.|  
|Taille estimée|Fournit la taille estimée des fichiers de base de données sur le disque. Si les données sont stockées dans plusieurs emplacements, cette estimation sera limitée aux fichiers de données stockés sous le dossier de la base de données.<br /><br /> **Taille estimée** peut également être utilisé comme base d’estimation de la mémoire. En général, la configuration requise pour la mémoire est supérieure à la taille des données sur le disque en raison des structures de données supplémentaires qui sont créées lors du chargement de la base de données dans la mémoire.<br /><br /> Pour affiner la configuration requise pour la mémoire, vous pouvez également utiliser le Gestionnaire des tâches afin d'examiner la mémoire de traitement Analysis Services avant et après le traitement de la base de données et observer la mémoire utilisée pour comprendre la configuration requise pour la mémoire de la base de données.|  
|Langage|Si le projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] est déployé dans une instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , la base de données hérite de la propriété de langue du serveur, sauf si une valeur différente est spécifiée ici.|  
|MasterDataSource ID|Utilisé avec les partitions distantes. Pour plus d’informations, consultez [Partitions distantes](../../analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-remote-partitions.md).|  
  
## <a name="see-also"></a>Voir aussi  
 [Boîte de dialogue Propriétés de la base de données &#40;SSAS - Multidimensionnelle&#41;](http://msdn.microsoft.com/library/70f000b7-917f-4699-b142-7a0d13ff767c)   
 [Configurer les propriétés d’un projet Analysis Services &#40;SSDT&#41;](../../analysis-services/multidimensional-models/configure-analysis-services-project-properties-ssdt.md)  
  
  
