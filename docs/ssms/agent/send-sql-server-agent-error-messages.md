---
title: "Envoyer des messages d’erreur SQL Server Agent| Microsoft Docs"
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
- messages [SQL Server], SQL Server Agent
- sending messages
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: 2597d0d7-951a-48cf-989f-abb67b9fdb36
caps.latest.revision: 5
author: stevestein
ms.author: sstein
manager: jhubbard
ms.workload: Inactive
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 11c657a4355ae77a068b4fa253cea80386369fc3
ms.contentlocale: fr-fr
ms.lasthandoff: 06/22/2017

---
# <a name="send-sql-server-agent-error-messages"></a>Envoyer des messages d'erreur SQL Server Agent
Cette rubrique explique comment configurer l'Agent [!INCLUDE[msCoName](../../includes/msconame_md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] pour envoyer ses messages d'erreur sur le réseau dans [!INCLUDE[ssCurrent](../../includes/sscurrent_md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)].  
  
**Dans cette rubrique**  
  
-   **Avant de commencer :**  
  
    [Limitations et restrictions](#Restrictions)  
  
    [Sécurité](#Security)  
  
-   [Pour envoyer des messages d'erreur de SQL Server Agent à l'aide de SQL Server Management Studio](#SSMSProcedure)  
  
## <a name="BeforeYouBegin"></a>Avant de commencer  
  
### <a name="Restrictions"></a>Limitations et restrictions  
  
-   Cependant, l'Explorateur d'objets affiche le nœud [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent uniquement si vous avez l'autorisation de l'utiliser.  
  
-   Le service [!INCLUDE[msCoName](../../includes/msconame_md.md)] Windows Messenger doit être en cours d'exécution pour recevoir les événements d'envoi sur le réseau.  
  
### <a name="Security"></a>Sécurité  
  
#### <a name="Permissions"></a>Autorisations  
Pour exécuter ses fonctions, l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] doit être configuré pour utiliser les informations d'identification d'un compte qui est membre du rôle serveur fixe **sysadmin** dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]. Le compte doit avoir les autorisations Windows suivantes :  
  
-   Ouvrir une session en tant que service (SeServiceLogonRight)  
  
-   Remplacer un jeton de niveau processus (SeAssignPrimaryTokenPrivilege)  
  
-   Outrepasser le contrôle de parcours (SeChangeNotifyPrivilege)  
  
-   Changer les quotas de mémoire d'un processus (SeIncreaseQuotaPrivilege)  
  
Pour plus d’informations sur les autorisations Windows requises pour le compte de service [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent, consultez [Sélectionner un compte pour le service SQL Server Agent](../../ssms/agent/select-an-account-for-the-sql-server-agent-service.md) et [Configuration des comptes de service Windows](http://msdn.microsoft.com/en-us/309b9dac-0b3a-4617-85ef-c4519ce9d014).  
  
## <a name="SSMSProcedure"></a>Utilisation de SQL Server Management Studio  
  
#### <a name="to-send-sql-server-agent-error-messages"></a>Pour envoyer des messages d'erreur de SQL Server Agent  
  
1.  Dans l' **Explorateur d'objets**, cliquez sur le signe plus pour développer le serveur qui contient le journal des erreurs de [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent dont vous souhaitez envoyer des messages d'erreur via le réseau.  
  
2.  Cliquez avec le bouton droit sur **SQL Server Agent** , puis sélectionnez **Propriétés**.  
  
3.  Dans la boîte de dialogue **Propriétés de SQL Server Agent –***nom_serveur* , sous **Journal des erreurs** dans la page **Général** , tapez le nom d’utilisateur ou le nom d’ordinateur auquel vous souhaitez envoyer des messages d’erreur dans la zone **Destinataire NET SEND** .  
  
4.  Cliquez sur **OK**.  
  

