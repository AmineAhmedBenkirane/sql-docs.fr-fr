---
title: Verrouiller une version (Master Data Services) | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: mds
ms.service: 
ms.component: master-data-services
ms.reviewer: 
ms.suite: sql
ms.technology: master-data-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- versions [Master Data Services], locking
- locking versions [Master Data Services]
ms.assetid: 7bb62a84-12d8-4b29-9b6e-6aa25410618e
caps.latest.revision: "7"
author: smartysanthosh
ms.author: nagavo
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 069108c50ed5304d6bdee009b7d7cdd8c878d2a5
ms.sourcegitcommit: 7f8aebc72e7d0c8cff3990865c9f1316996a67d5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2017
---
# <a name="lock-a-version-master-data-services"></a>Verrouiller une version (Master Data Services)
  Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], verrouillez une version d’un modèle pour empêcher que des modifications ne soient apportées aux membres du modèle et à leurs attributs.  
  
> [!NOTE]  
>  Quand une version est verrouillée, les super utilisateurs et les administrateurs de modèle peuvent continuer à ajouter, à modifier et à supprimer des membres. Les autres utilisateurs qui ont une autorisation sur le modèle peuvent consulter les membres uniquement.  
  
## <a name="prerequisites"></a>Conditions préalables  
 Pour effectuer cette procédure :  
  
-   Vous devez être administrateur de modèle. Pour plus d’informations, consultez [Administrateurs &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
-   L’état de la version doit être **Ouvert**.  
  
-   Vous devez avoir l’autorisation d’accéder à la zone fonctionnelle Gestion des versions. Pour plus d’informations, consultez [Autorisations de zone fonctionnelle &#40;Master Data Services&#41;](../master-data-services/functional-area-permissions-master-data-services.md).  
  
### <a name="to-lock-a-version"></a>Pour verrouiller une version  
  
1.  Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Gestion des versions**.  
  
2.  Dans la page **Gérer les versions** , sélectionnez la ligne de la version à verrouiller.  
  
3.  Cliquez sur **Verrouiller**.  
  
4.  Dans la boîte de dialogue de confirmation, cliquez sur **OK**.  
  
## <a name="next-steps"></a>Étapes suivantes  
  
-   [Valider une version par rapport aux règles d’entreprise &#40;Master Data Services&#41;](../master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
-   [Activer une version &#40;Master Data Services&#41;](../master-data-services/commit-a-version-master-data-services.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Versions &#40;Master Data Services&#41;](../master-data-services/versions-master-data-services.md)   
 [Déverrouiller une version &#40;Master Data Services&#41;](../master-data-services/unlock-a-version-master-data-services.md)  
  
  
