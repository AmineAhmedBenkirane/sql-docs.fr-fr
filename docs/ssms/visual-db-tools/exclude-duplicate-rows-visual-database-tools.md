---
title: Exclure les doublons de lignes (Visual Database Tools) | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- search criteria [SQL Server], excluding rows
- row duplicates [SQL Server]
- duplicate rows
- row excluded in search [SQL Server]
- result sets [SQL Server], duplicate values
- excluding rows
ms.assetid: ab35a363-421d-4665-946b-ae3f6397af50
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: bad0e2729b2a0bfa0728d9257194c4adb10a885e
ms.contentlocale: fr-fr
ms.lasthandoff: 04/11/2017

---
# <a name="exclude-duplicate-rows-visual-database-tools"></a>Exclure les doublons de lignes (Visual Database Tools)
Si vous souhaitez afficher uniquement des valeurs uniques dans un jeu de résultats, vous pouvez spécifier qu'il faut exclure les doublons du jeu de résultats.  
  
### <a name="to-exclude-duplicate-rows-from-the-result-set"></a>Pour exclure les doublons du jeu de résultats  
  
1.  Cliquez avec le bouton droit sur un point de l’arrière-plan du volet Schéma, puis choisissez **Propriétés** dans le menu contextuel.  
  
2.  Dans la fenêtre Propriétés, cliquez sur **Valeurs DISTINCT** et affectez-lui la valeur **Oui**.  
  
    Le Concepteur de requêtes et de vues insère le mot clé DISTINCT devant la liste des colonnes affichées dans l'instruction SQL.  
  
    > [!NOTE]  
    > Si vous utilisez le mot clé DISTINCT, il se peut que vous ne puissiez pas modifier le jeu de résultats dans le volet Résultats.  
  
## <a name="see-also"></a>Voir aussi  
[Spécifier des critères de recherche &amp;#40;Visual Database Tools&amp;#41;](../../ssms/visual-db-tools/specify-search-criteria-visual-database-tools.md)  
[Trier et regrouper des résultats de requête &amp;#40;Visual Database Tools&amp;#41;](../../ssms/visual-db-tools/sort-and-group-query-results-visual-database-tools.md)  
  

