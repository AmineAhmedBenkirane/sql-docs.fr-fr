---
title: "Autoriser l&#39;acc&#232;s sur le r&#233;seau &#224; un point de terminaison de mise en miroir de bases de donn&#233;es au moyen de l&#39;authentification&#160;Windows (SQL Server) | Microsoft Docs"
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
  - "authentification Windows [SQL Server]"
  - "mise en miroir de bases de données (SQL Server), sécurité"
ms.assetid: 28c8fec5-5feb-4c84-8d72-f2bd1ae3b40d
caps.latest.revision: 34
ms.author: "mikeray"
manager: "jhubbard"
---
# Autoriser l&#39;acc&#232;s sur le r&#233;seau &#224; un point de terminaison de mise en miroir de bases de donn&#233;es au moyen de l&#39;authentification&#160;Windows (SQL Server)
  L'utilisation de l'authentification Windows pour connecter les points de terminaison de mise en miroir de bases de données de deux instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requiert une configuration manuelle des comptes de connexion dans les conditions suivantes :  
  
-   Si les instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fonctionnent comme des services sous des comptes de domaine différents (dans les mêmes domaines ou dans des domaines approuvés), la connexion de chaque compte doit être créée en **maître** sur chacune des instances de serveur distant, et cette connexion doit disposer d’autorisations CONNECT sur le point de terminaison.  
  
-   Si les instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fonctionnent comme le compte de service réseau, la connexion de chaque compte d’ordinateur hôte (*DomainName***\\***ComputerName$*) doit être créée en **maître** sur chacune des instances de serveur distant, et cette connexion doit disposer d’autorisations CONNECT sur le point de terminaison. En effet, une instance de serveur s'exécutant sous le compte de service réseau s'authentifie à l'aide du compte de domaine de l'ordinateur hôte.  
  
> [!NOTE]  
>  Vérifiez qu'il existe un point de terminaison pour chaque instance du serveur. Pour plus d’informations, consultez [Créer un point de terminaison de mise en miroir de bases de données pour l’authentification Windows &#40;Transact-SQL&#41;](../../database-engine/database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).  
  
### Pour configurer des connexions pour l'authentification Windows  
  
1.  Pour le compte d'utilisateur de chaque instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], créez une connexion sur les autres instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Utilisez une instruction [CREATE LOGIN](../../t-sql/statements/create-login-transact-sql.md) avec la clause FROM WINDOWS.  
  
     Pour plus d’informations, consultez [Créer un compte de connexion](../../relational-databases/security/authentication-access/create-a-login.md).  
  
2.  En outre, pour vérifier que l'utilisateur de connexion a accès au point de terminaison, utilisez l'instruction [GRANT](../../t-sql/statements/grant-transact-sql.md) pour accorder des autorisations de connexion sur le point de terminaison à la connexion. Notez que l'attribution d'autorisations de connexion n'est pas nécessaire si l'utilisateur est un administrateur.  
  
     Pour en savoir plus, voir [Grant a Permission to a Principal](../../relational-databases/security/authentication-access/grant-a-permission-to-a-principal.md).  
  
## Exemple  
 L'exemple [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant crée une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour un compte d'utilisateur nommé `Otheruser` qui appartient à un domaine du nom de `Adomain`. Des autorisations de connexion sont ensuite octroyées à cet utilisateur pour le point de terminaison de la mise en miroir de bases de données préexistantes appelé `Mirroring_Endpoint`.  
  
```  
USE master;  
GO  
CREATE LOGIN [Adomain\Otheruser] FROM WINDOWS;  
GO  
GRANT CONNECT on ENDPOINT::Mirroring_Endpoint TO [Adomain\Otheruser];  
GO  
```  
  
## Voir aussi  
 [Vue d’ensemble des groupes de disponibilité Always On &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)   
 [Mise en miroir de bases de données &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md)   
 [Sécurité du transport de la mise en miroir de bases de données et des groupes de disponibilité Always On &#40;SQL Server&#41;](../../database-engine/database-mirroring/transport security - database mirroring - always on availability.md)   
 [Point de terminaison de mise en miroir de bases de données &#40;SQL Server&#41;](../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md)  
  
  