---
title: "Sélectionner les lignes ne correspondant pas à une valeur (Visual Database Tools) | Microsoft Docs"
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
- search conditions [SQL Server], rows not matching value
- row not matching value [SQL Server]
- NOT operator [Visual Database Tools]
- search criteria [SQL Server], rows not matching value
ms.assetid: 19898578-7b2f-401c-bb8f-9f2a017efdf7
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 64c4f182e369f8e51a4b1381c5774c951ea5e738
ms.lasthandoff: 04/11/2017

---
# <a name="select-rows-that-do-not-match-a-value-visual-database-tools"></a>Sélectionner les lignes ne correspondant pas à une valeur (Visual Database Tools)
Pour rechercher des lignes ne correspondant pas à une valeur, utilisez l'opérateur NOT.  
  
### <a name="to-find-rows-that-do-not-match-a-value"></a>Pour rechercher des lignes ne correspondant pas à une valeur  
  
1.  Si ce n’est déjà fait, ajoutez les colonnes ou les expressions que vous souhaitez utiliser dans votre condition de recherche au [volet Critères](../../ssms/visual-db-tools/criteria-pane-visual-database-tools.md).  
  
2.  Localisez la ligne comportant l’expression ou la colonne de données à rechercher, puis entrez l’opérateur NOT suivi d’une valeur de recherche dans la colonne de la grille **Filtre** .  
  
Si vous souhaitez, par exemple, rechercher toutes les lignes figurant dans une table `products` dans laquelle les valeurs de la colonne des codes produits commencent par un autre caractère que « A », vous pouvez alors entrer la condition de recherche suivante :  
  
```  
NOT LIKE 'A%'  
```  
  
## <a name="see-also"></a>Voir aussi  
[Règles pour l'entrée de valeurs de recherche (Visual Database Tools)](../../ssms/visual-db-tools/rules-for-entering-search-values-visual-database-tools.md)  
[Spécifier des critères de recherche (Visual Database Tools)](../../ssms/visual-db-tools/specify-search-criteria-visual-database-tools.md)  
  

