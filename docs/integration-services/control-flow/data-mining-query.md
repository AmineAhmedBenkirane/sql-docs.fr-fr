---
title: "Requête d’exploration de données | Documents Microsoft"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: control-flow
ms.reviewer: 
ms.suite: sql
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.dts.designer.dataminingquery.f1
ms.assetid: 948e358a-6245-429f-82c7-4cedc5e048fd
caps.latest.revision: 23
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 8809f1e5f91ad5746b66d4640747b1ec0a923f0f
ms.contentlocale: fr-fr
ms.lasthandoff: 08/03/2017

---
# <a name="data-mining-query"></a>Requête d'exploration de données
  Le volet de conception contient le Générateur de requêtes de prévisions d'exploration de données, qui peut servir à créer des requêtes de prévisions d'exploration de données. Vous pouvez concevoir des requêtes de prévisions basées sur des tables d'entrée ou des requêtes de prévisions singleton. Passez à la vue de résultat pour exécuter la requête et afficher les résultats. La vue de la requête affiche la requête DMX (Data Mining Extensions) créée par le Générateur de requêtes de prévisions d'exploration de données.  
  
## <a name="options"></a>Options  
 Bouton de basculement entre les vues  
 Cliquez sur une icône pour basculer entre le volet de conception et le volet de requête. Par défaut, le volet de conception est ouvert.  
  
 Pour basculer vers le volet de conception, cliquez sur le ![icône conception](../../integration-services/control-flow/media/ssis-designicon.gif "icône conception") icône.  
  
 Pour basculer vers le volet de requête, cliquez sur le ![icône SQL](../../integration-services/control-flow/media/ssis-queryicon.gif "icône SQL") icône.  
  
 **Modèle d'exploration de données**  
 Choisissez le modèle d'exploration de données sur lequel vous souhaitez baser vos prévisions.  
  
 **Sélectionner un modèle**  
 Ouvre la boîte de dialogue **Sélectionnez un modèle d’exploration de données** .  
  
 **Colonnes d'entrée**  
 Affiche les colonnes d'entrée sélectionnées utilisées pour générer les prévisions.  
  
 **Source**  
 Sélectionnez dans la liste déroulante la source contenant le champ qui sera utilisé pour la colonne. Vous pouvez utiliser le modèle d’exploration de données sélectionné dans la table **Modèle d’exploration de données** , la ou les tables d’entrée sélectionnées dans la table **Sélectionner une ou plusieurs tables d’entrée** , une fonction de prédiction ou une expression personnalisée.  
  
 Les colonnes des tables contenant le modèle d'exploration de données et les colonnes d'entrée peuvent être glissées et déplacées sur la cellule.  
  
 **Champ**  
 Sélectionnez une colonne dans la liste des colonnes dérivées de la table source. Si vous avez sélectionné **Fonction de prédiction** dans **Source**, cette cellule contient une liste déroulante des fonctions de prédiction disponibles pour le modèle d’exploration de données sélectionné.  
  
 **Alias**  
 Nom de la colonne retourné par le serveur.  
  
 **Afficher**  
 Sélectionnez cette option pour retourner la colonne ou pour utiliser la colonne uniquement dans la clause WHERE.  
  
 **Grouper**  
 Utilisez cette option avec la colonne **et/ou** pour regrouper les expressions. Par exemple, (expr1 OU expr2) ET expr3.  
  
 **et/ou**  
 Utilisez cette option pour créer une requête logique. Par exemple, (expr1 OU expr2) ET expr3.  
  
 **Critères/Argument**  
 Spécifiez une condition ou une expression utilisateur qui s'applique à la colonne. Les colonnes des tables contenant le modèle d'exploration de données et les colonnes d'entrée peuvent être glissées et déplacées sur la cellule.  
  
## <a name="see-also"></a>Voir aussi  
 [Outils de requête d'exploration de données](../../analysis-services/data-mining/data-mining-query-tools.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Référence des instructions](../../dmx/data-mining-extensions-dmx-statements.md)  
  
  

