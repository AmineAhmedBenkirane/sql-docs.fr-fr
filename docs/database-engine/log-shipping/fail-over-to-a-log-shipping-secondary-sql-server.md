---
title: "Basculer vers une base de donn&#233;es secondaire de copie des journaux de transaction (SQL Server) | Microsoft Docs"
ms.custom: ""
ms.date: "03/07/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-high-availability"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "bases de données primaires [SQL Server]"
  - "fichiers de données secondaires [SQL Server], basculement manuel"
  - "copie des journaux de transaction [SQL Server], basculement"
  - "basculement [SQL Server], copie des journaux de transaction"
ms.assetid: edfe5d59-4287-49c1-96c9-dd56212027bc
caps.latest.revision: 31
author: "MikeRayMSFT"
ms.author: "mikeray"
manager: "jhubbard"
caps.handback.revision: 31
---
# Basculer vers une base de donn&#233;es secondaire de copie des journaux de transaction (SQL Server)
  Le basculement vers une base de données secondaire de copie des journaux de transactions est utile en cas d'échec ou d'un besoin de maintenance de l'instance du serveur principal.  
  
## Préparation en vue d'un basculement contrôlé  
 En règle générale, les bases de données primaire et secondaire ne sont pas synchronisées, car la base de données primaire est en permanence mise à jour après son dernier travail de sauvegarde. De même, dans certains cas, les sauvegardes récentes du journal des transactions n'ont pas été copiées dans les instances du serveur secondaire ou certaines copies des sauvegardes du journal n'ont peut-être pas encore été appliquées dans la base de données secondaire. Si possible, nous vous recommandons de commencer par synchroniser l'ensemble des bases de données secondaires avec la base de données primaire.  
  
 Pour plus d’informations sur l’opération de copie des journaux de transaction, consultez [À propos de la copie des journaux de transaction &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).  
  
## Basculement  
 Pour basculer vers une base de données secondaire :  
  
1.  Copiez tous les fichiers de sauvegarde non copiés du partage de sauvegarde vers le dossier de destination de copie de chaque serveur secondaire.  
  
2.  Appliquez à la suite toutes les sauvegardes non appliquées du journal des transactions à chaque base de données secondaire. Pour plus d’informations, consultez [Appliquer les sauvegardes du journal de transactions &#40;SQL Server&#41;](../../relational-databases/backup-restore/apply-transaction-log-backups-sql-server.md).  
  
3.  Si la base de données primaire est accessible, sauvegardez le journal des transactions actif et appliquez la sauvegarde du journal aux bases de données secondaires.  
  
     Si l'instance du serveur principal d'origine n'est pas endommagée, sauvegardez la fin du journal des transactions de la base de données primaire à l'aide de l'option WITH NORECOVERY. Cette opération laisse la base de données en état de restauration et donc inaccessible aux utilisateurs. Par la suite, vous pouvez la restaurer par progression en appliquant les sauvegardes du journal des transactions à partir de la base de données primaire de remplacement.  
  
     Pour plus d’informations, consultez [Sauvegardes du journal des transactions &#40;SQL Server&#41;](../../relational-databases/backup-restore/transaction-log-backups-sql-server.md).  
  
4.  Une fois que les serveurs secondaires sont synchronisés, vous pouvez basculer vers celui de votre choix en récupérant sa base de données secondaire et en redirigeant des clients vers cette instance de serveur. La récupération place la base de données dans un état cohérent et permet sa mise en ligne.  
  
    > [!NOTE]  
    >  Lorsque vous rendez une base de données secondaire disponible, vous devez vous assurer que ses métadonnées sont cohérentes avec celles de la base de données primaire d'origine. Pour plus d’informations, consultez [Gérer les métadonnées lors de la mise à disposition d’une base de données sur une autre instance de serveur &#40;SQL Server&#41;](../../relational-databases/databases/manage metadata when making a database available on another server.md).  
  
5.  Une fois que vous avez récupéré une base de données secondaire, vous pouvez la reconfigurer en tant que base de données primaire pour d'autres bases de données secondaires.  
  
     Si aucune autre base de données secondaire n’est disponible, consultez [Configurer la copie des journaux de transaction &#40;SQL Server&#41;](../../database-engine/log-shipping/configure-log-shipping-sql-server.md).  
  
##  <a name="RelatedTasks"></a> Tâches associées  
  
-   [Changer des rôles entre les serveurs primaire et secondaire de copie des journaux de transaction &#40;SQL Server&#41;](../../database-engine/log-shipping/change-roles-between-primary-and-secondary-log-shipping-servers-sql-server.md)  
  
-   [Gestion des connexions et des travaux après un basculement de rôle &#40;SQL Server&#41;](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
## Voir aussi  
 [Tables et procédures stockées liées à la copie des journaux de transaction](../../database-engine/log-shipping/log-shipping-tables-and-stored-procedures.md)   
 [À propos de la copie des journaux de transaction &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [Sauvegardes de la fin du journal &#40;SQL Server&#41;](../../relational-databases/backup-restore/tail-log-backups-sql-server.md)  
  
  