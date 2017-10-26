---
title: "Les données d’exploration de données de référence des instructions Extensions (DMX) | Documents Microsoft"
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
dev_langs:
- DMX
helpviewer_keywords:
- Data Mining Extensions [Analysis Services], statements
- DMX [Analysis Services], statements
- statements [DMX], reference
- mining models [Analysis Services], training
- mining structures [DMX]
- mining models [Analysis Services], options
- mining structures [DMX], options
ms.assetid: 9cfa1db4-0f21-4fa3-8158-f94c48987e1b
caps.latest.revision: 31
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: e7c9740eebec925bc2b25c6437f488f898288a1e
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="data-mining-extensions-dmx-statements"></a>Instructions Data Mining Extensions (DMX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Utilisation des données des modèles d’exploration de données [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] implique les principales tâches suivantes :  
  
-   Création de structures et de modèles d'exploration de données  
  
-   Traitement des structures et des modèles d'exploration de données  
  
-   Suppression de structures ou de modèles d'exploration de données  
  
-   Copie de modèles d'exploration de données  
  
-   Parcourir les modèles d’exploration de données  
  
-   Prévision dans des modèles d'exploration de données  
  
 Vous pouvez utiliser les instructions DMX (Data Mining Extensions) pour exécuter chacune de ces tâches par programme.  
  
 Création de structures et de modèles d'exploration de données  
 Utilisez le [CREATE MINING STRUCTURE &#40; DMX &#41;](../dmx/create-mining-structure-dmx.md) instruction pour ajouter une nouvelle structure d’exploration de données à une base de données. Vous pouvez ensuite utiliser le [ALTER MINING STRUCTURE &#40; DMX &#41;](../dmx/alter-mining-structure-dmx.md) instruction pour ajouter des modèles d’exploration de données à la structure d’exploration de données.  
  
 Utilisez le [créer un modèle d’exploration de données &#40; DMX &#41;](../dmx/create-mining-model-dmx.md) instruction pour créer la structure d’exploration de données associé et de modèle d’exploration de données.  
  
 Traitement des structures et des modèles d'exploration de données  
 Utilisez le [INSERT INTO &#40; DMX &#41;](../dmx/insert-into-dmx.md) instruction pour traiter une structure et un modèle d’exploration de données.  
  
 Suppression de structures ou de modèles d'exploration de données  
 Utilisez le [Supprimer &#40; DMX &#41;](../dmx/delete-dmx.md) instruction pour supprimer toutes les données d’apprentissage à partir d’un modèle ou une structure d’exploration de données. Utilisez le [DROP MINING STRUCTURE &#40; DMX &#41;](../dmx/drop-mining-structure-dmx.md) ou [supprimer le modèle d’exploration de données &#40; DMX &#41;](../dmx/drop-mining-model-dmx.md) instructions pour le supprimer complètement une structure ou un modèle d’exploration de données à partir d’une base de données.  
  
 Copie de modèles d'exploration de données  
 Utilisez le [SELECT INTO &#40; DMX &#41;](../dmx/select-into-dmx.md) instruction pour copier la structure d’un modèle d’exploration de données existant dans un nouveau modèle d’exploration de données et pour l’apprentissage du nouveau modèle avec les mêmes données.  
  
 Parcourir les modèles d’exploration de données  
 Utilisez le [SELECT &#40; DMX &#41;](../dmx/select-dmx.md) instruction pour rechercher les informations que l’algorithme d’exploration de données calcule et stocke dans le modèle d’exploration de données pendant l’apprentissage du modèle. Comme avec [!INCLUDE[tsql](../includes/tsql-md.md)], vous pouvez utiliser plusieurs clauses avec l’instruction SELECT, d’étendre sa puissance. Ces clauses incluent [DISTINCT FROM \<modèle >](../dmx/select-distinct-from-model-dmx.md), [FROM \<modèle >. CAS](../dmx/select-from-model-cases-dmx.md), [FROM \<modèle >. SAMPLE_CASES](../dmx/select-from-model-sample-cases-dmx.md), [FROM \<modèle >. CONTENU](../dmx/select-from-model-content-dmx.md) et [FROM \<modèle >. DIMENSION_CONTENT](../dmx/select-from-model-dimension-content-dmx.md).  
  
 Prévision dans des modèles d'exploration de données  
 Utilisez le [PREDICTION JOIN](../dmx/select-from-model-prediction-join-dmx.md) clause de l’instruction SELECT pour créer des prédictions basées sur un modèle d’exploration de données existant.  
  
 Vous pouvez également importer et exporter des modèles à l’aide de la [importation &#40; DMX &#41;](../dmx/import-dmx.md) et [exportation &#40; DMX &#41;](../dmx/export-dmx.md) instructions.  
  
 Ces tâches sont classées en deux catégories, les instructions de définition de données et les instructions de manipulation de données, décrites dans les tableaux ci-dessous.  
  
|Rubrique| Description|  
|-----------|-----------------|  
|[Les Extensions d’exploration de données &#40; DMX &#41; Instructions de définition de données](../dmx/dmx-statements-data-definition.md)|Fait partie du langage de définition de données (DDL). utilisé pour définir un nouveau modèle d'exploration de données (y compris l'apprentissage) ou pour supprimer un modèle d'exploration de données existant d'une base de données.|  
|[Les Extensions d’exploration de données &#40; DMX &#41; Instructions de Manipulation de données](../dmx/dmx-statements-data-manipulation.md)|Fait partie du langage de manipulation de données (DML). Est utilisé pour utiliser les modèles d'exploration de données existants, notamment pour explorer un modèle ou pour créer des prévisions.|  
  
## <a name="see-also"></a>Voir aussi  
 [Les Extensions d’exploration de données &#40; DMX &#41; Référence de fonction](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Référence des opérateurs](../dmx/data-mining-extensions-dmx-operator-reference.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Conventions de syntaxe](../dmx/data-mining-extensions-dmx-syntax-conventions.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Éléments de syntaxe](../dmx/data-mining-extensions-dmx-syntax-elements.md)  
  
  

