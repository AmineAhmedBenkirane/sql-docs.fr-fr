---
title: "Assistant Déploiement des Services de l’analyse en cours d’exécution | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Analysis Services Deployment Wizard, running
ms.assetid: 3a38d489-4625-4878-bd18-c6f903be33df
caps.latest.revision: "41"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: On Demand
ms.openlocfilehash: 9a647f65ebbd482fa7f279732685f132d57fcc09
ms.sourcegitcommit: f1a6944f95dd015d3774a25c14a919421b09151b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2017
---
# <a name="running-the-analysis-services-deployment-wizard"></a>Exécution de l'Assistant Déploiement d'Analysis Services
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]Lorsque vous utilisez la [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Assistant déploiement pour déployer un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projet, vous pouvez exécuter l’Assistant comme suit :  
  
-   **Interactive** lorsqu’il est exécuté de manière interactive, le [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Assistant déploiement génère un script de déploiement basé sur les fichiers d’entrée, modifié de manière interactive par l’utilisateur. L'Assistant applique les modifications utilisateur uniquement au script de déploiement. Il ne modifie pas les fichiers d'entrée. Pour plus d’informations sur les fichiers d’entrée, voir [Précisions sur les fichiers d’entrée utilisés pour créer le script de déploiement](../../analysis-services/multidimensional-models/deployment-script-files-input-used-to-create-deployment-script.md).  
  
-   **À partir de l’invite de commandes** lorsqu’il est exécuté à l’invite de commandes, le [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Assistant déploiement génère un script de déploiement basé sur les commutateurs que vous utilisez pour exécuter l’Assistant. L'Assistant peut effectuer les opérations suivantes : vous demander une entrée utilisateur et modifier les fichiers d'entrée en fonction de cette entrée, exécuter un déploiement automatisé en mode silencieux en utilisant les fichiers d'entrée tels quels, ou créer un script de déploiement que vous pouvez utiliser ultérieurement.  
  
## <a name="running-the-analysis-services-deployment-wizard-interactively"></a>Exécution de l'Assistant Déploiement d'Analysis Services de manière interactive  
 Lorsque vous exécutez l'Assistant Déploiement [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de manière interactive, il lit les valeurs des fichiers d'entrée et affiche ces informations. Vous pouvez modifier ces valeurs d'entrée, telle que la destination du déploiement, les paramètres de configuration, les options de déploiement et les mots de passe des chaînes de connexion, ou les laisser telles quelles. Si vous modifiez les valeurs d’entrée, l’Assistant utilise ces modifications lors de la génération du script de déploiement. Toutefois, il ne modifie pas les valeurs du fichier d'entrée.  
  
> [!NOTE]  
>  Pour que l'Assistant Déploiement [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] modifie les valeurs d'entrée, exécutez-le à partir de l'invite de commandes et configurez-le pour fonctionner en mode de fichier de réponses.  
  
 Une fois que vous passez en revue les valeurs d’entrée et effectué les modifications appropriées, l’Assistant génère le script de déploiement. Vous pouvez exécuter ce script de déploiement immédiatement sur le serveur de destination ou l'enregistrer en vue d'une utilisation ultérieure.  
  
#### <a name="to-run-the-analysis-services-deployment-wizard-interactively"></a>Pour exécuter l'Assistant Déploiement d'Analysis Services de manière interactive  
  
-   Dans le menu **Démarrer**, pointez successivement sur **Tous les programmes**, **Microsoft SQL Server**et **Analysis Services**, puis cliquez sur **Assistant Déploiement**.  
  
     —ou—  
  
-   Dans le **projets** dossier de la [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de projet, double-cliquez sur le \<nom du projet > fichier .asdatabase.
    > [!NOTE]  
    >  Si vous ne trouvez pas le fichier .asdatabase, utilisez la fonction de recherche et spécifiez *.asdatabase. Ou bien, vous devrez peut-être générer le projet dans SSDT.  
  
## <a name="running-the-analysis-services-deployment-wizard-at-the-command-prompt"></a>Exécution de l'Assistant Déploiement d'Analysis Services à partir de l'invite de commandes  
 Vous pouvez également exécuter l'Assistant Déploiement [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] à partir de l'invite de commandes. Lorsque vous exécutez l'Assistant à l'invite de commandes, vous fournissez le chemin d'accès complet au fichier .asdatabase et exécutez l'Assistant en l'un des modes suivants :  
  
 **Mode de fichier de réponses**  
 Dans ce mode, l’Assistant permet de modifier de manière interactive les fichiers d’entrée générés à l’origine lors de la création du projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]. L’Assistant enregistre les fichiers d’entrée modifiés avant de générer le script de déploiement. Les fichiers d'entrée deviennent le nouveau point de départ de la prochaine exécution de l'Assistant.  
  
 Pour exécuter l’Assistant en mode fichier de réponses, utilisez le **/a** basculer.  
  
 **Mode silencieux**  
 En mode silencieux, l'Assistant exécute un déploiement automatisé en fonction des informations qui se trouvent dans les fichiers d'entrée.  
  
 Pour exécuter l’Assistant en mode silencieux, utilisez la **/s** basculer. Lorsque vous exécutez l'Assistant en mode silencieux, les messages sont affichés sur la console ou enregistrés dans un fichier journal (s'il en existe un).  
  
 **Mode de sortie**  
 En mode de sortie, l’Assistant génère un script de déploiement pour une exécution ultérieure basé sur les fichiers d’entrée.  
  
 Pour exécuter l’Assistant en mode de sortie, utilisez la **/o** basculer et fournissez un nom de fichier de sortie.  
  
 Pour plus d’informations sur les commutateurs de ligne de commande, voir [Déployer des solutions de modèle avec l’utilitaire de déploiement](../../analysis-services/multidimensional-models/deploy-model-solutions-with-the-deployment-utility.md).  
  
 La procédure suivante explique comment exécuter l'Assistant Déploiement [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] à partir de l'invite de commandes.  
  
#### <a name="to-run-the-analysis-services-deployment-wizard-at-the-command-prompt"></a>Pour exécuter l'Assistant Déploiement d'Analysis Services à partir de l'invite de commandes  
  
1.  Ouvrez une invite de commandes et accédez au dossier C:\Program Files (x86)\Microsoft SQL Server\120\Tools\Binn\ManagementStudio.  
  
2.  Tapez **Microsoft.AnalysisServices.Deployment.exe** , suivi des commutateurs qui correspondent au mode dans lequel vous souhaitez exécuter l'Assistant.  
  
## <a name="see-also"></a>Voir aussi  
 [Description du script de déploiement Analysis Services](../../analysis-services/multidimensional-models/understanding-the-analysis-services-deployment-script.md)   
 [Déployer des solutions de modèle à l’aide de l’Assistant Déploiement](../../analysis-services/multidimensional-models/deploy-model-solutions-using-the-deployment-wizard.md)  
  
  
