---
title: "Créer des requêtes avec des paramètres sans nom (Visual Database Tools) | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology: tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unnamed parameters
- parameters [SQL Server], unnamed
ms.assetid: 5f4b664b-3d3d-4d07-a0e7-791d78743504
caps.latest.revision: "4"
author: stevestein
ms.author: sstein
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 14c6f54d95a4160922b608cfe184b9775ccb4918
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="create-queries-with-unnamed-parameters-visual-database-tools"></a>Créer des requêtes avec des paramètres sans nom (Visual Database Tools)
Vous pouvez créer une requête avec un paramètre sans nom en spécifiant un point d'interrogation (?) comme espace réservé pour une valeur littérale. Le Concepteur de requêtes et de vues lui donnera un nom temporaire. Vous pouvez définir autant de paramètres sans nom que vous le souhaitez dans la requête.  
  
Lorsque vous exécutez la requête dans le Concepteur de requêtes et de vues, la boîte de dialogue Paramètres de la requête s'affiche avec le nom temporaire.  
  
### <a name="to-specify-an-unnamed-parameter"></a>Pour spécifier un paramètre sans nom  
  
1.  Ajoutez les colonnes ou expressions à rechercher dans le [volet Critères](../../ssms/visual-db-tools/criteria-pane-visual-database-tools.md). Si vous ne souhaitez pas que les colonnes ou expressions de recherche apparaissent dans le résultat de la requête, supprimez-les comme colonnes de sortie.  
  
2.  Recherchez la ligne contenant la colonne de données ou l’expression à rechercher puis, dans la colonne **Filtre** de la grille, entrez un point d’interrogation (?).  
  
    Par défaut, le Concepteur de requêtes et de vues ajoute l'opérateur « = ». Toutefois, vous pouvez modifier la cellule pour le remplacer par « > », « < », ou un autre opérateur de comparaison SQL.  
  
## <a name="see-also"></a>Voir aussi  
[Requête avec des paramètres &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/query-with-parameters-visual-database-tools.md)  
  
