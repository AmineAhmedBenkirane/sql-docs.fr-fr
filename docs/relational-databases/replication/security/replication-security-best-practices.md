---
title: "M&#233;thodes pr&#233;conis&#233;es en mati&#232;re de s&#233;curit&#233; de r&#233;plication | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "replication"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "sécurité [réplication SQL Server], meilleures pratiques"
  - "sécurité [réplication SQL Server], entre les domaines"
  - "authentification [réplication SQL Server]"
  - "Internet [réplication SQL Server], sécurité"
ms.assetid: 1ab2635d-0992-4c99-b17d-041d02ec9a7c
caps.latest.revision: 42
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 42
---
# M&#233;thodes pr&#233;conis&#233;es en mati&#232;re de s&#233;curit&#233; de r&#233;plication
  La réplication permet de déplacer des données d'environnements distribués qui englobent tant des intranets sur un domaine unique que des applications accédant à des données entre des domaines non approuvés et sur Internet. Il est important de bien connaître toutes les méthodes de sécurisation des connexions de réplication afin de choisir celle qui répond le mieux à la situation.  
  
 Les informations suivantes concernent la réplication dans tous les environnements :  
  
-   Chiffrez les connexions entre des ordinateurs d'une topologie de réplication à l'aide d'une méthode standard dans l'industrie, telle que les réseaux privés virtuels (VPN, Virtual Private Networks), SSL (Secure Sockets Layer) et IPSEC (IP Security). Pour plus d’informations, consultez [activer des connexions chiffrées dans le moteur de base de données & #40 ; SQL Server Configuration Manager & #41 ;](../../../database-engine/configure-windows/enable encrypted connections to the database engine.md). Pour plus d’informations sur l’utilisation de VPN et SSL pour répliquer des données sur Internet, consultez [sécurisation de la réplication sur Internet](../../../relational-databases/replication/security/securing-replication-over-the-internet.md).  
  
     Si vous utilisez SSL pour sécuriser les connexions entre les ordinateurs dans une topologie de réplication, spécifiez la valeur **1** ou **2** pour la **- EncryptionLevel** paramètre de chaque agent de réplication (valeur **2** est recommandé). Valeur **1** indique que le chiffrement est utilisé, mais l’agent ne vérifie pas que le certificat de serveur SSL est signé par un émetteur approuvé ; une valeur de **2** Spécifie que le certificat est vérifié. Les paramètres des agents peuvent être spécifiés dans des profils d'agent et sur la ligne de commande. Pour plus d'informations, consultez :  
  
    -   [Work with Replication Agent Profiles](../../../relational-databases/replication/agents/work-with-replication-agent-profiles.md)  
  
    -   [Afficher et modifier les paramètres d’invite de l’Agent de réplication & #40 ; SQL Server Management Studio & #41 ;](../../../relational-databases/replication/agents/view and modify replication agent command prompt parameters.md)  
  
    -   [Concepts des exécutables de l'agent de réplication](../../../relational-databases/replication/concepts/replication-agent-executables-concepts.md)  
  
-   Exécutez chaque agent de réplication sous un compte Windows différent et utilisez l'authentification Windows pour toutes les connexions des agents de réplication. Pour plus d’informations sur la spécification des comptes, consultez [Gérer les connexions et les mots de passe lors de la réplication](../../../relational-databases/replication/security/manage-logins-and-passwords-in-replication.md).  
  
-   Accordez à chaque agent les autorisations dont ils ont besoin et pas davantage. Pour plus d’informations, consultez la section « Autorisations requises par les Agents » de [modèle de sécurité de l’Agent de réplication](../../../relational-databases/replication/security/replication-agent-security-model.md).  
  
-   Vérifiez que tous les comptes de l'Agent de fusion et de l'Agent de distribution figurent dans la liste d'accès à la publication. Pour plus d’informations, consultez [sécuriser le serveur de publication](../../../relational-databases/replication/security/secure-the-publisher.md).  
  
-   Suivez le principe du moindre privilège en n'accordant aux comptes de la liste d'accès à la publication que les autorisations nécessaires pour effectuer des tâches de réplication. N'ajoutez pas de connexions inutiles pour la réplication aux rôles de serveur fixe.  
  
-   Configurez le partage d'instantanés de telle sorte que tous les Agent de fusion et tous les Agents de distribution puissent disposer d'un accès en lecture. Dans le cas d'instantanés pour des publications avec des filtres paramétrés, vérifiez que chaque dossier est configuré pour n'autoriser l'accès qu'aux comptes appropriés de l'Agent de fusion.  
  
-   Configurez le partage d'instantanés de telle sorte que l'Agent d'instantané puisse disposer d'un accès en écriture.  
  
-   Si vous utilisez des abonnements par extraction de données (pull), préférez l'utilisation d'un partage réseau à un chemin d'accès local du dossier d'instantanés.  
  
 Si votre topologie de réplication comprend des ordinateurs qui se trouvent dans des domaines différents ou dans des domaines sans relations de confiance, vous pouvez utiliser l'authentification Windows ou l'authentification [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour les connexions établies par des agents (pour plus d'informations sur les domaines, consultez la cocumentation Windows). L'authentification Windows est une méthode de sécurité préconisée.  
  
-   Pour utiliser l'authentification Windows  
  
    -   Ajoutez un compte Windows local (et non un compte de domaine) pour chaque agent sur les nœuds appropriés (utilisez le même nom et le même mot de passe sur chaque nœud). Par exemple, l'Agent de distribution d'un abonnement par envoi de données (push) s'exécute sur le serveur de distribution et établit des connexions avec le serveur de distribution et l'Abonné. Le compte Windows de l'Agent de distribution doit être ajouté au serveur de distribution et à l'Abonné.  
  
    -   Vérifiez qu'un agent donné (par exemple, l'Agent de distribution pour un abonnement) s'exécute sous le même compte sur chaque ordinateur.  
  
-   Pour utiliser l'authentification [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :  
  
    -   Ajoutez un compe [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour chaque agent sur les nœuds appropriés (utilisez le même nom de compte et le même mot de passe sur chaque nœud). Par exemple, l'Agent de distribution d'un abonnement par envoi de données (push) s'exécute sur le serveur de distribution et établit des connexions avec le serveur de distribution et l'Abonné. Le compte [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de l'Agent de distribution doit être ajouté au serveur de distribution et à l'Abonné.  
  
    -   Vérifiez qu'un agent donné (par exemple, l'Agent de distribution d'un abonnement) établit des connexions sous le même compte sur chaque ordinateur.  
  
    -   Dans les situations exigeant l'authentification [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], l'accès aux partages d'instantanés UNC n'est souvent pas disponible (par exemple, l'accès peut être bloqué par un pare-feu). Dans ce cas, vous pouvez transférer l'instantané aux abonnés via FTP (File Transfer Protocol). Pour plus d’informations, consultez [instantanés via FTP Transfer](../../../relational-databases/replication/transfer-snapshots-through-ftp.md).  
  
## Voir aussi  
 [Activer les connexions chiffrées dans le moteur de base de données & #40 ; Gestionnaire de Configuration SQL Server & #41 ;](../../../database-engine/configure-windows/enable encrypted connections to the database engine.md)   
 [Réplication sur Internet](../../../relational-databases/replication/replication-over-the-internet.md)   
 [Sécuriser l'abonné](../../../relational-databases/replication/security/secure-the-subscriber.md)   
 [Protéger le serveur de distribution](../../../relational-databases/replication/security/secure-the-distributor.md)   
 [Sécuriser le serveur de publication](../../../relational-databases/replication/security/secure-the-publisher.md)   
 [Sécurité et Protection & #40 ; Réplication & #41 ;](../../../relational-databases/replication/security/security-and-protection-replication.md)  
  
  