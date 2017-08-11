---
title: Installation de fichiers uniquement (Reporting Services) | Documents Microsoft
ms.custom: 
ms.date: 03/30/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- files-only installation [Reporting Services]
- installation options [Reporting Services]
ms.assetid: bdc74a8f-046c-4aa0-bfbd-4f1711dfb9ce
caps.latest.revision: 22
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: f9548290288b30b5a25d57083a7a2c4813a6609c
ms.contentlocale: fr-fr
ms.lasthandoff: 08/09/2017

---
# <a name="files-only-installation-reporting-services"></a>Installation de fichiers uniquement (Reporting Services)
  *L’installation de fichiers uniquement* fait référence à une installation de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dans laquelle le programme d’installation crée l’arborescence pour les fichiers programme [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , copie les fichiers sur disque, inscrit le service Report Server sur l’ordinateur local, configure le compte de service, accorde les autorisations de fichiers au compte de service et inscrit le fournisseur WMI [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .  
  
 Une installation de fichiers uniquement inclut les fonctionnalités [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] suivantes : le service Report Server (qui héberge le service Web Report Server, l'application de traitement en arrière-plan et le Gestionnaire de rapports), le Générateur de rapports, l'outil de configuration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] et les utilitaires de ligne de commande [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] (rsconfig.exe, rskeymgmt.exe et rs.exe). Elle ne s’applique pas aux fonctionnalités partagées telles que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] ou [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], qui doivent être spécifiées comme éléments séparés si vous souhaitez les installer.  
  
 Par opposition avec d'autres modes d'installation, un serveur de rapports installé en mode fichiers uniquement n'est pas opérationnel lorsque l'installation est terminée. Une configuration supplémentaire doit mettre en ligne le serveur de rapports à l’aide du [Gestionnaire de Configuration de Reporting Services &#40; En Mode natif &#41; ](../../reporting-services/install-windows/reporting-services-configuration-manager-native-mode.md).  
  
## <a name="when-to-select-files-only-installation-mode"></a>Quand sélectionner le mode d'installation Fichiers uniquement  
 Une installation de fichiers uniquement doit être effectuée lorsque :  
  
-   vous souhaitez connecter le serveur de rapports à une base de données de serveur de rapports distante ;  
  
-   vous souhaitez installer le serveur de rapports en tant qu'instance nommée ;  
  
-   vous devez respecter des spécifications de déploiement qui incluent l'utilisation de paramètres ou de fonctionnalités personnalisés et vous souhaitez disposer d'un contrôle total sur le moment et la manière dont le serveur est configuré.  
  
-   Installation d'un cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui inclut [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].  
  
## <a name="how-to-perform-a-files-only-installation"></a>Comment effectuer une installation de fichiers uniquement  
 L'installation de fichiers uniquement est le mode d'installation par défaut pour [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].  
  
 Vous pouvez spécifier une installation de fichiers uniquement par le biais de la ligne de commande ou dans l'Assistant Installation. Les rubriques suivantes fournissent des instructions pas à pas :  
  
-   [Installer SQL Server 2016 à partir de l’Assistant Installation &#40; Le programme d’installation &#41; ](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md).  
  
-   [Installer SQL Server 2016 à partir de l’invite de commandes](../../database-engine/install-windows/install-sql-server-2016-from-the-command-prompt.md).  
  
#### <a name="example-command-line-script"></a>Exemple de script de ligne de commande  
 Pour plus de clarté, l'exemple inclut /RSINSTALLMODE="FilesOnlyMode". Toutefois, le mode fichiers uniquement étant le mode par défaut, vous pouvez omettre ceci et obtenir tout de même une installation en mode fichiers uniquement.  
  
```  
setup /q /ACTION=install /FEATURES=RS /InstanceName=MSSQLSERVER /RSSVCACCOUNT="NT AUTHORITY\NETWORK SERVICE" /RSINSTALLMODE="FilesOnlyMode"  
```  
  
#### <a name="installation-wizard"></a>Assistant Installation  
 Lorsque vous sélectionnez [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dans la page Sélection de fonctionnalités, le programme d'installation fournit une page de configuration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] qui vous permet de spécifier le mode d'installation. Pour spécifier une installation de fichiers uniquement, sélectionnez **Installer mais ne pas configurer le serveur** dans la page Configuration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .  
  
## <a name="see-also"></a>Voir aussi  
 [Vérifier une installation de Reporting Services](../../reporting-services/install-windows/verify-a-reporting-services-installation.md)   
 [Configurer le compte de Service Report Server &#40; Gestionnaire de Configuration de SSRS &#41;](../../reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)   
 [Configurer des URL de Report Server &#40; Gestionnaire de Configuration de SSRS &#41;](../../reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager.md)   
 [Configurer une connexion de base de données de serveur de rapports &#40; Gestionnaire de Configuration de SSRS &#41;](../../reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager.md)   
 [Installer le Mode SharePoint de Reporting Services](../../reporting-services/install-windows/install-reporting-services-sharepoint-mode.md)   
 [Installer le serveur de rapports Reporting Services en mode natif](~/reporting-services/install-windows/install-reporting-services-native-mode-report-server.md)   
 [Outils de Reporting Services](../../reporting-services/tools/reporting-services-tools.md)  
  
  


