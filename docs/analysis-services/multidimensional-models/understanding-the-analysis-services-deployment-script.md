---
title: Présentation de l’analyse du Script de déploiement des Services | Documents Microsoft
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.component: multidimensional-models
ms.topic: article
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 35ebb4489ed72f370ffc4a2f2657f6caa5460714
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="understanding-the-analysis-services-deployment-script"></a>Description du script de déploiement Analysis Services
[!INCLUDE[ssas-appliesto-sqlas-all-aas](../../includes/ssas-appliesto-sqlas-all-aas.md)]

  Le script de déploiement XMLA généré par l’Assistant Déploiement de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] comporte deux sections :  
  
-   La première partie du script de déploiement contient les commandes nécessaires à la création, la modification ou la suppression des objets [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] appropriés dans la base de données de destination. Par défaut, les fichiers d'entrée générés par le projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] sont basés sur un déploiement incrémentiel. Par conséquent, le script de déploiement XMLA n'affecte que les objets qui ont été modifiés ou supprimés.  
  
-   La seconde partie du script de déploiement contient les commandes requises pour traiter uniquement les objets créés ou modifiés sur le serveur de destination (option Traiter par défaut) ou pour traiter intégralement la base de données de destination. Vous pouvez également décider que le script de déploiement ne contiendra aucune commande de traitement.  
  
 L'ensemble du script de déploiement peut être exécuté dans une seule transaction ou dans plusieurs transactions. Si le script est exécuté dans plusieurs transactions, la première partie du script est exécutée sous la forme d'une seule transaction, et chaque objet est traité dans sa propre transaction.  
  
> [!IMPORTANT]  
>  L’Assistant Déploiement [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] déploie les objets uniquement dans une seule base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] . Il ne déploie pas des objets, ni des données au niveau du serveur.  
  
## <a name="see-also"></a>Voir aussi  
 [L’Assistant Déploiement de Analysis Services en cours d’exécution](../../analysis-services/multidimensional-models/running-the-analysis-services-deployment-wizard.md)   
 [Précisions sur les fichiers d’entrée utilisés pour créer le Script de déploiement](../../analysis-services/multidimensional-models/deployment-script-files-input-used-to-create-deployment-script.md)  
  
  
