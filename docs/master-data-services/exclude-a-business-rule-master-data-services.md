---
title: Exclure une règle d’entreprise (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.service: ''
ms.component: non-specific
ms.reviewer: ''
ms.suite: sql
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules [Master Data Services], excluding
ms.assetid: bdbc9df0-23f7-40b9-8aba-4445c1482580
caps.latest.revision: 7
author: leolimsft
ms.author: lle
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: d3d0ca4ae6b01f2a0de0a85cf83e725956a0f14b
ms.sourcegitcommit: a85a46312acf8b5a59a8a900310cf088369c4150
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="exclude-a-business-rule-master-data-services"></a>Exclure une règle d'entreprise (Master Data Services)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], excluez une règle d'entreprise lorsque vous ne voulez pas supprimer la règle définitivement, mais que vous ne souhaitez pas valider des données par rapport à elle.  
  
## <a name="prerequisites"></a>Prerequisites  
 Pour effectuer cette procédure :  
  
-   Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .  
  
-   Vous devez être administrateur de modèle. Pour plus d’informations, consultez [Administrateurs &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
### <a name="to-exclude-a-business-rule"></a>Pour exclure une règle d'entreprise  
  
1.  Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.  
  
2.  Dans la barre de menus, pointez sur **Gérer** et cliquez sur **Règles d'entreprise**.  
  
3.  Dans la page **Règles d’entreprise** , sélectionnez un modèle dans la liste déroulante **Modèle** .  
  
4.  Dans la liste déroulante **Entité** , sélectionnez une entité.  
  
5.  Dans la liste déroulante **Types de membres** , sélectionnez un type de membre.  
  
6.  Dans la grille, sélectionnez la ligne pour la règle d’entreprise à exclure et cliquez sur **Modifier**.  
  
7.  Cochez la case **Exclu** .  
  
8.  Cliquez sur **Enregistrer**.  
  
9. Cliquez sur **Tout publier**.  
  
10. Dans la boîte de dialogue de confirmation, cliquez sur **OK**. La valeur de la colonne **État de la règle d’entreprise** est **Exclu** et celle de la colonne **Exclu** est **Oui**.  
  
## <a name="see-also"></a> Voir aussi  
 [Supprimer une règle d’entreprise &#40;Master Data Services&#41;](../master-data-services/delete-a-business-rule-master-data-services.md)   
 [Créer et publier une règle d’entreprise &#40;Master Data Services&#41;](../master-data-services/create-and-publish-a-business-rule-master-data-services.md)   
 [Business Rules &#40;Master Data Services&#41;](../master-data-services/business-rules-master-data-services.md)  
  
  
