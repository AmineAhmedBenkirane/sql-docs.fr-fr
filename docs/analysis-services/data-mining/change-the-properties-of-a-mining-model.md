---
title: "Modifier les propri&#233;t&#233;s d&#39;un mod&#232;le d&#39;exploration de donn&#233;es | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
  - "analysis-services/data-mining"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "modèles d’exploration de données [Analysis Services], propriétés"
  - "propriétés [data mining]"
ms.assetid: aefaeb7f-d174-48d1-a188-0987a3b1196b
caps.latest.revision: 38
author: "Minewiskan"
ms.author: "owend"
manager: "jhubbard"
caps.handback.revision: 38
---
# Modifier les propri&#233;t&#233;s d&#39;un mod&#232;le d&#39;exploration de donn&#233;es
  Certaines propriétés du modèle d'exploration de données s'appliquent au modèle dans son ensemble, et d'autres propriétés de modèle s'appliquent à des colonnes individuelles. La propriété **Extraction**, qui spécifie si les données de cas doivent être disponibles pour l’interrogation, et la propriété **Description** sont des exemples de propriétés qui s’appliquent à l’ensemble du modèle. Les propriétés qui s’appliquent à la colonne sont **Utilisation** et **ModelingFlags**, qui contrôlent l’utilisation des données de la colonne dans le modèle.  
  
 Les propriétés de modèle suivantes ont des éditeurs avancés que vous pouvez utiliser pour créer des expressions ou pour configurer les propriétés de modèle complexes. Les propriétés suivantes fournissent :  
  
-   Propriété **Filtre** : ouvre la boîte de dialogue [Filtre de jeu de données ou Filtre de modèle](../Topic/Data%20Set%20Filter%20or%20Model%20Filter%20Dialog%20Box.md).  
  
-   Propriété **AlgorithmParameters** : ouvre la [Boîte dialogue Paramètres d’algorithme &#40;vue Modèles d’exploration de données&#41;](../Topic/Algorithm%20Parameters%20Dialog%20Box%20\(Mining%20Models%20View\).md).  
  
 Pour plus d’informations sur la définition des propriétés dans un modèle d’exploration, consultez [Colonnes de modèle d’exploration de données](../../analysis-services/data-mining/mining-model-columns.md).  
  
### Pour modifier les propriétés d'un modèle d'exploration de données  
  
1.  Sous l’onglet **Modèles d’exploration de données** du Concepteur d’exploration de données, cliquez avec le bouton droit sur l’en-tête de colonne contenant le nom du modèle d’exploration de données ou sur la ligne de la grille qui contient le nom de l’algorithme d’exploration de données, puis sélectionnez **Propriétés**.  
  
2.  Dans la fenêtre **Propriétés** à droite de l’écran, mettez en surbrillance la valeur qui correspond à la propriété à modifier, puis entrez la nouvelle valeur.  
  
     La nouvelle valeur est appliquée lorsque vous sélectionnez un élément différent dans le concepteur.  
  
### Pour modifier les propriétés d'une colonne de modèle d'exploration de données  
  
1.  Sous l’onglet **Modèles d’exploration de données** du Concepteur d’exploration de données, cliquez avec le bouton droit sur la cellule de la grille à l’intersection de la colonne de la structure d’exploration de données et du modèle d’exploration de données, puis sélectionnez **Propriétés**.  
  
2.  Dans la fenêtre **Propriétés** à droite de l’écran, mettez en surbrillance la valeur qui correspond à la propriété à modifier, puis entrez la nouvelle valeur.  
  
    > [!NOTE]  
    >  Si l’utilisation de la colonne est définie sur **Ignorer**, la fenêtre **Propriétés** pour la colonne est vide.  
  
     La nouvelle valeur est appliquée lorsque vous sélectionnez un élément différent dans le concepteur.  
  
## Voir aussi  
 [Tâches du modèle d'exploration de données et procédures](../../analysis-services/data-mining/mining-model-tasks-and-how-tos.md)  
  
  