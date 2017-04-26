---
title: "Configurer WMI pour afficher l’état du serveur dans les outils SQL Server | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WMI Provider for Server Events, setting permissions
- WMI permissions [SQL Server]
ms.assetid: 7e97197b-ed4d-40d1-9a52-9ab1d92401d7
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 950c4d2fdef0359042ebbed168c761e44316ab03
ms.lasthandoff: 04/11/2017

---
# <a name="configure-wmi-to-show-server-status-in-sql-server-tools"></a>Configurer WMI pour afficher l'état du serveur dans les outils SQL Server
Cette rubrique explique comment configurer WMI pour afficher l'état du serveur dans les outils SQL Server dans [!INCLUDE[ssCurrent](../includes/sscurrent_md.md)]. Lors de la connexion aux serveurs, les composants Serveurs inscrits et Explorateur d'objets de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)], ainsi que le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)] , utilisent WMI (Windows Management Instrumentation) pour obtenir l'état des services [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)] (MSSQLSERVER) et [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)] Agent (MSSQLSERVER). Pour afficher l'état du service, l'utilisateur doit disposer des droits d'accéder à distance à l'objet WMI. Cette autorisation peut être configurée seulement si WMI a été installé sur le serveur.  
  
## <a name="SSMSProcedure"></a>Pour configurer l'autorisation WMI  
  
1.  Sur le serveur distant, dans le menu **Démarrer** , cliquez sur **Exécuter**.  
  
2.  Dans la zone **Ouvrir** , tapez **wmimgmt.msc**et cliquez sur **OK**.  
  
3.  Dans le programme **Windows Management Infrastructure** , cliquez avec le bouton droit sur **Contrôle WMI (local)**, puis cliquez sur **Propriétés**.  
  
4.  Dans la boîte de dialogue **Propriétés de WMI Control (Local)** , sous l’onglet **Sécurité** , développez **Root**, puis cliquez sur **CIMV2**.  
  
5.  Cliquez sur **Sécurité** pour ouvrir la boîte de dialogue **Sécurité pour ROOT\CIMV2** .  
  
6.  Ajoutez un groupe ou un utilisateur à la zone **Noms de groupes ou d’utilisateurs** et sélectionnez-le.  
  
7.  Dans la zone **Autorisations pour***<group or user>* , sélectionnez la colonne **Autoriser** correspondant à l’autorisation **Appel à distance autorisé** , pour les utilisateurs dont vous souhaitez détecter à distance l’état de service.  
  
## <a name="see-also"></a>Voir aussi  
[Démarrer, arrêter ou suspendre le service SQL Server Agent](../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md)  
  

