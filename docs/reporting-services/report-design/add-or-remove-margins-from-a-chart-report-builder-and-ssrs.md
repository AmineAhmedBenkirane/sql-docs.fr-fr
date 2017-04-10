---
title: "Ajouter ou supprimer des marges dans un graphique (G&#233;n&#233;rateur de rapports et SSRS) | Microsoft Docs"
ms.custom: ""
ms.date: "03/03/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "reporting-services-sharepoint"
  - "reporting-services-native"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 91c43f58-5771-4d33-a54d-0e802d2f5cba
caps.latest.revision: 8
author: "maggiesMSFT"
ms.author: "maggies"
manager: "erikre"
caps.handback.revision: 8
---
# Ajouter ou supprimer des marges dans un graphique (G&#233;n&#233;rateur de rapports et SSRS)
Pour les types de graphiques Histogrammes et Nuages de points dans les rapports paginés [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], le graphique ajoute automatiquement des marges latérales aux extrémités de l’axe des abscisses. Dans les graphiques à barres, le graphique ajoute automatiquement des marges latérales aux extrémités de l'axe des ordonnées. Dans tous les autres types de graphiques, aucune marge latérale n'est ajoutée. Vous ne pouvez pas modifier la taille de la marge.  
  
 Cette rubrique ne s'applique pas aux types de graphiques à secteurs, en anneau, en entonnoir ni en pyramide.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## Pour activer ou désactiver les marges latérales  
  
1.  Cliquez avec le bouton droit sur l’axe, puis sélectionnez **Propriétés de l’axe**. La boîte de dialogue **Propriétés de l’axe vertical** ou **Propriétés de l’axe** s’affiche.  
  
2.  Dans la page **Options de l’axe**, définissez la propriété **Marges latérales** :  
  
    -   **Automatique** Le graphique détermine s’il faut ajouter une marge latérale en fonction du type de graphique.  
  
    -   **Désactivé** Les graphiques à barres, histogrammes et nuages de points n’ont pas de marges latérales.  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## Voir aussi  
 [Mise en forme des étiquettes des axes sur un graphique &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md)   
 [Boîte de dialogue Propriétés de l’axe, Options de l’axe &#40;Générateur de rapports et SSRS&#41;](../Topic/Axis%20Properties%20Dialog%20Box,%20Axis%20Options%20\(Report%20Builder%20and%20SSRS\).md)   
 [Spécifier un intervalle d’axe &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/specify-an-axis-interval-report-builder-and-ssrs.md)   
 [Mettre en forme les étiquettes des axes en tant que dates ou devises &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md)   
 [Graphiques &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)  
  
  