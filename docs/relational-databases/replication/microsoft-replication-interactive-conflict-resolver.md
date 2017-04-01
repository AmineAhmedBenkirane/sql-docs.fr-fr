---
title: "Outil de r&#233;solution des conflits de r&#233;plication Microsoft interactif | Microsoft Docs"
ms.custom: ""
ms.date: "03/07/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "replication"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.rep.replconflictviewer.interactiveresolver.f1"
ms.assetid: d3d4a480-782b-4b1d-b839-565c8cf6cb24
caps.latest.revision: 23
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 23
---
# Outil de r&#233;solution des conflits de r&#233;plication Microsoft interactif
  L'Outil de résolution des conflits de réplication Microsoft interactif peut s'utiliser pour les abonnements de fusion synchronisés au moyen du Gestionnaire de synchronisation Windows. Il permet d'afficher, comparer, modifier et sélectionner les conflits dans les données des résultats. La réplication comporte également l'Outil de résolution des conflits qui permet d'afficher et de modifier les résultats des conflits après leur validation. L'Outil de résolution des conflits interactif permet de sélectionner le résultat pendant la synchronisation.  
  
> [!NOTE]  
>  Les conflits qui concernent des enregistrements logiques ne sont pas affichés dans le résolveur interactif. Pour afficher des informations sur ces conflits, utilisez des procédures stockées de réplication. Pour plus d’informations, consultez [Afficher les informations de conflit pour les Publications de fusion & #40 ; Programmation de Transact-SQL de réplication & #41 ;](../../relational-databases/replication/view conflict information for merge publications.md).  
  
## Options  
 **Nom de colonne**  
 Noms de toutes les colonnes de la table. Une ou plusieurs colonnes peuvent comporter des données en conflit. Indépendamment des colonnes en conflit, la ligne gagnante complète remplace la totalité de la ligne perdante.  
  
 **Résolution suggérée**  
 Résolution du conflit suggérée par l'outil de résolution des conflits pour l'article.  
  
 **Serveur de publication**  
 Valeur des données du serveur de publication.  
  
 **Abonné**  
 Valeur des données de l'abonné.  
  
 **Accepter la suggestion**, **accepter le serveur de publication**, et **accepter l’abonné**  
 Cliquez sur l'option correspondante pour accepter la ligne qui sera appliquée par le serveur de publication ou l'abonné, en fonction du perdant du conflit. Si le serveur de publication perd le conflit, tous les autres abonnés reçoivent la ligne gagnante lors de leur prochaine synchronisation avec le serveur de publication.  
  
 **Résoudre automatiquement tous les conflits restants**  
 Résout tous les conflits restants en utilisant la résolution suggérée par l'outil de résolution des conflits pour l'article.  
  
 **Journaliser les détails de ce conflit pour future référence**  
 Enregistre les détails du conflit dans des tables système.  
  
## Voir aussi  
 [Résolution interactive des conflits](../../relational-databases/replication/merge/interactive-conflict-resolution.md)   
 [Afficher et résoudre les conflits de données pour les Publications de fusion & #40 ; SQL Server Management Studio & #41 ;](../../relational-databases/replication/view and resolve data conflicts for merge publications.md)   
 [Synchroniser un abonnement à l’aide du Gestionnaire de synchronisation Windows & #40 ; Le Gestionnaire de synchronisation Windows & #41 ;](../../relational-databases/replication/synchronize a subscription using windows synchronization manager.md)   
 [Détection et résolution avancées des conflits de réplication de fusion](../../relational-databases/replication/merge/advanced-merge-replication-conflict-detection-and-resolution.md)  
  
  