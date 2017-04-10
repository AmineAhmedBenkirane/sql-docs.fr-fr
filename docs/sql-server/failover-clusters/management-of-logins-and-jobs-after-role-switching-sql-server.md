---
title: "Gestion des connexions et des travaux apr&#232;s un basculement de r&#244;le (SQL Server) | Microsoft Docs"
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
  - "basculement de rôle [SQL Server]"
ms.assetid: fc2fc949-746f-40c7-b5d4-3fd51ccfbd7b
caps.latest.revision: 25
author: "MikeRayMSFT"
ms.author: "mikeray"
manager: "jhubbard"
caps.handback.revision: 25
---
# Gestion des connexions et des travaux apr&#232;s un basculement de r&#244;le (SQL Server)
  Lors du déploiement d’une solution de récupération d’urgence ou haute disponibilité pour une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], il est important de reproduire les informations importantes stockées pour la base de données dans les bases de données **master** ou **msdb**. En général, les informations importantes incluent les travaux de la base de données primaire/principale et les connexions des utilisateurs ou des processus qui doivent se connecter à la base de données. Vous devez dupliquer ces informations dans une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui héberge une base de données secondaire/miroir. Si possible, il est préférable de reproduire, par programmation, l'information au niveau de la nouvelle base de données primaire/principale, après le basculement des rôles.  
  
## Connexions  
 Sur chaque instance de serveur qui héberge une copie de la base de données, vous devez reproduire les connexions qui sont autorisées à accéder à la base de données principale. Lorsque le rôle primaire/principal bascule, seuls les utilisateurs dont les connexions existent sur la nouvelle instance de serveur primaire/principal peuvent accéder à la nouvelle base de données primaire/principale. Les utilisateurs dont les connexions ne sont pas définies sur la nouvelle instance de serveur primaire/principal sont orphelins et ne peuvent pas accéder à la base de données.  
  
 Si un utilisateur est orphelin, créez la connexion sur la nouvelle instance de serveur primaire/principal et exécutez [sp_change_users_login](../../relational-databases/system-stored-procedures/sp-change-users-login-transact-sql.md). Pour plus d’informations, consultez [Dépanner des utilisateurs orphelins &#40;SQL Server&#41;](../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md).  
  
###  <a name="SSauthentication"></a> Connexions des applications qui utilisent l'authentification SQL Server ou une connexion locale Windows  
 Si une application utilise l'authentification SQL Server ou une connexion locale Windows, des SID incompatibles peuvent empêcher la résolution de la connexion de l'application sur une instance distante de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. En cas de SID incompatibles, la connexion peut se solder par un utilisateur orphelin sur l'instance de serveur distante. Ce problème peut se produire lorsqu'une application se connecte à une base de données de copie des journaux de transaction ou une base de données mise en miroir suite à un basculement ou à une base de données d'abonné de réplication qui a été initialisée à partir d'une sauvegarde.  
  
 Pour éviter ce problème, nous vous recommandons de prendre des mesures préventives lorsque vous configurez une telle application de manière à utiliser une base de données hébergée par une instance distante de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. La prévention implique de transférer des connexions et des mots de passe de l'instance locale de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'instance distante de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Pour plus d’informations sur la manière d’éviter ce problème, consultez l’article 918992 de la Base de connaissances : [Comment faire pour transférer des noms d’accès et des mots de passe entre instances de SQL Server](http://support.microsoft.com/kb/918992/).  
  
> [!NOTE]  
>  Ce problème affecte les comptes Windows locaux sur différents ordinateurs. Toutefois, ce problème ne se pose pas pour les comptes de domaine car le SID est identique sur chacun des ordinateurs.  
  
 Pour plus d’informations, consultez [Orphaned Users with Database Mirroring and Log Shipping (Utilisateurs orphelins avec mise en miroir de bases de données et copie des journaux de transaction)](http://blogs.msdn.com/b/sqlserverfaq/archive/2009/04/13/orphaned-users-with-database-mirroring-and-log-shipping.aspx) (blog du moteur de base de données).  
  
## Travaux  
 Les travaux tels que les travaux de sauvegarde, requièrent une attention particulière. Généralement, après un basculement de rôle, le propriétaire de la base de données ou l'administrateur système doit recréer les travaux de la nouvelle base de données primaire/principale.  
  
 Lorsque l'ancienne instance de serveur primaire/principal est disponible, vous devez supprimer les travaux originaux sur cette instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Notez que ces travaux de la base de données miroir actuelle échouent dans la mesure où celle-ci se trouve en état de restauration (RESTORING) et qu'elle n'est ainsi pas disponible.  
  
> [!NOTE]  
>  Différentes instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peuvent être configurées différemment, avec des lettres de lecteurs de lecteur différentes, ou quelque chose d'équivalent. Les travaux de chaque partenaire doivent autoriser de telles différences.  
  
## Voir aussi  
 [Gérer les métadonnées lors de la mise à disposition d’une base de données sur une autre instance de serveur &#40;SQL Server&#41;](../../relational-databases/databases/manage metadata when making a database available on another server.md)   
 [Dépanner des utilisateurs orphelins &#40;SQL Server&#41;](../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md)  
  
  