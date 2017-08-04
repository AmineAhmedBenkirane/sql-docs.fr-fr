---
title: SELECT (DMX) | Documents Microsoft
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SELECT
dev_langs:
- DMX
helpviewer_keywords:
- browsing mining model [Analysis Services]
- TOP clause, SELECT
- FLATTENED option
- predictions [DMX]
- ORDER BY clause [DMX]
- SELECT statement [DMX]
- mining models [Analysis Services], browsing
- statements [DMX], SELECT statement
- WHERE clause, DMX
ms.assetid: 32d9e8fd-796b-4e1c-ae59-73cd6f645485
caps.latest.revision: 43
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: c012d5fd04ed19665964119d0a0985b08ff2c7c8
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="select-dmx"></a>SELECT (DMX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Le **sélectionnez** instruction dans les Extensions DMX (Data Mining) est utilisée pour les tâches suivantes dans l’exploration de données :  
  
-   Exploration du contenu d'un modèle d'exploration de données existant  
  
-   Création de prévisions à partir d'un modèle d'exploration de données existant  
  
-   Création d'une copie d'un modèle d'exploration de données existant  
  
-   Navigation dans la structure d'exploration de données  
  
 Bien que la syntaxe complète de cette instruction soit complexe, les principales clauses utilisées pour naviguer dans un modèle et sa structure sous-jacente peuvent être résumées comme suit :  
  
```  
SELECT [FLATTENED] [TOP <n>] <select list>  
FROM <model/structure>[.aspect]  
[WHERE <condition expression>]  
[ORDER BY <expression>[DESC|ASC]]  
```  
  
## <a name="flattened"></a>FLATTENED  
 Certains clients d'exploration de données n'acceptent pas les jeux de résultats en format hiérarchique provenant d'un fournisseur d'exploration de données. Ces clients n'ont peut-être pas la possibilité de gérer les hiérarchies ou ils doivent stocker les résultats dans une table dénormalisée unique. Pour convertir les données provenant de tables imbriquées en tables à plat, vous devez exiger que les résultats de requête soient aplatis.  
  
 Pour aplatir les résultats de requête, utilisez la **sélectionnez** syntaxe avec le **FLATTENED** option, comme indiqué dans l’exemple suivant :  
  
```  
SELECT FLATTENED <select list> FROM ...  
```  
  
## <a name="top-n-and-order-by"></a>HAUT \<n > et ORDER BY  
 Vous pouvez trier les résultats d’une requête à l’aide d’une expression, puis de retourner un sous-ensemble des résultats en utilisant une combinaison de la **ORDER BY** et **haut** clauses. Ceci s'avère utile dans les scénarios du type publipostage ciblé dans lesquels vous souhaitez uniquement envoyer les résultats aux personnes les plus probables. Vous pouvez classer les résultats d’une requête de prédiction de publipostage par la probabilité de prédiction de cible et puis retourner uniquement la partie supérieure \<n > résultats.  
  
## <a name="select-list"></a>Select list  
 Le  *\<liste de sélection >* peuvent inclure des références de colonnes scalaires, fonctions de prédiction et des expressions. Les options disponibles dépendent de l'algorithme et des contextes suivants :  
  
-   si vous interrogez une structure ou un modèle d'exploration de données ;  
  
-   si vous interrogez du contenu ou des cas ;  
  
-   si les données sources correspondent à une table relationnelle ou un cube ;  
  
-   si vous effectuez des prédictions.  
  
 Dans de nombreux cas, vous pouvez utiliser des alias ou créer des expressions simples basées sur les éléments de la liste de sélection. Par exemple, l'exemple suivant illustre une expression simple sur les colonnes du modèle :  
  
```  
SELECT [CustomerID], [Last Name] + ', ' + [FirstName] AS FullName  
FROM <model>.CASES  
```  
  
 L'exemple suivant crée un alias pour une colonne qui contient les résultats d'une fonction de prédiction :  
  
```  
SELECT Predict([Column1], 'Value') as Column1Prediction  
FROM MyModel  
JOIN <source data query>  
```  
  
## <a name="where"></a>WHERE  
 Vous pouvez limiter les cas qui sont retournées par la requête en utilisant un **où** clause. Le **où** spécifie les références de cette colonne dans la **où** l’expression doit avoir la même sémantique que les références de colonne dans la  *\<liste de sélection >* de la **sélectionnez** instruction et peut, renvoie uniquement une expression booléenne. La syntaxe de la **où** est la clause suivante  
  
```  
WHERE < condition expression >  
```  
  
 La liste de sélection et **où** clause d’une **sélectionnez** instruction doit respecter les règles suivantes :  
  
-   La liste de sélection doit contenir une expression qui ne retourne pas de résultat booléen. Vous pouvez modifier l'expression, mais celle-ci doit retourner des résultats non booléens.  
  
-   Le **où** clause doit contenir une expression qui retourne un résultat booléen. Vous pouvez modifier la clause, mais celle-ci doit retourner un résultat booléen.  
  
## <a name="predictions"></a>Prévisions  
 Vous pouvez utiliser deux types de syntaxe pour la création des prévisions :  
  
-   [SELECT FROM &#60; modèle &#62; JOINTURE de prédiction &#40; DMX &#41;](../dmx/select-from-model-prediction-join-dmx.md)  
  
-   [SELECT FROM &#60; modèle &#62; &#40; DMX &#41;](../dmx/select-from-model-dmx.md)  
  
 Le premier type de prévision permet de créer des prévisions complexes, en temps réel ou par traitement.  
  
 Le deuxième type de prévision crée une jointure de prévision vide sur une colonne prédictible dans un modèle d'exploration de données, et retourne l'état le plus probable de la colonne. Les résultats de cette requête dépendent intégralement du contenu du modèle d'exploration de données.  
  
 Vous pouvez insérer une instruction select dans la requête source d’une instruction SELECT FROM PREDICTION JOIN à l’aide de la syntaxe suivante.  
  
```  
SELECT FROM PREDICTION JOIN (<SELECT statement>) AS t, WHERE <SELECT statement>  
```  
  
 Pour plus d’informations sur la création de requêtes de prédiction, consultez [Structure et l’utilisation de requêtes de prédiction DMX](../dmx/structure-and-usage-of-dmx-prediction-queries.md).  
  
## <a name="clause-syntax"></a>Syntaxe des clauses  
 En raison de la complexité de la navigation avec le **sélectionnez** instruction, les éléments de syntaxe détaillée et les arguments décrits par clause. Pour plus d'informations sur chaque clause, cliquez sur une rubrique dans la liste suivante :  
  
 [SELECT DISTINCT FROM &#60; modèle &#62; &#40; DMX &#41;](../dmx/select-distinct-from-model-dmx.md)  
  
 [SELECT FROM &#60; modèle &#62;. CONTENU &#40; DMX &#41;](../dmx/select-from-model-content-dmx.md)  
  
 [SELECT FROM &#60; modèle &#62;. CAS &#40; DMX &#41;](../dmx/select-from-model-cases-dmx.md)  
  
 [SELECT FROM &#60; modèle &#62;. SAMPLE_CASES &#40; DMX &#41;](../dmx/select-from-model-sample-cases-dmx.md)  
  
 [SELECT FROM &#60; modèle &#62;. DIMENSION_CONTENT &#40; DMX &#41;](../dmx/select-from-model-dimension-content-dmx.md)  
  
 [SELECT FROM &#60; modèle &#62; JOINTURE de prédiction &#40; DMX &#41;](../dmx/select-from-model-prediction-join-dmx.md)  
  
 [SELECT FROM &#60; modèle &#62; &#40; DMX &#41;](../dmx/select-from-model-dmx.md)  
  
 [SELECT FROM &#60; structure &#62;. CAS](../dmx/select-from-structure-cases.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Les Extensions d’exploration de données &#40; DMX &#41; Instructions de définition de données](../dmx/dmx-statements-data-definition.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Instructions de Manipulation de données](../dmx/dmx-statements-data-manipulation.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Référence des instructions](../dmx/data-mining-extensions-dmx-statements.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Instructions de Manipulation de données](../dmx/dmx-statements-data-manipulation.md)  
  
  

