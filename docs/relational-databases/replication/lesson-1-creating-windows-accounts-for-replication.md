---
title: "Le&#231;on&#160;1&#160;: Cr&#233;ation de comptes Windows pour la r&#233;plication | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "replication"
ms.tgt_pltfrm: ""
ms.topic: "article"
applies_to: 
  - "SQL Server 2016"
helpviewer_keywords: 
  - "réplication [SQL Server], didacticiels"
  - "réplication [SQL Server], administration"
ms.assetid: 65c3816b-47f0-448c-a4a4-ebd3e2a58820
caps.latest.revision: 17
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 17
---
# Le&#231;on&#160;1&#160;: Cr&#233;ation de comptes Windows pour la r&#233;plication
Dans cette leçon, vous allez créer des comptes Windows pour exécuter les agents de réplication. Vous allez créer un compte Windows distinct sur le serveur local pour les agents suivants :  
  
|Agent|Emplacement|Nom du compte|  
|---------|------------|----------------|  
|Agent d'instantané|Serveur de publication|\<*nom_ordinateur*>\repl_snapshot|  
|l'Agent de lecture du journal ;|Serveur de publication|\<*nom_ordinateur*>\repl_logreader|  
|Agent de distribution|Serveur de publication et Abonné|\<*nom_ordinateur*>\repl_distribution|  
|Agent de fusion|Serveur de publication et Abonné|\<*nom_ordinateur*>\repl_merge|  
  
> [!NOTE]  
> Dans les didacticiels de réplication, le serveur de publication et le serveur de distribution partagent la même instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Le serveur de publication et l'Abonné peuvent partager la même instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mais ce n'est pas une obligation. Si le serveur de publication et l'Abonné partagent la même instance, les étapes de création de comptes pour l'Abonné ne sont pas requises.  
  
### Pour créer des comptes Windows locaux pour les agents de réplication sur le serveur de publication  
  
1.  Sur le serveur de publication, dans le Panneau de configuration, dans **Outils d’administration**, ouvrez **Gestion de l’ordinateur**.  
  
2.  Dans **Outils système**, développez **Utilisateurs et groupes locaux**.  
  
3.  Cliquez avec le bouton droit sur **Utilisateurs**, puis cliquez sur **Nouvel utilisateur**.  
  
4.  Entrez **repl_snapshot** dans la zone **Nom d’utilisateur**, fournissez le mot de passe et autres informations appropriées, puis cliquez sur **Créer** pour créer le compte repl_snapshot.  
  
5.  Répétez l'étape précédente pour créer les comptes repl_logreader, repl_distribution et repl_merge.  
  
6.  Cliquez sur **Fermer**.  
  
### Pour créer des comptes Windows locaux pour les agents de réplication sur l'Abonné  
  
1.  Sur l’Abonné, dans le Panneau de configuration, dans **Outils d’administration**, ouvrez **Gestion de l’ordinateur**.  
  
2.  Dans **Outils système**, développez **Utilisateurs et groupes locaux**.  
  
3.  Cliquez avec le bouton droit sur **Utilisateurs**, puis cliquez sur **Nouvel utilisateur**.  
  
4.  Entrez **repl_distribution** dans la zone **Nom d’utilisateur**, fournissez le mot de passe et autres informations appropriées, puis cliquez sur **Créer** pour créer le compte repl_distribution.  
  
5.  Répétez l'étape précédente pour créer le compte repl_merge.  
  
6.  Cliquez sur **Fermer**.  
  
## Étapes suivantes  
Vous avez créé avec succès les comptes Windows des agents de réplication. Ensuite, vous allez configurer le dossier d'instantanés. Voir [Leçon 2 : Préparation du dossier d’instantanés](../../relational-databases/replication/lesson-2-preparing-the-snapshot-folder.md).  
  
## Voir aussi  
[Présentation des Agents de réplication](../../relational-databases/replication/agents/replication-agents-overview.md)  
  
  
  
