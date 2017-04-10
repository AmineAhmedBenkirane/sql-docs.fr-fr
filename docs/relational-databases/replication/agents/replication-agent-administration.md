---
title: "Administration de l&#39;Agent de r&#233;plication | Microsoft Docs"
ms.custom: ""
ms.date: "08/24/2016"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "replication"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Agent d’instantané, administration"
  - "Agent de lecture du journal, administration"
  - "Agent de lecture de la file d’attente, administration"
  - "agents partagés [réplication SQL Server]"
  - "Agent de fusion, administration"
  - "Agent de distribution, administration"
  - "agents [réplication SQL Server], administration"
  - "travaux de nettoyage de réplication [réplication SQL Server]"
  - "administration de la réplication, agents"
  - "réplication [SQL Server], administration"
  - "agents indépendants [réplication SQL Server]"
ms.assetid: f27186b8-b1b2-4da0-8b2b-91f632c2ab7e
caps.latest.revision: 48
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 48
---
# Administration de l&#39;Agent de r&#233;plication
  Les agents de réplication accomplissent de nombreuses tâches associées à la réplication, notamment la création de copies du schéma et des données, la détection des mises à jour sur le serveur de publication ou sur l'Abonné, et la propagation des modifications entre les serveurs. Par défaut, les agents de réplication s’exécutent sous [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] les étapes de travail de l’Agent. Les agents sont simplement des exécutables et peuvent donc être appelés directement à partir de la ligne de commande et de scripts de commande par lot. Chaque agent de réplication prend en charge un ensemble de paramètres d'exécution utilisés pour contrôler comment il s'exécute ; ces paramètres sont spécifiés dans un profil d'agent ou sur la ligne de commande.  
  
> [!IMPORTANT]  
>  Par défaut, le service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent est désactivé lors de l'installation de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , sauf si vous choisissez explicitement de démarrer automatiquement le service au cours de l'installation.  
  
 Les fichiers de l'Agent de réplication se trouvent sous [!INCLUDE[ssInstallPathVar](../../../includes/ssinstallpathvar-md.md)]\COM. Le tableau suivant contient la liste des noms des exécutables de la réplication et les noms des fichiers correspondants. Cliquez sur le lien correspondant à un agent pour afficher les informations de référence de ses paramètres.  
  
