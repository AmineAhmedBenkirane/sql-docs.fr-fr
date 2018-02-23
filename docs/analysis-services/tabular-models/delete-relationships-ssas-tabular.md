---
title: Supprimer des relations | Documents Microsoft
ms.custom: 
ms.date: 02/22/2018
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: 
ms.component: multidimensional-tabular
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d40e3f05-54e8-4c4b-807a-0b06f446079b
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 690224c1798494e75f6b26add07d51c3afa7134f
ms.sourcegitcommit: d8ab09ad99e9ec30875076acee2ed303d61049b7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="delete-relationships"></a>Supprimer des relations 
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]
Vous pouvez supprimer des relations existantes à l'aide du générateur de modèles dans la vue de diagramme ou à l'aide de la boîte de dialogue Gérer les relations. Pour plus d’informations sur l’utilisation des relations dans les modèles tabulaires, consultez [relations](../../analysis-services/tabular-models/relationships-ssas-tabular.md).  
  
## <a name="considerations-for-deleting-relationships"></a>Considérations relatives à la suppression de relations  
 Gardez à l'esprit les points suivants lorsque vous décidez de supprimer ou non une relation :  
  
-   Il n'existe aucune méthode permettant d'annuler la suppression d'une relation. Vous pouvez recréer la relation, mais cette opération requiert le recalcul complet des formules dans le modèle. Par conséquent, effectuez toujours des vérifications avant de supprimer une relation utilisée dans des formules.  
  
-   La suppression d'une relation entre deux tables peut provoquer des erreurs dans les formules qui référencent ces tables.  
  
-   La fonction DAX (Data Analysis Expression) RELATED utilise les relations entre des tables pour rechercher des valeurs associées dans une autre table. Elle génèrera des résultats différents après la suppression de la relation. Pour plus d'informations, consultez la fonction RELATED (DAX).  
  
-   Outre la modification des résultats des tableaux croisés dynamiques et des formules, la création et la suppression de relations entraînent le recalcul du classeur, ce qui peut prendre du temps.  
  
## <a name="delete-relationships"></a>Supprimer des relations  
  
#### <a name="to-delete-a-relationship-by-using-diagram-view"></a>Pour supprimer une relation à l'aide de la vue de diagramme  
  
1.  Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], cliquez sur le menu **Modèle** , puis pointez sur **Vue du modèle**, et enfin sur **Vue de diagramme**.  
  
2.  Cliquez avec le bouton droit sur une ligne de relation entre deux tables, puis cliquez sur **Supprimer**.  
  
#### <a name="to-delete-a-relationship-by-using-the-manage-relationships-dialog-box"></a>Pour supprimer une relation à l'aide de la boîte de dialogue Gérer les relations.  
  
1.  Dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], cliquez sur le menu **Table** , puis sur **Gérer les relations**.  
  
2.  Dans la boîte de dialogue **Gérer les relations** , sélectionnez une ou plusieurs relations dans la liste.  
  
     Pour sélectionner plusieurs relations, maintenez la touche Ctrl enfoncée pendant que vous cliquez sur chaque relation.  
  
3.  Cliquez sur **Supprimer la relation**.  
  
4.  Dans la boîte de dialogue **Gérer les relations** , cliquez sur **Fermer**.  
  
## <a name="see-also"></a>Voir aussi  
 [Relationships](../../analysis-services/tabular-models/relationships-ssas-tabular.md)   
 [Créer une relation](../../analysis-services/tabular-models/create-a-relationship-between-two-tables-ssas-tabular.md)  
  
  
