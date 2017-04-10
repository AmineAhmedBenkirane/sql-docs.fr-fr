---
title: "Objets de messagerie de base de donn&#233;es | Microsoft Docs"
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
  - "messagerie de base de données [SQL Server], bases de données hôtes"
  - "messagerie de base de données [SQL Server], objets de messagerie"
  - "bases de données hôtes de messagerie [SQL Server]"
  - "bases de données hôtes [messagerie de base de données]"
ms.assetid: 5aa2886e-1db1-4066-85df-57ccf4538c54
caps.latest.revision: 32
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 31
---
# Objets de messagerie de base de donn&#233;es
  La base de données **msdb** est la base de données hôte de messagerie de base de données. Elle contient les procédures stockées et les objets de messagerie de la messagerie de base de données. Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] contient l'Assistant Configuration de la messagerie de base de données qui permet d'activer la messagerie de base de données, de créer et de gérer les profils et les comptes, et de configurer les options de la messagerie de base de données.  
  
##  <a name="ComponentsAndConcepts"></a> Objets dans la base de données **msdb**  
 [!INCLUDE[ssSB](../../includes/sssb-md.md)] doit être activé dans la base de données **msdb** . Cependant, la messagerie de base de données n'utilise pas la mise en réseau [!INCLUDE[ssSB](../../includes/sssb-md.md)] . Par conséquent, les utilisateurs ne sont pas obligés de créer un point de terminaison [!INCLUDE[ssSB](../../includes/sssb-md.md)] pour utiliser la messagerie de base de données. Le processus de messagerie de base de données externe utilise une connexion [!INCLUDE[vstecado](../../includes/vstecado-md.md)] standard pour communiquer avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 La messagerie de base de données expose les objets suivants dans la base de données **msdb** lorsque la messagerie de base de données est activée.  
  
 Ces objets sont l'interface de la messagerie de base de données au sein de la base de données hôte de messagerie. D'autres objets sont installés pour implémenter les fonctions proposées par les objets répertoriés ci-dessus. Cependant, ces objets sont réservés à une utilisation interne.  
  
|Nom   |Type|Description|  
|----------|----------|-----------------|  
|[sysmail_allitems &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sysmail-allitems-transact-sql.md)|**Affichage**|Liste tous les messages soumis à la messagerie de base de données.|  
|[sysmail_event_log &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sysmail-event-log-transact-sql.md)|**Affichage**|Liste les messages sur le comportement du [Database Mail External Program](../../relational-databases/database-mail/database-mail-external-program.md).|  
|[sysmail_faileditems &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sysmail-faileditems-transact-sql.md)|**Affichage**|Informations sur les messages que la messagerie de base de données n'a pas pu envoyer|  
|[sysmail_mailattachments &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sysmail-mailattachments-transact-sql.md)|**Affichage**|Informations sur les pièces jointes aux messages de la messagerie de base de données.|  
|[sysmail_sentitems &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sysmail-sentitems-transact-sql.md)|**Affichage**|Informations sur les messages envoyés au moyen de la messagerie de base de données.|  
|[sysmail_unsentitems &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sysmail-unsentitems-transact-sql.md)|**Affichage**|Informations sur les messages que la messagerie de base de données est en train d'envoyer|  
|[sp_send_dbmail &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-send-dbmail-transact-sql.md)|**Procédure stockée**|Envoie des messages électroniques à l'aide de la messagerie de base de données.|  
|[sysmail_delete_log_sp &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sysmail-delete-log-sp-transact-sql.md)|**Procédure stockée**|Efface les messages du journal de la messagerie de base de données.|  
|[sysmail_delete_mailitems_sp &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sysmail-delete-mailitems-sp-transact-sql.md)|**Procédure stockée**|Efface les messages de la file d'attente de la messagerie de base de données.|  
|[sysmail_help_status_sp &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sysmail-help-status-sp-transact-sql.md)|**Procédure stockée**|Indique si la messagerie de base de données est démarrée.|  
|[sysmail_start_sp (Transact-SQL)](../../relational-databases/system-stored-procedures/sysmail-start-sp-transact-sql.md)|**Procédure stockée**|Démarre les objets Service Broker utilisés par le programme externe. Ces objets sont démarrés par défaut.|  
|[sysmail_stop_sp (Transact-SQL)](../../relational-databases/system-stored-procedures/sysmail-stop-sp-transact-sql.md)|**Procédure stockée**|Arrête les objets Service Broker utilisés par le programme externe.|  
  
 [&#91;Haut&#93;](#Top)  
  
## Voir aussi  
 [Messagerie de base de données](../../relational-databases/database-mail/database-mail.md)   
 [SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md)  
  
  