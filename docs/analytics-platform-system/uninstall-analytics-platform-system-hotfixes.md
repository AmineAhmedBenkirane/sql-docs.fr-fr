---
title: "Désinstallation de correctifs de système de plateforme Analytique (système de plateforme Analytique)"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.prod: sql-non-specified
ms.prod_service: mpp-data-warehouse
ms.service: 
ms.component: analytics-platform-system
ms.technology: mpp-data-warehouse
ms.custom: 
ms.date: 01/05/2017
ms.reviewer: na
ms.suite: sql
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: c9ab596d-3f5a-48e2-bce7-c9be99b8c23b
caps.latest.revision: "21"
ms.openlocfilehash: 04740eeccc1b7837c278ce0041cc1e6f78fd4c60
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="uninstall-analytics-platform-system-hotfixes"></a>Désinstallation de correctifs de système de plateforme Analytique
Les étapes suivantes décrivent comment désinstaller un correctif de système de plateforme Analytique précédemment installé.  
  
## <a name="before-you-begin"></a>Avant de commencer  
  
### <a name="prerequisites"></a>Conditions préalables  
Pour effectuer ces étapes, vous devez :  
  
-   Une connexion de système de plateforme Analytique avec des autorisations pour accéder à la Console d’administration pour contrôler le matériel.  
  
-   Le compte d’administrateur de domaine pour vous connecter à la *< appliance_domain >***-HST01** nœud.  
  
-   Le numéro d’article pour le correctif logiciel à désinstaller.  
  
## <a name="HowToUninstallPDW"></a>Pour désinstaller un correctif logiciel SQL Server PDW  
  
1.  Ouvrez une session sur le *< appliance_domain >***-HST01** nœud en tant que l’administrateur de domaine de l’ensemble fibre optique.  
  
2.  Pour ouvrir une invite de commandes, utilisez l’exécution en tant qu’option de l’administrateur.  
  
3.  Remplacez les répertoires par `C:\PDWINST\Patches\<kbarticle>\media` où  *<kbarticle>*  est le numéro d’article de Base de connaissances pour le correctif logiciel à désinstaller.  
  
    ```  
    cd /d c:\PDWINST\Patches\<kbarticle>\media  
    ```  
  
4.  Pour supprimer le correctif logiciel, exécutez la commande suivante.  
  
    ```  
    setup.exe /action="removepatch" /DomainAdminPassword="<password>"  
    ```  
  
## <a name="see-also"></a>Voir aussi  
[Téléchargez et appliquez les mises à jour Microsoft &#40; Système de plateforme Analytique &#41;](download-and-apply-microsoft-updates.md)  
[Désinstaller les mises à jour Microsoft &#40; Système de plateforme Analytique &#41;](uninstall-microsoft-updates.md)  
[Appliquer des correctifs de système de plateforme Analytique &#40; Système de plateforme Analytique &#41;](apply-analytics-platform-system-hotfixes.md)  
[Logiciel de maintenance &#40; Système de plateforme Analytique &#41;](software-servicing.md)  
  
