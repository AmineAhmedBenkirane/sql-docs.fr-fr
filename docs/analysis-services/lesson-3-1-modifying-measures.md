---
title: Modification des mesures | Documents Microsoft
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: tutorial
ms.reviewer: 
ms.suite: sql
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: get-started-article
applies_to:
- SQL Server 2016
ms.assetid: 7bd48810-15ce-45ff-862b-372d08606995
caps.latest.revision: 14
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: On Demand
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 350fadc471d30f79b8b1e6b1e8d63cc507f1d484
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="lesson-3-1---modifying-measures"></a>Leçon 3-1-modification des mesures
Vous pouvez utiliser la propriété **FormatString** pour définir des paramètres de mise en forme qui contrôlent comment les mesures sont affichées aux utilisateurs. Au cours de cette tâche, vous allez spécifier des propriétés de formatage pour les mesures relatives aux devises et aux pourcentages dans le cube du didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .  
  
### <a name="to-modify-the-measures-of-the-cube"></a>Pour modifier les mesures du cube  
  
1.  Affichez l’onglet **Structure de cube** du Concepteur de cube pour le cube du didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , développez le groupe de mesures **Internet Sales** dans le volet **Mesures** , cliquez avec le bouton droit sur **Order Quantity**, puis choisissez **Propriétés**.  
  
2.  Dans la fenêtre des propriétés, cliquez sur l'icône en forme de punaise **Masquer automatiquement** pour épingler la fenêtre des propriétés.  
  
    Il est plus facile de modifier les propriétés de plusieurs éléments à la fois dans le cube lorsque la fenêtre des propriétés reste ouverte.  
  
3.  Dans la fenêtre Propriétés, cliquez sur la liste **FormatString** , puis tapez **#,#**.  
  
4.  Dans la barre d'outils de l'onglet **Structure de cube** , cliquez sur l'icône **Afficher la grille de mesures** à gauche.  
  
    L'affichage de la grille permet de sélectionner plusieurs mesures en même temps.  
  
5.  Sélectionnez l'une des mesures suivantes. Vous pouvez sélectionner plusieurs mesures en cliquant sur chacune d'elles tout en maintenant enfoncée la touche CTRL :  
  
    -   **Unit Price**  
  
    -   **Extended Amount**  
  
    -   **Discount Amount**  
  
    -   **Product Standard Cost**  
  
    -   **Total Product Cost**  
  
    -   **Sales Amount**  
  
    -   **Tax Amt**  
  
    -   **Freight**  
  
6.  Dans la fenêtre des propriétés, dans la liste **FormatString** , sélectionnez **Currency**.  
  
7.  Dans la zone de liste déroulante en haut de la fenêtre des propriétés (sous la barre de titre), sélectionnez la mesure **Unit Price Discount Pct**, puis sélectionnez **Percent** dans la liste **FormatString** .  
  
8.  Dans la fenêtre des propriétés, remplacez la propriété **Name** de la mesure **Unit Price Discount Pct** par **Unit Price Discount Percentage**.  
  
9. Dans le volet **Mesures** , cliquez sur **Tax Amt** et remplacez le nom de cette mesure par **Tax Amount**.  
  
10. Dans la fenêtre des propriétés, cliquez sur l'icône **Masquer automatiquement** pour masquer la fenêtre des propriétés, puis cliquez sur **Afficher l'arborescence de mesures** dans la barre d'outils de l'onglet **Structure de cube** .  
  
11. Dans le menu **Fichier** , cliquez sur **Enregistrer tout**.  
  
## <a name="next-task-in-lesson"></a>Tâche suivante de la leçon  
[Modification de la dimension Customer](../analysis-services/lesson-3-2-modifying-the-customer-dimension.md)  
  
## <a name="see-also"></a>Voir aussi  
[Définir des dimensions de base de données](../analysis-services/multidimensional-models/define-database-dimensions.md)  
[Configurer des propriétés de mesure](../analysis-services/multidimensional-models/configure-measure-properties.md)  
  
  
  

