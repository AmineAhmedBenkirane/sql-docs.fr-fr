---
title: Supprimer une Table | Documents Microsoft
ms.custom: ''
ms.date: 02/22/2018
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.component: data-mining
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: be4ed45f-fde3-466c-9869-49bd3ddb505e
caps.latest.revision: 9
author: Minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 981fae53def2e7501d0acb23746db8e7619bc1c7
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="delete-a-table"></a>Supprimer une table
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]
  Dans le générateur de modèles, vous pouvez supprimer des tables dont vous n'avez plus besoin dans votre base de données model de l'espace de travail. La suppression d’une table n’affecte pas les données sources d’origine, mais uniquement les données que vous avez importées et que vous utilisiez. Vous ne pouvez pas annuler la suppression d'une table.  
  
### <a name="to-delete-a-table"></a>Pour supprimer une table  
  
-   Cliquez avec le bouton droit sur l’onglet situé au bas du générateur de modèles pour la table à supprimer, puis sélectionnez **Supprimer**.  
  
## <a name="considerations-when-deleting-tables"></a>Considérations à prendre en compte lors de la suppression de tables  
  
-   Lorsque vous supprimez une table, l'onglet tout entier sur lequel se trouvait la table est supprimé.  
  
-   Si des mesures étaient associées à cette table, la définition de la mesure est également supprimée.  
  
-   Si vous avez créé des colonnes calculées à l'aide de cette table, les colonnes de cette table sont également supprimées ; toutes les colonnes calculées dans d'autres tables qui utilisent les colonnes de la table supprimée affichent une erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [Tables et colonnes](../../analysis-services/tabular-models/tables-and-columns-ssas-tabular.md)  
  
  
