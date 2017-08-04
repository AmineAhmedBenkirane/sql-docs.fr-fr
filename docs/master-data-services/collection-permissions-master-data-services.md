---
title: Autorisations de collection (Master Data Services) | Documents Microsoft
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
- collections [Master Data Services], permissions
- permissions [Master Data Services], collections
ms.assetid: 703e1bf5-4b4b-4830-8a5b-f979b09f677d
caps.latest.revision: 6
author: sabotta
ms.author: carlasab
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 6361881ec6af124d7bbfd6cb4b4b225259823a06
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="collection-permissions-master-data-services"></a>Autorisations de collection (services de données de référence)
  Les autorisations de collection s'appliquent à toutes les collections d'une entité. Vous ne pouvez pas donner d'autorisation à une collection spécifique ; les autorisations s'appliquent à toutes les collections.  
  
> [!NOTE]  
>  Ces autorisations s’appliquent à la zone fonctionnelle **Explorateur** de l’interface utilisateur uniquement.  
  
|Autorisation|Description|  
|----------------|-----------------|  
|**Lecture**|L’utilisateur peut lire les membres de collection et les attributs de membre.|  
|**Créer**|L’utilisateur peut créer des membres de collection et affecter des valeurs d’attribut.|  
|**Update**|L’utilisateur peut mettre à jour les membres de collection, les attributs et les relations.|  
|**Supprimer**|L’utilisateur peut supprimer les membres de collection.|  
|**Refuser**|Tous les accès aux membres de collection sont refusés.|  
  
 Vous pouvez combiner les autorisations d’accès en lecture, de création, de mise à jour et de suppression. Lorsque les autorisations Create, Update et Delete sont attribuées, l’autorisation Read est attribuée automatiquement.  
  
## <a name="see-also"></a>Voir aussi  
 [Affecter des autorisations d’objet modèle &#40; Master Data Services &#41;](../master-data-services/assign-model-object-permissions-master-data-services.md)   
 [Collections de &#40; Master Data Services &#41;](../master-data-services/collections-master-data-services.md)   
 [Autorisations d’objet modèle &#40; Master Data Services &#41;](../master-data-services/model-object-permissions-master-data-services.md)  
  
  
