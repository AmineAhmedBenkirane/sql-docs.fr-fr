---
title: "Créer un administrateur de modèle (Master Data Services) | Documents Microsoft"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- administrators [Master Data Services], creating
ms.assetid: dae17afc-3b39-490e-b51f-2d8da26d429e
caps.latest.revision: 6
author: sabotta
ms.author: carlasab
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 637227399e0ecd6c1feb1f75b95e38d0b370d816
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="create-a-model-administrator-master-data-services"></a>Créer un administrateur de modèle (Master Data Services)
  Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], créez un administrateur de modèle quand vous souhaitez qu’un groupe ou un utilisateur ait toutes les autorisations sur tous les objets dans un ou plusieurs modèles.  
  
> [!TIP]  
>  Pour simplifier l'administration, créez un groupe Windows ou local et configurez-le comme un administrateur de modèle. Vous pouvez ensuite ajouter et supprimer des utilisateurs dans le groupe sans accéder à l'interface utilisateur de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].  
  
## <a name="prerequisites"></a>Conditions préalables  
 Pour effectuer cette procédure :  
  
-   Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Autorisations d'accès** .  
  
-   Vous devez être administrateur de modèle. Pour plus d’informations, consultez [Administrateurs &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
### <a name="to-create-a-model-administrator"></a>Pour créer un administrateur de modèle  
  
1.  Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Autorisations d'accès**.  
  
2.  Dans la page **Utilisateurs** ou **Groupes** , sélectionnez la ligne de l'utilisateur ou du groupe à modifier.  
  
3.  Cliquez sur **Modifier l'utilisateur sélectionné**.  
  
4.  Cliquez sur l'onglet **Modèles** .  
  
5.  Dans la liste **Modèle** , sélectionnez éventuellement un modèle.  
  
6.  Cliquez sur **Modifier**.  
  
7.  Cliquez sur le modèle auquel vous souhaitez affecter une autorisation.  
  
8.  Dans le menu, sélectionnez **Administrateur**.  
  
9. Effectuez les étapes 7 et 8 pour chaque modèle que vous souhaitez que le groupe ou l'utilisateur administre.  
  
10. Cliquez sur **Enregistrer**.  
  
## <a name="see-also"></a>Voir aussi  
 [Administrateurs &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md)   
 [Affecter des autorisations d’objet modèle &#40; Master Data Services &#41;](../master-data-services/assign-model-object-permissions-master-data-services.md)   
 [Affecter des autorisations des membres de hiérarchie &#40; Master Data Services &#41;](../master-data-services/assign-hierarchy-member-permissions-master-data-services.md)   
 [Autorisations d’objet modèle &#40; Master Data Services &#41;](../master-data-services/model-object-permissions-master-data-services.md)   
 [Autorisations des membres de hiérarchie &#40; Master Data Services &#41;](../master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  
