---
title: "Afficher le journal des applications Windows (Windows) | Microsoft Docs"
ms.custom: 
ms.date: 02/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- viewing logs
- application logs [SQL Server]
- logs [SQL Server], application
- monitoring Windows NT application log [SQL Server]
- Windows NT application logs [SQL Server]
- displaying logs
- monitoring [SQL Server], events
- logs [SQL Server], viewing
ms.assetid: 168a6c6e-12df-46a9-9904-55d63ca8fe14
caps.latest.revision: 25
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 148bb839729d26ca2c9b5dad8d51696e9c8c6a5c
ms.contentlocale: fr-fr
ms.lasthandoff: 06/22/2017

---
# <a name="view-the-windows-application-log-windows-10"></a>Afficher le journal des applications Windows (Windows 10)
  Lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est configuré pour vous permettre d'utiliser le journal des applications Windows, chaque session [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y enregistre des nouveaux événements. Contrairement au journal des erreurs de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , un nouveau journal des applications n'est pas créé chaque fois que vous démarrez une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
### <a name="view-the-windows-application-log"></a>Consulter le journal des applications Windows  
  
1.  Dans la **barre de recherche**, tapez **Observateur d’événements**, puis sélectionnez l’application de bureau Observateur d’événements.
  
2.  Dans l’Observateur d’événements, ouvrez **Journaux des applications et des services**.    
3.  Les événements [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont identifiés par l’entrée **MSSQLSERVER** (les instances nommées sont identifiées par **MSSQL$***<nom_instance>*) dans la colonne **Source**. Les événements de SQL Server Agent sont identifiés par l’entrée SQLSERVERAGENT (pour les instances [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nommées, les événements de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sont identifiés par **SQLAgent$**\<*nom_instance*>). Les événements du service Microsoft Search sont identifiés par l'entrée **Microsoft Search**.  
  
4.  Pour afficher le journal d’un autre ordinateur, cliquez avec le bouton droit sur **Observateur d’événements (local)**, sélectionnez **Connexion à un autre ordinateur**, puis renseignez la boîte de dialogue **Sélectionner un ordinateur**.  
  
5.  Pour afficher uniquement les événements [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , dans le menu **Affichage** , cliquez sur **Filtrer**et dans la liste **Source de l'événement** , sélectionnez **MSSQLSERVER**. Pour afficher uniquement les événements de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , sélectionnez **SQLSERVERAGENT** dans la liste **Source de l'événement** .  
  
6.  Pour obtenir plus de détails sur un événement particulier, double-cliquez sur cet événement.  
  
## <a name="see-also"></a>Voir aussi  
 [Afficher le journal des erreurs SQL Server &#40;SQL Server Management Studio&#41;](../../relational-databases/performance/view-the-sql-server-error-log-sql-server-management-studio.md)  
  
  