|Exécutable de l'agent|Nom de fichier|  
|----------------------|---------------|  
|[Agent d'instantané de réplication](../../../relational-databases/replication/agents/replication-snapshot-agent.md)|snapshot.exe|  
|[Agent de distribution de réplication](../../../relational-databases/replication/agents/replication-distribution-agent.md)|distrib.exe|  
|[Agent de lecture du journal des réplications](../../../relational-databases/replication/agents/replication-log-reader-agent.md)|logread.exe|  
|[Agent de lecture de la file d'attente de réplication](../../../relational-databases/replication/agents/replication-queue-reader-agent.md)|qrdrsvc.exe|  
|[Agent de fusion de réplication](../../../relational-databases/replication/agents/replication-merge-agent.md)|replmerg.exe|  
  
 En plus des agents de réplication, la réplication a plusieurs travaux qui effectuent de la maintenance planifiée et à la demande.  
  
 **Pour exécuter les travaux des agents et de maintenance**  
  
-   [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] et moniteur de réplication : [Démarrer et arrêter un Agent de réplication & #40 ; SQL Server Management Studio & #41 ;](../../../relational-databases/replication/agents/start-and-stop-a-replication-agent-sql-server-management-studio.md)  
  
-   Programmation de la réplication : [Concepts des exécutables l’Agent de réplication](../../../relational-databases/replication/concepts/replication-agent-executables-concepts.md)  
  
## Profils de l'Agent  
 Quand la réplication est configurée, un ensemble de profils d'agent est installé sur le serveur de distribution. Un profil d'agent contient un ensemble de paramètres qui sont utilisés chaque fois qu'un agent s'exécute : pendant le processus de démarrage, chaque agent se connecte au service de distribution et interroge les paramètres situés dans son profil. La réplication fournit un profil par défaut pour chaque agent et des profils supplémentaires prédéfinis pour l'Agent de lecture du journal, l'Agent de distribution et l'Agent de fusion. En plus des profils fournis, vous pouvez créer des profils adaptés aux besoins de vos applications. Pour plus d’informations, voir [Replication Agent Profiles](../../../relational-databases/replication/agents/replication-agent-profiles.md).  
  
 Pour plus d’informations sur la spécification des paramètres de ligne de commande directe, consultez [Concepts des exécutables de l’Agent réplication](../../../relational-databases/replication/concepts/replication-agent-executables-concepts.md).  
  
## Surveillance des Agents de réplication  
 Le moniteur de réplication vous permet d'afficher des informations et d'effectuer des tâches associées à chaque agent de réplication. La liste suivante comprend chacun des agents, les onglets du moniteur de réplication sur lesquels ils peuvent être trouvés et un lien vers une rubrique qui explique comment accéder à ces onglets :  
  
-   Les agents suivants sont associés à des publications dans le moniteur de réplication :  
  
    -   Agent d'instantané  
  
    -   l'Agent de lecture du journal ;  
  
    -   Agent de lecture de la file d'attente  
  
     Accéder aux informations et les tâches associées à ces agents via les **Agents** onglet. Pour plus d’informations, consultez [afficher des informations et effectuer des tâches pour les Agents associés à une Publication & #40 ; Moniteur de réplication & #41 ;](../../../relational-databases/replication/monitor/view information and perform tasks for publication agents.md).  
  
-   Les agents suivants sont associés à des abonnements dans le moniteur de réplication :  
  
    -   Agent de distribution  
  
    -   Agent de fusion  
  
     Accéder aux informations et les tâches associées à ces agents via les onglets suivants : **liste de suivi** (disponible pour chaque serveur de publication) ou le **tous les abonnements** (disponible pour chaque publication). Pour plus d’informations, consultez [afficher des informations et effectuer des tâches pour les Agents associés à un abonnement & #40 ; Moniteur de réplication & #41 ;](../../../relational-databases/replication/monitor/view information and perform tasks for subscription agents.md).  
  
## Agents indépendants et partagés  
 Un Agent indépendant est un Agent qui sert un seul abonnement. Un agent partagé fournit des services à plusieurs abonnements ; si plusieurs abonnements utilisant le même agent partagé doivent se synchroniser, ils attendent par défaut dans une file d'attente, et l'agent partagé leur fournit ce service l'un après l'autre. Le temps de latence est réduit lors de l'utilisation d'agents indépendants car ceux-ci sont disponibles dès que l'abonnement doit être synchronisé. La réplication de fusion utilise toujours des agents indépendants, et la réplication transactionnelle utilise par défaut des agents indépendants pour les publications créées dans l'Assistant Nouvelle publication (dans les versions précédentes de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], la réplication transactionnelle utilisait par défaut des agents partagés).  
  
## Travaux de maintenance de la réplication  
 La réplication utilise les travaux suivants pour effectuer de la maintenance planifiée et à la demande.  
  
|Travail de nettoyage|Description|Planification par défaut|  
|------------------|-----------------|----------------------|  
|Nettoyage de l'historique de l'agent : distribution|Supprime les enregistrements historiques des agents de réplication dans la base de données de distribution.|S'exécute toutes les dix minutes|  
|Nettoyage de la distribution : distribution|Suppression des transactions répliquées de la base de données de distribution. Désactive les abonnements qui n’ont été pas été synchronisés au cours de la période maximale de rétention de distribution.|S'exécute toutes les dix minutes|  
|Nettoyage de l'abonnement expiré|Détecte les abonnements expirés et les retire des bases de données de publication.|S'exécute chaque jour à 1 heure du matin.|  
|Réinitialiser les abonnements présentant des erreurs lors de la validation de données|Détecte tous les abonnements qui ont des échecs de validation des données et les marque pour réinitialisation. Lors de l'exécution suivante de l'Agent de fusion ou de l'Agent de distribution, un nouvel instantané sera appliqué aux Abonnés.|Pas de planification par défaut (non activé par défaut).|  
|Contrôle des Agents de réplication|Détecte les Agents de réplication n'ayant pas d'enregistrement historique actif. Il écrit dans le [!INCLUDE[msCoName](../../../includes/msconame-md.md)] journal des événements Windows si une étape de travail échoue.|S'exécute toutes les dix minutes.|  
|Actualisateur d'analyse de réplication pour la distribution|Actualise les requêtes mises en cache utilisées par le moniteur de réplication.|S'exécute en permanence.|  
  
## Voir aussi  
 [Surveillance de la réplication](../../../relational-databases/replication/monitor/monitoring-replication-overview.md)  
  
  