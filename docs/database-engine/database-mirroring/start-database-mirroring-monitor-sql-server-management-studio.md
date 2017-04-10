---
title: "D&#233;marrer le moniteur de mise en miroir de bases de donn&#233;es (SQL Server Management Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-high-availability"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "surveillance de la mise en miroir de bases de données [SQL Server]"
  - "Moniteur de mise en miroir de bases de données [SQL Server], démarrage"
  - "mise en miroir de bases de données [SQL Server], surveillance"
ms.assetid: 53165335-97ca-4f88-8e78-22f1839dee98
caps.latest.revision: 20
author: "MikeRayMSFT"
ms.author: "mikeray"
manager: "jhubbard"
caps.handback.revision: 20
---
# D&#233;marrer le moniteur de mise en miroir de bases de donn&#233;es (SQL Server Management Studio)
  Le moniteur de mise en miroir de base de données fait partie du Moniteur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], que vous pouvez démarrer à partir de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
> [!NOTE]  
>  Le Moniteur de mise en miroir de bases de données n’est pas disponible dans toutes les éditions de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Pour obtenir la liste des fonctionnalités prises en charge par l’édition de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [Fonctionnalités prise en charge par les éditions de SQL Server 2016](../Topic/Features%20Supported%20by%20the%20Editions%20of%20SQL%20Server%202016.md).  
  
### Pour lancer l'analyse de mise en miroir de base de données  
  
1.  Après vous être connecté à l'instance du serveur principal, dans l'Explorateur d'objets, cliquez sur le nom du serveur pour développer son arborescence.  
  
2.  Développez **Bases de données**, puis sélectionnez la base de données à analyser.  
  
3.  Cliquez avec le bouton droit sur la base de données, sélectionnez **Tâches**, puis cliquez sur **Lancer le moniteur de mise en miroir de bases de données**.  
  
4.  Dans la boîte de dialogue **Moniteur de mise en miroir de bases de données**, cliquez sur **Inscrire la base de données mise en miroir** pour inscrire une ou plusieurs bases de données en miroir.  
  
    > [!NOTE]  
    >  Lorsque vous inscrivez une base de données sur un partenaire, elle est automatiquement inscrite sur l'autre partenaire. Si le moniteur possède déjà des informations d'identification de connexion pour l'instance de l'autre partenaire, elles sont utilisées pour établir la connexion. Autrement, le moniteur tente d'établir une connexion avec l'authentification Windows. Si vous souhaitez modifier les informations d’identification utilisées pour la connexion à l’une des instances de serveur, cliquez sur **Afficher la boîte de dialogue Gérer les connexions serveur lorsque je clique sur OK**.  
  
 Pour plus d’informations sur le moniteur de mise en miroir de bases de données, consultez [Vue d’ensemble du moniteur de mise en miroir de bases de données](../../database-engine/database-mirroring/database-mirroring-monitor-overview.md).  
  
## Voir aussi  
 [Mise en miroir de bases de données &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md)   
 [Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server Management Studio&#41;](../../database-engine/database-mirroring/establish database mirroring session - windows authentication.md)  
  
  