---
title: Installer SQL Server PowerShell | Microsoft Docs
ms.custom: 
ms.date: 09/05/2017
ms.prod:
- sql-server-2016
- sql-server-2017
ms.reviewer: 
ms.suite: 
ms.technology: setup-install
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 854c0b2f-02d2-46a4-a8cc-6b7a5d191cf8
caps.latest.revision: "9"
author: MikeRayMSFT
ms.author: mikeray
manager: jhubbard
ms.openlocfilehash: 0962e563c85f7707615486bbe87847a7988e6ed6
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="install-sql-server-powershell"></a>Installer SQL Server PowerShell
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Le programme d’installation configure automatiquement les composants de PowerShell.  

Vous installez le logiciel qui fournit la prise en charge de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour Windows PowerShell à l'aide du programme d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Quand vous sélectionnez des fonctionnalités [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui nécessitent la prise en charge de PowerShell, le programme d’installation installe les composants PowerShell [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] suivants :  
  
- Les composants logiciels enfichables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell. Les composants logiciels enfichables sont des fichiers DLL qui implémentent deux types de prises en charge de Windows PowerShell pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:  
  
  - Un jeu d'applets de commande [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Les applets de commande sont des commandes qui implémentent une action spécifique. Par exemple, **Invoke-Sqlcmd** exécute un script [!INCLUDE[tsql](../../includes/tsql-md.md)] ou XQuery qui peut également être exécuté à l’aide de l’utilitaire **sqlcmd** , et **Invoke-PolicyEvaluation** indique si les objets [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont conformes aux stratégies de la gestion basée sur des stratégies.  
  
  - Un fournisseur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Le fournisseur vous permet de naviguer dans la hiérarchie d'objets [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en utilisant un chemin d'accès semblable à un chemin d'accès de système de fichiers. Chaque objet est associé à une classe des modèles objets de gestion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Vous pouvez utiliser les méthodes et propriétés de la classe pour effectuer des travaux sur les objets. Par exemple, si vous changez de répertoire (cd) pour accéder à un objet de bases de données dans un chemin d'accès, vous pouvez utiliser les méthodes et propriétés de la classe Microsoft.SqlServer.Managment.SMO.Database pour gérer la base de données.  
 
- Module **sqlps** importé dans des sessions Windows PowerShell pour charger les composants logiciels enfichables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
 
- [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] prend en charge le démarrage de sessions Windows PowerShell à partir de l’arborescence de l’Explorateur d’objets. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent prend en charge les étapes de travail Windows PowerShell.  
  
PowerShell est installé et configuré dans Windows Server 2012 et Windows 8, et versions ultérieures. Pour plus d’informations sur l’installation de Windows PowerShell, consultez [Installation de Windows PowerShell](http://docs.microsoft.com/powershell/scripting/setup/installing-windows-powershell).  

Pour plus d'informations, consultez :   

- [SQL Server PowerShell](../../relational-databases/scripting/sql-server-powershell.md)  
  
  
