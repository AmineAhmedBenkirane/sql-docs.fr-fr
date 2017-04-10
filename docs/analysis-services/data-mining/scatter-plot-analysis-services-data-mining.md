---
title: "Nuage de points (Analysis Services&#160;- Exploration de donn&#233;es) | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
  - "analysis-services/data-mining"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "graphiques [Analysis Services]"
  - "modèles d’exploration de données [Analysis Services], validation"
  - "graphiques à nuages de points"
  - "algorithmes de régression [Analysis Services]"
ms.assetid: 166812ec-fd1c-47c8-88db-d5041142be91
caps.latest.revision: 20
author: "Minewiskan"
ms.author: "owend"
manager: "jhubbard"
caps.handback.revision: 20
---
# Nuage de points (Analysis Services&#160;- Exploration de donn&#233;es)
  Un *nuage de points* représente graphiquement les valeurs réelles de vos données par rapport aux valeurs prédites par le modèle. Le nuage de points affiche les valeurs réelles le long de l'axe des X et les valeurs prédites le long de l'axe des Y. Il affiche également une ligne qui illustre la prédiction parfaite, où la valeur prédite correspond exactement à la valeur réelle. La distance d'un point par rapport à cette ligne à un angle idéal de 45 degrés indique le niveau d'exactitude ou d'inexactitude de la prédiction.  
  
## Fonctionnement du nuage de points  
 Considérons un modèle dans lequel le département marketing prédit les ventes quotidiennes basées sur le nombre de clics sur un lien envoyé dans un message électronique promotionnel. Étant donné que le nombre de clics et le volume des ventes sont des valeurs numériques continues, vous pouvez tracer le nombre de clics en tant que variable indépendante et les ventes en tant que variable dépendante. Ce faisant, la ligne droite affiche la relation linéaire attendue, et les points éparpillés autour de cette ligne montrent comment les données réelles divergent de celles attendues. Cette analyse vous indique, d'un seul coup d'œil, le degré de corrélation d'un ensemble de résultats avec une entrée particulière, et le degré de variation par rapport au modèle idéal.  
  
## Interprétation des résultats  
 Le diagramme suivant présente un exemple de nuage de points, créé pour le scénario qui vient d'être décrit.  
  
 ![exemple de nuage de points pour régression linéaire](../../analysis-services/data-mining/media/scatterplot-callctr.gif "exemple de nuage de points pour régression linéaire")  
  
 Vous pouvez positionner la souris sur n'importe quel point éparpillé autour de la ligne pour afficher les valeurs prédite et réelle dans une info-bulle. Il n’y a aucune **légende d’exploration de données** pour un nuage de points ; toutefois, le graphique lui-même contient une légende qui affiche le score associé au modèle. Pour plus d’informations sur l’interprétation du score, consultez [Contenu du modèle d’exploration de données pour les modèles de régression linéaire &#40;Analysis Services - Exploration de données&#41;](../../analysis-services/data-mining/mining-model-content-for-linear-regression-models-analysis-services-data-mining.md).  
  
 Vous pouvez copier la représentation visuelle du graphique dans le Presse-papiers, mais pas la formule ou les données sous-jacentes. Si vous voulez afficher la formule de régression pour la ligne, vous pouvez créer une requête de contenu sur le modèle. Pour plus d’informations, consultez [Exemples de requête de modèle de régression linéaire](../../analysis-services/data-mining/linear-regression-model-query-examples.md).  
  
## Restrictions sur les nuages de points  
 Un nuage de points peut être créé uniquement si le modèle que vous choisissez sous l’onglet **Sélection d’entrée** contient un attribut prédictible continu. Vous ne devez effectuer aucune sélection supplémentaire. Le type de graphique de nuage de points est automatiquement affiché sous l’onglet **Graphique de courbes d’élévation** en fonction du modèle et du type d’attribut.  
  
 Bien que les modèles de séries chronologiques prédisent des nombres continus, vous ne pouvez pas mesurer la précision d'un modèle de série chronologique en utilisant un nuage de points. Il existe d'autres méthodes que vous pouvez utiliser, comme la réservation d'une partie des données historiques. Pour plus d’informations, consultez [Exemples de requêtes de modèle de série chronologique](../../analysis-services/data-mining/time-series-model-query-examples.md).  
  
## Contenu connexe  
 Les rubriques suivantes contiennent davantage d'informations sur la façon dont vous pouvez créer et utiliser les nuages de points et graphiques d'analyse de précision associés.  
  
|Rubriques|Liens|  
|------------|-----------|  
|Propose une procédure pas à pas permettant de créer un graphique de courbes d'élévation pour le modèle de publipostage ciblé.|[Didacticiel sur l'exploration de données de base](../Topic/Basic%20Data%20Mining%20Tutorial.md)<br /><br /> [Test de la précision à l’aide de graphiques de courbes d’élévation &#40;Didacticiel sur l’exploration de données de base&#41;](../Topic/Testing%20Accuracy%20with%20Lift%20Charts%20\(Basic%20Data%20Mining%20Tutorial\).md)|  
|Explique les types de graphique associés.|[Graphique de courbes d’élévation &#40;Analysis Services - Exploration de données&#41;](../../analysis-services/data-mining/lift-chart-analysis-services-data-mining.md)<br /><br /> [Graphique des bénéfices &#40;Analysis Services - Exploration de données&#41;](../../analysis-services/data-mining/profit-chart-analysis-services-data-mining.md)<br /><br /> [Matrice de classification &#40;Analysis Services - Exploration de données&#41;](../../analysis-services/data-mining/classification-matrix-analysis-services-data-mining.md)|  
|Décrit les utilisations de la validation croisée pour les modèles et les structures d'exploration de données.|[Validation croisée &#40;Analysis Services - Exploration de données&#41;](../../analysis-services/data-mining/cross-validation-analysis-services-data-mining.md)|  
|Décrit les étapes permettant de créer des graphiques de courbes d'élévation et d'autres graphiques d'analyse de précision.|[Tâches de test et validation et procédures &#40;exploration des données&#41;](../../analysis-services/data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md)|  
  
## Voir aussi  
 [Test et validation &#40;exploration de données&#41;](../../analysis-services/data-mining/testing-and-validation-data-mining.md)  
  
  