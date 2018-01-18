---
title: "(Niveau de compatibilité 1200) de modélisation tabulaire | Documents Microsoft"
ms.custom: 
ms.date: 01/17/2018
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: get-started-article
applies_to: SQL Server 2016
keywords:
- Analysis Services
- "Modèle tabulaire"
- Didacticiel
- SSAS
ms.assetid: 140d0b43-9455-4907-9827-16564a904268
caps.latest.revision: "40"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Active
ms.openlocfilehash: 20248d68dc0371ef158f287d1f3a8bc9e87360d3
ms.sourcegitcommit: dcac30038f2223990cc21775c84cbd4e7bacdc73
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/18/2018
---
# <a name="tabular-modeling-1200-compatibility-level"></a>Modélisation tabulaire (niveau de compatibilité 1200)
[!INCLUDE[ssas-appliesto-sql2016-later-aas](../includes/ssas-appliesto-sql2016-later-aas.md)]

Ce didacticiel inclut des leçons sur la création d’un modèle tabulaire d’Analysis Services à le [niveau de compatibilité 1200](../analysis-services/tabular-models/compatibility-level-for-tabular-models-in-analysis-services.md) à l’aide de [SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt)et déployer votre modèle à un serveur Analysis Services en local ou dans Azure.  
 
Si vous utilisez SQL Server 2017 ou Azure Analysis Services, et que vous souhaitez créer votre modèle à la compatibilité 1400 niveau, utilisez le [Azure Analysis Services - didacticiel Adventure Works](https://review.docs.microsoft.com/azure/analysis-services/tutorials/aas-adventure-works-tutorial?branch=master). Cette version de mise à jour utilise la fonctionnalité obtenir des données de nouveau, moderne pour vous connecter et importer les données sources et utilise le langage de M pour configurer des partitions.
 
  
## <a name="what-youll-learn"></a>Contenu du didacticiel   
  
-   Comment créer un nouveau projet de modèle tabulaire dans SSDT.
  
-   Importer des données depuis une base de données relationnelle SQL Server dans un projet de modèle tabulaire.  
  
-   Créer et gérer des relations entre des tables dans le modèle.  
  
-   Créer et gérer des calculs, des mesures et des indicateurs de performance clés qui aideront les utilisateurs à analyser les données du modèle.  
  
-   Créer et gérer des perspectives et des hiérarchies qui aideront les utilisateurs à parcourir plus facilement les données du modèle en fournissant des points de vue spécifiques à l'entreprise et à l'application.  
  
-   Créer des partitions qui divisent les données des tables en plus petites parties logiques pouvant être traitées indépendamment des autres partitions.  
  
-   Sécuriser les objets et les données du modèle en créant des rôles à l'aide des membres utilisateurs.  
  
-   Comment déployer un modèle tabulaire à un serveur Analysis Services en local ou dans Azure.  
  
## <a name="scenario"></a>Scénario  
Ce didacticiel est basé sur Adventure Works Cycles, une société fictive. Adventure Works est une société de fabrication multinationale volumineux qui produit et distribue des bicyclettes métalliques et pour les marchés d’Amérique du Nord, Europe et Asie. Avec son siège social à Bothell, Washington, la société emploie 500 employés. En outre, Adventure Works emploie plusieurs équipes commerciales régionales pour couvrir son marché.  
  
Pour améliorer la prise en charge des besoins d'analyse des données des équipes de vente et marketing et des seniors du management, vous devez créer un modèle tabulaire pour que les utilisateurs analysent les données des ventes Internet dans la base de données AdventureWorksDW donnée en exemple.  
  
Pour pouvoir exécuter ce didacticiel et le modèle tabulaire des ventes Internet Adventure Works, vous devez suivre plusieurs leçons. Dans chaque leçon, vous exécuterez une série de tâches ; vous devez effectuer chaque tâche dans l'ordre pour terminer la leçon. Dans une leçon donnée il peut y avoir plusieurs tâches qui accomplissent des résultats similaires, mais comment vous effectuez chaque tâche est légèrement différente. Cela est de montrer qu’il existe souvent plusieurs façons pour effectuer une tâche particulière et à utiliser les compétences que vous avez appris dans les tâches précédentes.  
  
L’objectif des leçons est pour vous guider dans la création d’un modèle tabulaire de base en cours d’exécution en mode In-Memory à l’aide de nombreuses fonctionnalités incluses dans SSDT. Chaque leçon découle de la leçon précédente, c'est pourquoi vous devez effectuer les leçons dans l'ordre. Une fois que vous avez terminé toutes les leçons, vous avez créé et déployé le modèle tabulaire d’exemple Adventure Works Internet Sales sur un serveur Analysis Services.  
  
Ce didacticiel n'inclut pas de leçons ni d'informations sur la gestion d'une base de données de modèles tabulaires déployée à l'aide de SQL Server Management Studio, ou sur l'utilisation d'une application cliente de création de rapports pour se connecter à un modèle déployé et parcourir ses données.  
  
## <a name="prerequisites"></a>Configuration requise  
Pour effectuer ce didacticiel, vous devez les conditions préalables suivantes :  
  
-   La version la plus récente de [ ! INCLURE[ssBIDevStudioFull](../ssdt/download-sql-server-data-tools-ssdt.md).

-   La dernière version de SQL Server Management Studio. [Obtenir la dernière version](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms). 
  
-   Une application cliente telle que [Power BI Desktop](https://powerbi.microsoft.com/desktop/) ou [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel.    
  
-   Une instance de SQL Server avec la base de données exemple Adventure Works DW 2014. Cet exemple de base de données comprend les données nécessaires pour effectuer ce didacticiel. [Obtenir la dernière version](http://go.microsoft.com/fwlink/?LinkID=335807).  
  

-   Un Azure Analysis Services ou SQL Server 2016 instance ou version ultérieure Analysis Services pour déployer votre modèle. [S’inscrire à une évaluation gratuite de Azure Analysis Services](https://azure.microsoft.com/services/analysis-services/).
  
## <a name="lessons"></a>Leçons  
Ce didacticiel inclut les leçons suivantes :  
  
|Leçon|Durée estimée|  
|----------|------------------------------|  
|[Leçon 1 : Créer un projet de modèle tabulaire](../analysis-services/lesson-1-create-a-new-tabular-model-project.md)|10 minutes|  
|[Leçon 2 : Ajouter des données](../analysis-services/lesson-2-add-data.md)|20 minutes|  
|[Leçon 3 : Marquer en tant que table de dates](../analysis-services/lesson-3-mark-as-date-table.md)|3 minutes|  
|[Leçon 4 : Créer des relations](../analysis-services/lesson-4-create-relationships.md)|10 minutes|  
|[Leçon 5 : Créer des colonnes calculées](../analysis-services/lesson-5-create-calculated-columns.md)|15 minutes|
|[Leçon 6 : Créer des mesures](../analysis-services/lesson-6-create-measures.md)|30 minutes|  
|[Leçon 7 : Créer des indicateurs de performance clés](../analysis-services/lesson-7-create-key-performance-indicators.md)|15 minutes|  
|[Leçon 8 : Créer des Perspectives](../analysis-services/lesson-8-create-perspectives.md)|5 minutes|  
|[Leçon 9 : Créer des hiérarchies](../analysis-services/lesson-9-create-hierarchies.md)|20 minutes|  
|[Leçon 10 : Créer des Partitions](../analysis-services/lesson-10-create-partitions.md)|15 minutes|  
|[Leçon 11 : Créer des rôles](../analysis-services/lesson-11-create-roles.md)|15 minutes|  
|[Leçon 12 : Analyser dans Excel](../analysis-services/lesson-12-analyze-in-excel.md)|20 minutes| 
|[Leçon 13 : Déployer](../analysis-services/lesson-13-deploy.md)|5 minutes|  
  
## <a name="supplemental-lessons"></a>Leçons supplémentaires  
Ce didacticiel inclut également des [leçons supplémentaires](http://msdn.microsoft.com/library/2018456f-b4a6-496c-89fb-043c62d8b82e). Les rubriques de cette section ne sont pas requises pour suivre ce didacticiel, mais peuvent être utiles pour mieux comprendre les fonctionnalités de création de modèles tabulaires avancées.  
  
|Leçon|Durée estimée|  
|----------|------------------------------|  
|[Implémentation de la sécurité dynamique à l'aide des filtres de lignes](../analysis-services/supplemental-lesson-implement-dynamic-security-by-using-row-filters.md)|30 minutes|  

  
## <a name="next-step"></a>Étape suivante  
Pour démarrer le didacticiel, passez à la première leçon : [Leçon 1 : Créer un projet de modèle tabulaire](../analysis-services/lesson-1-create-a-new-tabular-model-project.md).  
  
  
  

