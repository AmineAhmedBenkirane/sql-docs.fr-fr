---
title: Modifier ou supprimer des Partitions (Analysis Services - multidimensionnel) | Documents Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- modifying partitions
- partitions [Analysis Services], modifying
ms.assetid: fb7a64ca-d021-4926-b92d-83476fbc40a3
caps.latest.revision: 30
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 4a253d7cc22d90a06369a914b7aec8b4a8ec315f
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="edit-or-delete-partitions-analyisis-services---multidimensional"></a>Modifier ou supprimer des partitions (Analysis Services - Multidimensionnel)
  Les partitions de cube sont modifiées à l’aide de l’onglet **Partitions** du Concepteur de cube dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]. L’onglet **Partitions** répertorie les partitions pour tous les groupes de mesures d’un cube. Il répertorie également les partitions d'écriture différée pour lesquelles l'écriture différée est activée.  
  
 Pour modifier les partitions d’un groupe de mesures, développez le groupe de mesures sous l’onglet **Partitions** . Les partitions d'un groupe de mesures sont répertoriées par un numéro ordinal dans un format de table dont les colonnes sont répertoriées dans le tableau ci-dessous.  
  
 Les paramètres d'un groupe de mesures lié doivent être modifiés dans le cube source.  
  
 La suppression de partitions se produit automatiquement lorsque vous fusionnez une partition source dans une partition de destination. La partition spécifiée comme source est supprimée une fois la fusion terminée. Vous pouvez également supprimer des partitions manuellement dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou dans l'onglet Partitions de [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]. Cliquez avec le bouton droit, puis sélectionnez **Supprimer**. N'oubliez pas que la suppression d'une partition supprime également les données et les agrégations. Par mesure de précaution, assurez-vous que vous disposez d'une sauvegarde récente de la base de données au cas où vous devriez annuler cette étape ultérieurement.  
  
> [!NOTE]  
>  Vous pouvez également utiliser des scripts XMLA qui automatisent les tâches de création, de fusion et de suppression de partitions. Un script XMLA peut être créé et exécuté dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ou dans des packages SSIS personnalisés qui s’exécutent en tant que tâche planifiée. Pour plus d’informations, consultez [Automatiser les tâches d’administration Analysis Services avec SSIS](../../analysis-services/instances/automate-analysis-services-administrative-tasks-with-ssis.md).  
  
## <a name="partition-source"></a>Source de partition  
 Spécifie la table source ou la requête nommée pour la partition. Pour modifier la table source, cliquez sur la cellule, puis sur le bouton Parcourir (**...**).  
  
 ![Colonne source dans le volet Partition](../../analysis-services/multidimensional-models/media/ssas-partitionsource.png "colonne Source dans le volet Partition")  
  
 Si la partition est basée sur une requête, cliquez sur le bouton Parcourir (**…**) pour modifier la requête. Ceci modifie la propriété **Source** de la partition. Pour plus d’informations, consultez [Modifier une source de partition afin d’utiliser une table de faits différente](../../analysis-services/multidimensional-models/change-a-partition-source-to-use-a-different-fact-table.md).  
  
 Vous pouvez spécifier une table dans la vue de source de données qui a la même structure que la table source d'origine (dans la source de données externe à partir de laquelle les données sont récupérées). La source peut se trouver dans une source de données ou une vue de source de données quelconque de la base de données de cube.  
  
## <a name="storage-settings"></a>Paramètres de stockage  
 Dans le Concepteur de cube, sous l’onglet Partitions, vous pouvez cliquer sur **Paramètres de stockage** pour sélectionner un des paramètres standard pour le stockage MOLAP, ROLAP ou HOLAP, ou configurer des paramètres personnalisés pour le mode de stockage et la mise en cache proactive. La valeur par défaut est MOLAP car elle offre les performances de requête les plus rapides. Pour plus d’informations sur chaque paramètre, consultez [Définir un stockage de partitions &#40;Analysis Services – Multidimensionnel&#41;](../../analysis-services/multidimensional-models/set-partition-storage-analysis-services-multidimensional.md).  
  
 Le stockage peut être configuré séparément pour chacune des partitions de chaque groupe de mesures d'un cube. Vous pouvez également configurer les paramètres de stockage par défaut pour un cube ou un groupe de mesures. Le stockage est configuré sous l’onglet **Partitions** de l’Assistant Cube.  
  
## <a name="see-also"></a>Voir aussi  
 [Créer et gérer une partition locale &#40;Analysis Services&#41;](../../analysis-services/multidimensional-models/create-and-manage-a-local-partition-analysis-services.md)   
 [Conception d’agrégations &#40; Analysis Services - multidimensionnel &#41;](../../analysis-services/multidimensional-models/designing-aggregations-analysis-services-multidimensional.md)   
 [Fusionner des partitions dans Analysis Services &#40;SSAS - Multidimensionnel&#41;](../../analysis-services/multidimensional-models/merge-partitions-in-analysis-services-ssas-multidimensional.md)  
  
  

