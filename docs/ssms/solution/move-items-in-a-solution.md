---
title: "Déplacer des éléments dans une solution | Microsoft Docs"
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
- moving items
- solutions [SQL Server Management Studio], item relocation
- relocating items
ms.assetid: b40a24eb-f528-4e70-b26e-5eaf6e0ed1ed
caps.latest.revision: 3
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: b0140646e92871aa5d3ab2acbb95b417ab38d28b
ms.contentlocale: fr-fr
ms.lasthandoff: 04/11/2017

---
# <a name="move-items-in-a-solution"></a>Déplacer des éléments dans une solution
Les éléments de projet des projets [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)] sont les requêtes, les connexions et les fichiers divers. Vous pouvez déplacer les requêtes et les fichiers divers d'un projet vers un autre dans l'Explorateur de solutions, mais vous ne pouvez pas déplacer les connexions.  
  
### <a name="to-move-items-in-solution-explorer"></a>Pour déplacer des éléments dans l'Explorateur de solutions  
  
1.  Dans l'Explorateur de solutions, sélectionnez l'élément que vous souhaitez déplacer.  
  
2.  Dans le menu **Edition** , cliquez sur **Couper**.  
  
3.  Dans l'Explorateur de solutions, sélectionnez la destination.  
  
4.  Dans le menu **Edition** , cliquez sur **Coller**.  
  
Vous pouvez déplacer des éléments en faisant glisser les requêtes et les fichiers divers dans l'Explorateur de solutions. Faire glisser ces éléments vous permet de voir le résultat de l'opération de glissement. Les requêtes déplacées d'un type de projet vers un autre peuvent être considérées comme des fichiers divers dans le projet cible.  
  
> [!NOTE]  
> Le déplacement d'une requête connectée n'entraîne pas le déplacement de la connexion vers le projet cible. Une fois déplacée vers le projet cible, la requête perd alors sa connexion.  
  
## <a name="see-also"></a>Voir aussi  
[Explorateur de solutions](../../ssms/solution/solution-explorer.md)  
[Copier des éléments d'une solution](../../ssms/solution/copy-items-in-a-solution.md)  
  

