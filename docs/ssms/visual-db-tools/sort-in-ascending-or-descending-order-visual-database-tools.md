---
title: "Trier par ordre croissant ou décroissant (Visual Database Tools) | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: ssms-visual-db
ms.reviewer: 
ms.suite: sql
ms.technology: tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- descending sorts
- ascending sorts
ms.assetid: d61cc55b-9ee8-4ecf-a32f-6459ae43910b
caps.latest.revision: "3"
author: stevestein
ms.author: sstein
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 7d9dc0f7b18b198a7c31a658c5f4de90dc12ebb8
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="sort-in-ascending-or-descending-order-visual-database-tools"></a>Trier par ordre croissant ou décroissant (Visual Database Tools)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)] Vous pouvez trier des résultats de requête par ordre croissant ou décroissant sur une ou plusieurs des colonnes dans le jeu de résultats en utilisant les mots clés **ASC** ou **DESC** avec la clause **ORDER BY**.  
  
> [!NOTE]  
> L'ordre de tri est déterminé en partie par la séquence de classement de la colonne. Vous pouvez modifier cette séquence dans la [boîte de dialogue Classement](../../ssms/visual-db-tools/collation-dialog-box-visual-database-tools.md).  
  
La procédure suivante suppose que vous ayez une requête ouverte dans le Concepteur de requêtes et de vues qui utilise la clause ORDER BY pour trier une ou plusieurs colonnes.  
  
### <a name="to-specify-or-change-the-order-in-which-results-are-sorted"></a>Pour spécifier ou modifier l'ordre dans lequel les résultats sont triés  
  
1.  Dans le [volet Critères](../../ssms/visual-db-tools/criteria-pane-visual-database-tools.md), cliquez sur le champ **Type de tri** pour la colonne que vous souhaitez réorganiser.  
  
2.  Choisissez **Croissant** ou **Décroissant** pour spécifier l'ordre de tri pour la colonne.  
  
Remarquez qu'au fur et à mesure que vous travaillez dans le volet Critères, la clause UNION de votre requête se modifie pour correspondre à vos actions les plus récentes.  
  
> [!NOTE]  
> Lorsque vous triez des résultats par plusieurs colonnes, spécifiez l'ordre dans lequel la recherche doit être effectuée à l'aide de la colonne Ordre de tri. Pour plus d’informations, consultez [Trier plusieurs colonnes dans des requêtes &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/sort-multiple-columns-in-queries-visual-database-tools.md).  
  
## <a name="see-also"></a> Voir aussi  
[Trier et regrouper des résultats de requête &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/sort-and-group-query-results-visual-database-tools.md)  
[Résumer les résultats de la requête &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/summarize-query-results-visual-database-tools.md)  
[Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
