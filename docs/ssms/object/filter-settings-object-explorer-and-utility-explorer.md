---
title: "Paramètres de filtre (Explorateur d’objets et Explorateur de l’utilitaire) | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology: tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.swb.common.filtersettings.f1
- sql13.ag.job.filtersettings.f1
ms.assetid: 4aab04bc-e1ab-4d4b-ab74-b287fc805bc2
caps.latest.revision: "4"
author: stevestein
ms.author: sstein
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 17bccb5ad0fe065699f2aed56d276568473ea56b
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="filter-settings-object-explorer-and-utility-explorer"></a>Paramètres de filtre (Explorateur d'objets et Explorateur de l'utilitaire)
Cette boîte de dialogue vous permet de spécifier un filtre. Un filtre vous permet de configurer l'Explorateur d'objets et l'Explorateur de l'utilitaire pour qu'ils affichent uniquement les éléments qui correspondent à des critères spécifiques. Par exemple, vous pouvez utiliser un filtre pour afficher uniquement les travaux dont le nom contient le mot « Maintenance ». L’en-tête de la boîte de dialogue **Paramètres du filtre** contient le nom du serveur et peut contenir le nom de la base de données.  
  
## <a name="uielement-list"></a>Liste des éléments de l'interface utilisateur  
**Propriété**  
Indique la propriété sur laquelle filtrer.  
  
**Opérateur**  
Permet de sélectionner la manière dont le filtre applique la valeur à la propriété. Les options suivantes sont possibles :  
  
-   **Égal à**  
  
    Le filtre affiche les éléments pour lesquels la propriété et la valeur correspondent exactement.  
  
-   **Contient**  
  
    Le filtre affiche les éléments pour lesquels la propriété contient la valeur. La propriété peut contenir du texte supplémentaire.  
  
-   **Ne contient pas**  
  
    Le filtre affiche les éléments pour lesquels la propriété ne contient pas la valeur.  
  
-   **Inférieur à**  
  
    Disponible pour les dates, ce filtre affiche les éléments dont la date est antérieure à la valeur fournie.  
  
-   **Inférieur ou égal à**  
  
    Disponible pour les dates, ce filtre affiche les éléments dont la date est antérieure à la valeur fournie ou contient cette valeur.  
  
-   **Supérieur à**  
  
    Disponible pour les dates, ce filtre affiche les éléments dont la date est postérieure à la valeur fournie.  
  
-   **Supérieur ou égal à**  
  
    Disponible pour les dates, ce filtre affiche les éléments dont la date est postérieure à la valeur fournie ou contient cette valeur.  
  
-   **Entre**  
  
    Disponible pour les dates, ce filtre affiche les éléments dont la date est comprise entre deux dates fournies. Sélectionnez **Entre** et appuyez sur Tab pour ajouter une autre ligne afin d’entrer la seconde date.  
  
-   **Non compris entre**  
  
    Disponible pour les dates, ce filtre affiche les éléments dont la date est antérieure ou postérieure aux deux dates fournies. Sélectionnez **Non compris entre** et quittez la colonne **Opérateur** à l’aide des tabulations pour ajouter une ligne afin d’entrer la seconde date.  
  
**Valeur**  
Tapez la valeur à comparer à la propriété. Pour une date, cliquez sur la flèche vers le bas pour afficher un calendrier vous permettant de sélectionner la date.  
  
**Effacer le filtre**  
Supprime tous les paramètres actuels du filtre.  
  
## <a name="see-also"></a>Voir aussi  
[Utiliser SQL Server Management Studio](../../ssms/use-sql-server-management-studio.md)  
[Vue d'ensemble de l'utilitaire SQL Server](http://msdn.microsoft.com/en-us/6e6cbd25-6b1c-4e21-9ade-4584e243fd8f)  
  
