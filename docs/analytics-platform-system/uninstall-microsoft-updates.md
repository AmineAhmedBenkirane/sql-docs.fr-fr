---
title: Désinstaller les mises à jour Microsoft (système de plateforme Analytique)
author: barbkess
ms.author: barbkess
manager: craigg
ms.prod: analytics-platform-system
ms.prod_service: mpp-data-warehouse
ms.service: ''
ms.component: ''
ms.technology: mpp-data-warehouse
ms.custom: ''
ms.date: 01/05/2017
ms.reviewer: na
ms.suite: sql
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: df61570a-210d-4154-822f-98acd721f075
caps.latest.revision: 19
ms.openlocfilehash: b428cdacefefa96cdd5c500d34225c6963f5cb1f
ms.sourcegitcommit: 9351e8b7b68f599a95fb8e76930ab886db737e5f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2018
---
# <a name="uninstall-microsoft-updates"></a>Désinstaller les mises à jour Microsoft
Cette rubrique décrit comment désinstaller une mise à jour Microsoft installé sur le matériel de système de plateforme Analytique.  
  
## <a name="before-you-begin"></a>Avant de commencer  
  
### <a name="prerequisites"></a>Configuration requise  
Pour effectuer ces étapes, vous devez :  
  
-   Une connexion de système de plateforme Analytique avec des autorisations pour accéder à la Console d’administration pour contrôler le matériel.  
  
-   Base de connaissances du compte d’administrateur de domaine de l’ensemble fibre optique pour vous connecter à la  *<Fabric Domain>***-HST01** nœud.  
  
## <a name="HowToUninstallMSFT"></a>Pour désinstaller les mises à jour Microsoft  
  
1.  Connexion à la  *<Fabric Domain>***-HST01** nœud en tant que l’administrateur de domaine de l’ensemble fibre optique.  
  
2.  Pour désinstaller les mises à jour sont approuvées pour WSUS désinstaller, ouvrez une fenêtre d’invite de commandes et entrez la commande suivante. Remplacez les éléments de l’espace réservé *< >* avec les informations appropriées.  
  
    ```  
    C:\pdwinst\media\setup.exe /action="RemoveMicrosoftUpdate" /DomainAdminPasswords="<password>"  
    ```  
  
## <a name="see-also"></a>Voir aussi  
[Téléchargez et appliquez les mises à jour Microsoft &#40;Analytique plate-forme système&#41;](download-and-apply-microsoft-updates.md)  
[Appliquer des correctifs de système de plateforme Analytique &#40;Analytique plate-forme système&#41;](apply-analytics-platform-system-hotfixes.md)  
[Désinstallation de correctifs de système de plateforme Analytique &#40;Analytique plate-forme système&#41;](uninstall-analytics-platform-system-hotfixes.md)  
[Maintenance de logiciel &#40;Analytique plate-forme système&#41;](software-servicing.md)  
  
