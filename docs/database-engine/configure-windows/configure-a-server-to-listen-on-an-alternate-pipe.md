---
title: "Configurer un serveur pour l&#39;&#233;coute d&#39;un canal de remplacement (Gestionnaire de configuration SQL&#160;Server) | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Canaux nommés [SQL Server], configuration"
  - "écoute [SQL Server], canaux"
  - "canaux [SQL Server], remplacement"
  - "canaux de remplacement [SQL Server]"
ms.assetid: 914f7491-e2be-4b0d-b3aa-fe5409cdbafa
caps.latest.revision: 29
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 29
---
# Configurer un serveur pour l&#39;&#233;coute d&#39;un canal de remplacement (Gestionnaire de configuration SQL&#160;Server)
  Cette rubrique décrit comment configurer un serveur pour l'écoute sur un autre canal dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide du Gestionnaire de configuration SQL Server. Par défaut, l’instance par défaut du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] écoute le canal nommé \\\\.\pipe\sql\query. Les instances nommées de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] et de [!INCLUDE[ssEW](../../includes/ssew-md.md)] écoutent d'autres canaux.  
  
 Il y a trois manières de se connecter à un canal nommé spécifique avec une application cliente :  
  
-   Exécution du service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser sur le serveur.  
  
-   Création d'un alias sur le client, spécification du canal nommé.  
  
-   Programmer le client pour une connexion à l'aide d'une chaîne de connexion personnalisée.  
  
##  <a name="SSMSProcedure"></a> Utilisation du Gestionnaire de configuration SQL Server  
  
#### Pour configurer le canal nommé utilisé par le moteur de base de données SQL Server  
  
1.  Dans le Gestionnaire de configuration SQL Server, dans le volet de la console, développez **Configuration du réseau SQL Server**, puis cliquez pour développer **Protocoles pour ** *\<nom_instance>*.  
  
2.  Dans le volet d’informations, cliquez avec le bouton droit sur **Canaux nommés**, puis cliquez sur **Propriétés**.  
  
3.  Sous l'onglet **Protocole** , dans la zone **Nom du canal** , tapez le canal que le [!INCLUDE[ssDE](../../includes/ssde-md.md)] doit écouter, puis cliquez sur **OK**.  
  
4.  Dans le volet de la console, cliquez sur **Services SQL Server**.  
  
5.  Dans le volet Détails, cliquez avec le bouton droit sur **SQL Server (**\<nom_instance>**)**, puis cliquez sur **Redémarrer** pour arrêter et redémarrer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 Lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] écoute un autre canal, il y a trois manières de se connecter à un canal nommé spécifique avec une application cliente :  
  
-   Exécution du service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser sur le serveur.  
  
-   Création d'un alias sur le client, spécification du canal nommé.  
  
-   Programmer le client pour une connexion à l'aide d'une chaîne de connexion personnalisée.  
  
## Voir aussi  
 [Créer ou modifier un alias de serveur devant être utilisé par un client &#40;Gestionnaire de configuration SQL Server&#41;](../../database-engine/configure-windows/create or delete a server alias for use by a client.md)   
 [Configuration réseau du serveur](../../database-engine/configure-windows/server-network-configuration.md)  
  
  