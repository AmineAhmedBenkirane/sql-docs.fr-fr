---
title: "Créer un groupe de hiérarchies récursives (Générateur de rapports et SSRS) | Documents Microsoft"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b830ba5-4d64-4348-a2b1-76b9338a1462
caps.latest.revision: 8
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: Machine Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 2adde1d53084f92ee16822c5b6d04a886f31fe28
ms.contentlocale: fr-fr
ms.lasthandoff: 06/22/2017

---
# <a name="create-a-recursive-hierarchy-group-report-builder-and-ssrs"></a>Créer un groupe de hiérarchies récursives (Générateur de rapports et SSRS)
Dans les rapports paginés [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , un groupe de hiérarchies récursives organise les données d’un dataset de rapport unique qui inclut plusieurs niveaux hiérarchiques, tels que la structure de rapports pour les relations entre directeur et employé dans une hiérarchie d’organisation.  
  
 Avant de pouvoir organiser les données d'une table comme un groupe de hiérarchies récursives, vous devez avoir un dataset unique qui contient toutes les données hiérarchiques. En outre, vous devez disposer de champs distincts pour l'élément à grouper et l'élément en fonction duquel le regroupement est effectué. Par exemple, un dataset où vous souhaitez regrouper les employés de manière récursive sous leur responsable, peut contenir un nom, un nom d'employé, un ID d'employé et un ID de responsable.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="to-create-a-recursive-hierarchy-group"></a>Pour créer un groupe de hiérarchies récursives  
  
1.  En mode Conception, ajoutez une table et faites glisser les champs de dataset à afficher. En général, le champ que vous souhaitez afficher comme une hiérarchie figure dans la première colonne.  
  
2.  Cliquez avec le bouton droit n'importe où dans la table pour la sélectionner. Le volet de regroupement affiche le groupe de détails pour la table sélectionnée. Dans le volet Groupes de lignes, cliquez avec le bouton droit sur **Détails**, puis cliquez sur **Modifier le groupe**. La boîte de dialogue **Propriétés du groupe** s’ouvre.  
  
3.  Dans **Expressions Groupe**, cliquez **Ajouter**. Une nouvelle ligne apparaît dans la grille.  
  
4.  Dans la liste **Grouper sur** , tapez ou sélectionnez le champ de groupement.  
  
5.  Cliquez sur **Avancé**.  
  
6.  Dans la liste **Parent récursif** , entrez ou sélectionnez le champ de groupement.  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     Exécutez le rapport. Le rapport affiche le groupe de hiérarchies récursives, même si aucun retrait n'indique la hiérarchie.  
  
## <a name="to-format-a-recursive-hierarchy-group-with-indent-levels"></a>Pour mettre en forme un groupe de hiérarchies récursives avec des niveaux de retrait  
  
1.  Cliquez sur la zone de texte qui contient le champ auquel vous souhaitez ajouter des niveaux de retrait pour afficher un format de hiérarchie. Les propriétés de la zone de texte s'affichent dans le volet Propriétés.  
  
    > [!NOTE]  
    >  Si vous ne voyez pas le volet Propriétés, cliquez sur **Propriétés** sous l’onglet **Affichage** .  
  
2.  Dans le volet Propriétés, développez le **remplissage** nœud, cliquez sur **gauche**et dans la liste déroulante, sélectionnez  **\<Expression... >**.  
  
3.  Dans le volet Expression, tapez l'expression suivante :  
  
     `=CStr(2 + (Level()*10)) + "pt"`  
  
     Toutes les propriétés de marge intérieure requièrent une chaîne au format *nnyy*, où  *nn*  est un nombre et *yy* est l’unité de mesure. L’exemple d’expression génère une chaîne utilisant la fonction **Level** pour augmenter la taille du remplissage en fonction du niveau de récursivité. Ainsi, une ligne de niveau 1 implique un remplissage de 12 points (2 + (1\*10)) et une ligne de niveau 3 correspond à un remplissage de 32 points (2 + (3\*10)). Pour plus d’informations sur la fonction **Level** , consultez [Fonction Level](../../reporting-services/report-design/report-builder-functions-level-function.md).  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     Exécutez le rapport. Le rapport affiche une vue hiérarchique des données groupées.  
  
## <a name="see-also"></a>Voir aussi  
 [Création de groupes de hiérarchies récursives &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/creating-recursive-hierarchy-groups-report-builder-and-ssrs.md)   
 [Filtrer, regrouper et trier des données &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/filter-group-and-sort-data-report-builder-and-ssrs.md)   
 [Informations de référence sur les fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/report-builder-functions-aggregate-functions-reference.md)   
 [Tables &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/tables-report-builder-and-ssrs.md)   
 [Matrices &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/create-a-matrix-report-builder-and-ssrs.md)   
 [Listes &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md)   
 [Tables, matrices et listes &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
