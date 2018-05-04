---
title: Activer l’extraction pour un modèle d’exploration de données | Documents Microsoft
ms.custom: ''
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: data-mining
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], how-to topics
- drillthrough [Analysis Services]
ms.assetid: 4fa44f60-ef9a-4b59-98c0-c0baf1195c8e
caps.latest.revision: 28
author: Minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 516fff1c886a0ae22a3449e513107d9a8e6366b5
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="enable-drillthrough-for-a-mining-model"></a>Activer l'extraction pour un modèle d'exploration de données
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  Si vous avez activé l'extraction pour un modèle d'exploration de données, lorsque vous parcourez le modèle, vous pouvez extraire des informations détaillées sur les cas utilisés pour créer le modèle. Pour consulter cette information, vous devez disposer des autorisations nécessaires et la structure doit déjà avoir été traitée.  
  
 **Autorisations** Pour qu’un utilisateur extraie les données d’un modèle ou d’une structure, il doit être membre d’un rôle qui a les autorisations [AllowDrillThrough](../../analysis-services/scripting/properties/allowdrillthrough-element-assl.md) pour le modèle ou la structure d’exploration de données. Les autorisations d'extraction sont définies séparément sur la structure et le modèle.  
  
-   Les autorisations d'extraction sur le modèle vous permettent d'extraire à partir du modèle, même si vous n'avez pas d'autorisations sur la structure.  
  
-   Les autorisations d’extraction sur la structure permettent en outre d’inclure des colonnes de structure dans les requêtes d’extraction à partir du modèle, à l’aide de la fonction [StructureColumn &#40;DMX&#41;](../../dmx/structurecolumn-dmx.md). Vous pouvez également interroger les scénarios d’apprentissage et de test dans la structure en utilisant la syntaxe SELECT… À partir de \<structure >. Syntaxe de cas.  
  
 **Mise en cache de cas d’apprentissage** L’extraction consiste à récupérer des informations sur les cas d’apprentissage dans la structure d’exploration de données. Ces informations sont mises en cache lorsque la structure est traitée. Par conséquent, si vous choisissez d’effacer toutes les données mises en cache en remplaçant la propriété <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> par **ClearAfterProcessing**, l’extraction ne fonctionne pas.  
  
> [!NOTE]  
>  Si les cas d’apprentissage n’ont pas été mis en cache, vous devez remplacer la propriété <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> par **KeepTrainingCases** , puis retraiter le modèle avant de pouvoir consulter les données de cas.  
  
 Pour plus d’informations, consultez [Requêtes d’extraction &#40;exploration de données&#41;](../../analysis-services/data-mining/drillthrough-queries-data-mining.md).  
  
### <a name="to-enable-drillthrough-on-a-mining-model"></a>Pour activer l'extraction sur un modèle d'exploration de données  
  
1.  Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], sous l’onglet **Modèles d’exploration de données** du Concepteur d’exploration de données, cliquez avec le bouton droit sur le nom du modèle d’exploration de données pour lequel vous voulez activer l’extraction, puis sélectionnez **Propriétés**.  
  
2.  Dans les fenêtres **Propriétés** , cliquez sur **AllowDrillthrough**et sélectionnez **True**.  
  
3.  Sous l’onglet **Modèles d’exploration de données** , cliquez avec le bouton droit sur le modèle et sélectionnez **Traiter le modèle**.  
  
### <a name="to-enable-caching-for-a-mining-structure"></a>Pour activer la mise en cache pour une structure d'exploration de données  
  
1.  Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], sous l’onglet **Structure d’exploration de données** du Concepteur d’exploration de données, cliquez avec le bouton droit sur le nom de la structure d’exploration de données.  
  
2.  Ouvrez la fenêtre **Propriétés** .  
  
3.  Dans la fenêtre **Propriétés** , recherchez la propriété **CacheMode** , puis sélectionnez **KeepTrainingCases** dans la liste.  
  
4.  Dans le menu **Base de données** , sélectionnez **Traiter**.  
  
## <a name="see-also"></a>Voir aussi  
 [Requêtes d’extraction & #40 ; exploration de données & #41 ;](../../analysis-services/data-mining/drillthrough-queries-data-mining.md)  
  
  
