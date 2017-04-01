---
title: "MSSQL_ENG021076 | Microsoft Docs"
ms.custom: ""
ms.date: "03/07/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "replication"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "MSSQL_ENG021076 (erreur)"
ms.assetid: 612e5c59-ba3e-49c3-a3df-56bac3d850a2
caps.latest.revision: 15
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 15
---
# MSSQL_ENG021076
    
## Détails du message  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID d'événement|21076|  
|Source de l'événement|MSSQLSERVER|  
|Composant|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|Nom symbolique||  
|Texte du message|L'instantané initial de l'article '%1!' n'est pas encore disponible.|  
  
## Explication  
 L'erreur MSSQL_ENG021076 peut se déclencher si l'Agent de distribution est démarré avant que l'Agent d'instantané ait terminé de générer l'instantané. Cette erreur n'est déclenchée que si la publication ne contient qu'un seul article. Si la publication contient plus d'un article, c'est l'erreur MSSQL_ENG021075 qui est déclenchée à la place. Pour plus d’informations, consultez [MSSQL_ENG021075](../../relational-databases/replication/mssql-eng021075.md).  
  
## Action de l'utilisateur  
 Si l'Agent d'instantané pour la publication n'a pas été démarré depuis la création de l'abonnement, ou depuis la dernière fois que vous avez réinitialisé l'abonnement, démarrez l'Agent d'instantané et laissez-le se terminer avant de démarrer l'Agent de distribution. Pour plus d’informations, consultez [créer et appliquer l’instantané](../../relational-databases/replication/create-and-apply-the-snapshot.md).  
  
 Si l'Agent d'instantané ne se termine pas, recherchez les erreurs dans son historique et résolvez-les. Pour plus d’informations sur l’affichage des détails d’erreur et d’état de l’agent dans le moniteur de réplication, consultez [afficher des informations et effectuer des tâches pour les Agents associés à une Publication & #40 ; Moniteur de réplication & #41 ;](../../relational-databases/replication/monitor/view information and perform tasks for publication agents.md).  
  
 Si l'erreur continue de se produire, augmentez le facteur de journalisation de l'agent et spécifiez un fichier de sortie pour le journal. En fonction du contexte de l'erreur, cette action peut fournir des pistes conduisant à l'erreur et/ou à d'autres messages d'erreur.  
  
## Voir aussi  
 [Erreurs et événements référence & #40 ; Réplication & #41 ;](../../relational-databases/replication/errors-and-events-reference-replication.md)  
  
  