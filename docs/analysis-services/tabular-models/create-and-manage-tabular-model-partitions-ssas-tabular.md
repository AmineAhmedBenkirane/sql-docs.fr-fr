---
title: "Créer et gérer des Partitions de modèles tabulaires | Documents Microsoft"
ms.custom: 
ms.date: 02/22/2018
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: 
ms.component: data-mining
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dab72cf0-95bc-4b63-95dc-505b5cd881c1
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 1dfe0ae7dd1ee92cd365a34cf6502d8358c474cb
ms.sourcegitcommit: d8ab09ad99e9ec30875076acee2ed303d61049b7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="create-and-manage-tabular-model-partitions"></a>Créer et gérer des partitions de modèles tabulaires
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]

  Les partitions divisent une table en sections logiques. Chaque partition peut ensuite être traitée (actualisée) indépendamment d'autres partitions. Les partitions définies pour un modèle au cours de la création de modèles sont dupliquées dans un modèle déployé. Une fois le déploiement terminé, vous pouvez gérer ces partitions à l'aide de la boîte de dialogue **Partitions** dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou à l'aide d'un script. Les tâches fournies dans cette rubrique décrivent comment créer et gérer des partitions pour un modèle déployé.  
  
  > [!NOTE]  
>  Partitions dans les modèles tabulaires créés au niveau de compatibilité 1400 sont définies à l’aide d’une instruction de requête M. Pour plus d’informations, consultez [M référence](https://msdn.microsoft.com/library/mt211003.aspx). 
>
  
## <a name="tasks"></a>Tâches  
 Pour créer et gérer des partitions d'une base de données de modèle tabulaire déployée, vous utiliserez la boîte de dialogue **Partitions** dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]. Pour afficher la boîte de dialogue **Partitions** , dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], cliquez avec le bouton droit sur une table, puis cliquez sur **Partitions**.  
  
###  <a name="bkmk_create_new"></a> Pour créer une nouvelle partition  
  
1.  Dans la boîte de dialogue **Partitions** , cliquez sur le bouton **Nouveau** .  
  
2.  Dans **Nom de la partition**, tapez un nom pour la partition. Par défaut, le nom de la partition par défaut est numéroté de manière incrémentielle pour chaque nouvelle partition.  
  
3.  Dans **instruction de requête**, tapez ou collez une instruction de requête SQL ou M qui définit les colonnes et toutes les clauses que vous souhaitez inclure dans la partition dans la fenêtre de requête.  
  
4.  Pour valider l'instruction, cliquez sur **Vérifier la syntaxe**.  
  
###  <a name="bkmk_copy"></a> Pour copier une partition  
  
1.  Dans la boîte de dialogue **Partitions** , dans la liste **Partitions** , sélectionnez la partition à copier, puis cliquez sur le bouton **Copier** .  
  
2.  Dans **Nom de la partition**, tapez un nouveau nom pour la partition.  
  
3.  Dans **instruction de requête**, modifiez l’instruction de requête.  
  
###  <a name="bkmk_merge"></a> Pour fusionner deux ou plusieurs partitions  
  
-   Dans la boîte de dialogue **Partitions** , dans la liste **Partitions** , utilisez Ctrl+clic pour sélectionner les partitions à fusionner, puis cliquez sur le bouton **Fusionner** .  
  
> [!IMPORTANT]  
>  Le fait de fusionner les partitions ne met pas à jour les métadonnées des partitions. Vous devez modifier l’instruction SQL ou M pour la partition résultante s’assurer que les opérations de traitement traitent toutes les données dans la partition fusionnée.  
  
###  <a name="bkmk_delete"></a> Pour supprimer une partition  
  
-   Dans la boîte de dialogue **Partitions** , dans la liste **Partitions** , sélectionnez la partition à supprimer, puis cliquez sur le bouton **Supprimer** .  
  
## <a name="see-also"></a>Voir aussi  
 [Partitions de modèles tabulaires](../../analysis-services/tabular-models/tabular-model-partitions-ssas-tabular.md)   
 [Partitions de processus de modèles tabulaires](../../analysis-services/tabular-models/process-tabular-model-partitions-ssas-tabular.md)  
  
  
