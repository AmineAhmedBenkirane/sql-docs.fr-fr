---
title: "Supprimer une r&#232;gle d&#39;entreprise (Master Data Services) | Microsoft Docs"
ms.custom: 
  - "SQL2016_New_Updated"
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "master-data-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "suppression de règles d'entreprise [Master Data Services]"
  - "règles d’entreprise [Master Data Services], suppression"
ms.assetid: b97aa4f9-569f-451d-ad62-65b81f980299
caps.latest.revision: 7
author: "sabotta"
ms.author: "carlasab"
manager: "jhubbard"
caps.handback.revision: 7
---
# Supprimer une r&#232;gle d&#39;entreprise (Master Data Services)
  Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], supprimez une règle d'entreprise lorsque vous n'en avez plus besoin.  
  
> [!NOTE]  
>  Vous pouvez empêcher la validation des données par rapport à une règle d'entreprise en l'excluant, plutôt qu'en la supprimant. Pour plus d’informations, consultez [Exclure une règle d’entreprise &#40;Master Data Services&#41;](../master-data-services/exclude-a-business-rule-master-data-services.md).  
  
## Conditions préalables  
 Pour effectuer cette procédure :  
  
-   Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .  
  
-   Vous devez être administrateur de modèle. Pour plus d’informations, consultez [Administrateurs &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
### Pour supprimer une règle d'entreprise  
  
1.  Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.  
  
2.  Dans la barre de menus, pointez sur **Gérer** et cliquez sur **Règles d'entreprise**.  
  
3.  Dans la page **Règles d’entreprise**, sélectionnez un modèle dans la liste déroulante **Modèle**.  
  
4.  Dans la liste déroulante **Entité**, sélectionnez une entité.  
  
5.  Dans la liste **Types de membres**, sélectionnez un type de membre auquel appliquer la règle d’entreprise.  
  
6.  Dans la grille, cliquez sur la ligne pour la règle d'entreprise à supprimer.  
  
7.  Cliquez sur **Supprimer**.  
  
8.  Dans la boîte de dialogue de confirmation, cliquez sur **OK**. La valeur de la colonne **État de la règle d’entreprise** est **Suppression en attente**.  
  
9. Cliquez sur **Tout publier**.  
  
10. Dans la boîte de dialogue de confirmation, cliquez sur **OK**. La règle d’entreprise supprimée n’est plus affichée dans la grille.  
  
## Voir aussi  
 [Exclure une règle d’entreprise &#40;Master Data Services&#41;](../master-data-services/exclude-a-business-rule-master-data-services.md)   
 [Créer et publier une règle d’entreprise &#40;Master Data Services&#41;](../master-data-services/create-and-publish-a-business-rule-master-data-services.md)   
 [Règles d’entreprise &#40;Master Data Services&#41;](../master-data-services/business-rules-master-data-services.md)  
  
  