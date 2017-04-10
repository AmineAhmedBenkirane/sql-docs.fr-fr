---
title: "D&#233;marrer l&#39;utilitaire sqlcmd | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 00d57437-7a29-4da1-b639-ee990db055fb
caps.latest.revision: 41
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
---
# D&#233;marrer l&#39;utilitaire sqlcmd
    
> [!NOTE]  
>  L’authentification Windows est le mode d’authentification par défaut pour **sqlcmd**. Pour utiliser l’authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous devez spécifier un nom d’utilisateur et un mot de passe en utilisant les options **-U** et **-P**.  
  
> [!NOTE]  
>  Par défaut, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] s’installe en tant qu’instance nommée **sqlexpress**.  
  
### Démarrer l’utilitaire sqlcmd et établir une connexion à une instance par défaut de SQL Server  
  
1.  Dans le menu **Démarrer** , cliquez sur **Exécuter**. Dans la zone **Ouvrir** , tapez **cmd**, puis cliquez sur **OK** pour ouvrir une fenêtre d'invite de commandes. (Si vous ne vous êtes encore jamais connecté à cette instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], vous devrez peut-être configurer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour qu’il accepte les connexions.)  
  
2.  À l’invite de commandes, saisissez **sqlcmd**.  
  
3.  Appuyez sur Entrée.  
  
     Vous bénéficiez maintenant d'une connexion approuvée à l'instance par défaut de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui est exécutée sur votre ordinateur.  
  
     **1>** correspond à l’invite **sqlcmd** indiquant le numéro de ligne. Chaque fois que vous appuyez sur ENTRÉE, le numéro augmente de un.  
  
4.  Pour terminer la session **sqlcmd** , saisissez **EXIT** sur l’invite **sqlcmd** .  
  
### Démarrer l’utilitaire sqlcmd et établir une connexion à une instance nommée de SQL Server  
  
1.  Ouvrez une fenêtre d’invite de commandes, puis tapez **sqlcmd -S***mon_serveur\nom_instance*. Remplacez *mon_serveur\nom_instance[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par le nom de l’ordinateur et de l’instance de * à laquelle vous souhaitez vous connecter.  
  
2.  Appuyez sur Entrée.  
  
     L’invite **sqlcmd** (1>) indique que vous êtes connecté à l’instance spécifiée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
    > [!NOTE]  
    >  Les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] entrées sont stockées dans une mémoire tampon. Elles sont exécutées en tant que lot lorsque la commande GO est rencontrée.  
  
## Voir aussi  
 [Exécuter des fichiers de script Transact-SQL à l'aide de sqlcmd](../../relational-databases/scripting/run-transact-sql-script-files-using-sqlcmd.md)  
  
  