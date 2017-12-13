---
title: "Gérer les modifications apportées aux vues de sources de données et Sources de données | Documents Microsoft"
ms.custom: 
ms.date: 03/01/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- modifying data sources
- modifying data source views
- data source views [Analysis Services], schema updates
- data sources [Analysis Services], schema updates
ms.assetid: 928c9f63-365a-43fd-9bbd-78828cc7e54d
caps.latest.revision: "25"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: eb5937621d3cb583f599bbcb28bdc635cd12f3a2
ms.sourcegitcommit: f1a6944f95dd015d3774a25c14a919421b09151b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2017
---
# <a name="manage-changes-to-data-source-views-and-data-sources"></a>Gérer des modifications dans les vues de source de données et les sources de données
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]Lorsque l’Assistant génération de schéma est relancé, il réutilise la même source de données et la vue de source de données utilisée pour la génération d’origine. Si vous ajoutez une source de données ou une vue de source de données, l'Assistant ne l'utilise pas. Si vous supprimez la source de données ou la vue de source de données d'origine après la génération initiale, vous devez exécuter l'Assistant depuis le début. Toutes les options précédemment définies dans l'Assistant sont également supprimées. Tous les objets existants d'une base de données sous-jacente qui étaient liés à une source de données ou une vue de source de données supprimée sont traités comme des objets créés par l'utilisateur lorsque vous exécutez l'Assistant Génération de schéma la fois suivante.  
  
 Si la vue de source de données ne reflète pas l'état réel de la base de données sous-jacente au moment de la génération, l'Assistant Génération de schéma risque de rencontrer des erreurs en générant le schéma pour la base de données de la zone de sujet. Par exemple, si la vue de source de données spécifie qu’une colonne a le type de données **int**, alors qu’il s’agit en fait du type **string**, l’Assistant Génération de schéma définit le type de données **INT** pour la clé étrangère afin de la faire correspondre à la vue de source de données, puis il ne parvient pas à créer la relation car le véritable type de données de cette colonne est **string**.  
  
 D'un autre côté, si vous modifiez la chaîne de connexion à la source de données en spécifiant une base de données différente de celle de la génération précédente, aucune erreur ne se produit. La nouvelle base de données est utilisée, et aucune modification n'est apportée à la base de données précédente.  
  
## <a name="see-also"></a>Voir aussi  
 [Présentation de la génération incrémentielle](../../analysis-services/multidimensional-models/understanding-incremental-generation.md)  
  
  
