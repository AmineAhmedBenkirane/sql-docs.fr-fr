---
title: "Installer la r&#233;plication SQL Server | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "setup-install"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "composants [réplication SQL Server]"
  - "installations via la ligne de commande [réplication SQL Server]"
  - "installation de la réplication"
  - "réplication [SQL Server], installation"
  - "invite de commandes [réplication SQL Server]"
ms.assetid: c50ad078-060b-4a8d-ad45-9e31a8d85729
caps.latest.revision: 41
author: "MikeRayMSFT"
ms.author: "mikeray"
manager: "jhubbard"
caps.handback.revision: 41
---
# Installer la r&#233;plication SQL Server
  Les composants de réplication peuvent être installés à l'aide de l'Assistant Installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou à l'invite de commandes. Installez la réplication lors de l'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou lors de la modification d'une instance existante.  
  
 Une fois que les composants de réplication sont installés, vous devez configurer le serveur avant de pouvoir utiliser la réplication. Pour plus d’informations, consultez [Configurer la distribution](../../relational-databases/replication/configure-distribution.md) dans la documentation en ligne [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
> [!IMPORTANT]  
>  Si vous installez des composants de réplication lorsque vous modifiez une instance existante de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous devez arrêter et redémarrer l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] une fois l'installation terminée. Cette action garantit que l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] reconnaît les sous-systèmes de l'agent de réplication et peut appeler les agents de réplication à partir des étapes de travail.  
  
## Installation de la réplication à l'aide du programme d'installation  
 **Pour installer la réplication en même temps qu’une nouvelle instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**  
  
-   Pour installer les composants de réplication, notamment des objets RMO (Replication Management Objects), sélectionnez **Réplication SQL Server** dans la page **Sélection de composant** de l’Assistant Installation.  
  
## Installation de la réplication à partir de l'invite de commandes  
 **Pour installer la réplication en même temps qu’une nouvelle instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**  
  
-   Consultez [Installer SQL Server 2016 à partir de l’invite de commandes](../../database-engine/install-windows/install-sql-server-2016-from-the-command-prompt.md).  
  
## Voir aussi  
 [Installer SQL Server 2016](../../database-engine/install-windows/install-sql-server-2016.md)   
 [Installer SQL Server 2016 à partir de l’invite de commandes](../../database-engine/install-windows/install-sql-server-2016-from-the-command-prompt.md)   
 [Fonctionnalités prises en charge par les éditions de SQL Server 2016](../Topic/Features%20Supported%20by%20the%20Editions%20of%20SQL%20Server%202016.md)  
  
  