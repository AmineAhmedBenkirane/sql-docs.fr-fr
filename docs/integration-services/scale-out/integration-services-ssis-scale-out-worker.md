---
title: SQL Server Integration Services (SSIS) Scale Out Worker | Microsoft Docs
ms.custom: 
ms.date: 07/18/2017
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: scale-out
ms.reviewer: 
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: haoqian
ms.author: haoqian
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: cb36dc89fbe8fbedc96e426d00f6982213d7d4c9
ms.sourcegitcommit: 7f8aebc72e7d0c8cff3990865c9f1316996a67d5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2017
---
# <a name="integration-services-ssis-scale-out-worker"></a>Integration Services (SSIS) Scale Out Worker

Scale Out Worker exécute un service [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion_md](../../includes/ssisnoversion-md.md)] Scale Out Worker pour extraire des tâches à partir de Scale Out Master et exécute les packages localement avec ISServerExec.exe.

## <a name="configure-sql-server-integration-services-scale-out-worker-service"></a>Configurer le service SQL Server Integration Services Scale Out Worker
Vous pouvez configurer le service Scale Out Worker à l’aide du fichier \<lecteur\>:\Program Files\Microsoft SQL Server\140\DTS\Binn\WorkerSettings.config. Vous devez redémarrer le service après avoir mis à jour le fichier de configuration.

Configuration  |Description  |Valeur par défaut  
---------|---------|---------
DisplayName|Nom complet du Scale Out Worker. **Pas en cours d’utilisation dans [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] 2017.**|Nom de l'ordinateur         
Description|Description du Scale Out Worker. **Pas en cours d’utilisation dans [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] 2017.**|Vide         
MasterEndpoint|Point de terminaison pour la connexion à Scale Out Master.|Point de terminaison défini pendant l’installation du Scale Out Worker.         
MasterHttpsCertThumbprint|Empreinte numérique du certificat client SSL utilisé pour authentifier Scale Out Master.|Empreinte numérique du certificat client spécifié pendant l’installation de Scale Out Worker.          
WorkerHttpsCertThumbprint|Empreinte numérique du certificat Scale Out Master utilisé pour authentifier le Scale Out Worker.|Empreinte numérique d’un certificat créé et installé automatiquement pendant l’installation du Scale Out Worker.          
StoreLocation|Emplacement du magasin de certificats de Worker.|LocalMachine       
StoreName|Nom du magasin où se trouve ce certificat de Worker.|My         
AgentHeartbeatInterval|Intervalle de pulsation du Scale Out Worker.|00:01:00         
TaskHeartbeatInterval|Intervalle d’état de la tâche de rapport du Scale Out Worker.|00:00:10         
HeartbeatErrorTollerance|Après ce laps de temps depuis la dernière pulsation de tâche, la tâche est arrêtée en cas de réception d’une réponse d’erreur de pulsation.|00:10:00      
TaskRequestMaxCPU|Limite supérieure d’utilisation du processeur pour la demande de tâches par le Scale Out Worker. **Pas en cours d’utilisation dans [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] 2017.**|70.0         
TaskRequestMinMemory|Limite inférieure d’utilisation de la mémoire (en Mo) pour la demande de tâches par le Scale Out Worker. **Pas en cours d’utilisation dans [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] 2017.**|100.0         
MaxTaskCount|Quantité maximale de tâches que peut contenir le Scale Out Worker.|10         
LeaseInternval|Intervalle de bail de détention d’une tâche par le Scale Out Worker.|00:01:00         
TasksRootFolder|Dossier des journaux des tâches. Le chemin de dossier \<lecteur\>: \Users\\*[compte]*\AppData\Local\SSIS\Cluster\Tasks est utilisé si la valeur est vide. [compte] est le compte exécutant le service Scale Out Worker. Par défaut, le compte est SSISScaleOutWorker140.|Vide         
TaskLogLevel|Niveau de journal des tâches du Scale Out Worker. (Verbose 0x01, Information 0x02, Warning 0x04, Error 0x08, Progress 0x10, CriticalError 0x20, Audit 0x40)|126 (Information,Warning,Error,Progress,CriticalError,Audit)     
TaskLogSegment|Intervalle de temps d’un fichier journal de tâche.|00:00:00         
TaskLogEnabled|Spécifie si le journal des tâches est activé.|true         
ExecutionLogCacheFolder|Dossier utilisé pour mettre en cache le journal d’exécution de package. Le chemin de dossier \<lecteur\>: \Users\\*[compte]*\AppData\Local\SSIS\Cluster\Agent\ELogCache est utilisé si la valeur est vide. [compte] est le compte exécutant le service Scale Out Worker. Par défaut, le compte est SSISScaleOutWorker140.|Vide         
ExecutionLogMaxBufferLogCount|Quantité maximale de journaux d’exécution mis en cache, dans une mémoire tampon de journal d’exécution en mémoire.|10000        
ExecutionLogMaxInMemoryBufferCount|Quantité maximale de mémoires tampon de journal d’exécution en mémoire pour les journaux d’exécution.|10         
ExecutionLogRetryCount|Nombre de nouvelles tentatives en cas d’échec de journalisation de l’exécution.|3
ExecutionLogRetryTimeout|Délai d’expiration des nouvelles tentatives en cas d’échec de journalisation de l’exécution. ExecutionLogRetryCount est ignoré si ExecutionLogRetryTimeout est atteint.|7.00:00:00 (7 jours)        
AgentId|ID d’agent de Worker du Scale Out Worker.|Généré automatiquement.        

## <a name="view-scale-out-worker-log"></a>Afficher le journal Scale Out Worker
Le fichier journal du service Scale Out Worker se trouve dans le dossier \<lecteur\>:\Users\\*[compte]*\AppData\Local\SSIS\ScaleOut\Agent.

L’emplacement du journal de chaque tâche est configuré dans le fichier WorkerSettings.config par TasksRootFolder. S’il n’est pas spécifié, le journal se trouve dans le dossier \<lecteur\>:\Users\\*[compte]*\AppData\Local\SSIS\ScaleOut\Tasks. 

*[compte]* est le compte exécutant le service Scale Out Worker. Par défaut, le compte est SSISScaleOutWorker140.
