---
title: "Exécuter Windows PowerShell à partir de SQL Server Management Studio | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: ssms-scripting
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f841825-da1f-4062-9a81-3cdbab03845b
caps.latest.revision: "11"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: f5ed1e815f1a98d791d7cf7d95ce233de15c3d02
ms.sourcegitcommit: b603dcac7326bba387befe68544619e026e6a15e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="run-windows-powershell-from-sql-server-management-studio"></a>Exécuter Windows PowerShell à partir de SQL Server Management Studio
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)] Vous pouvez démarrer des sessions Windows PowerShell à partir de **l’Explorateur d’objets** dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]. [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] lance Windows PowerShell, charge le module **sqlps** et affecte au contexte de chemin le nœud associé dans l’arborescence de l’ **Explorateur d’objets** .  
  
## <a name="before-you-begin"></a>Avant de commencer  
 Quand vous spécifiez l’exécution de PowerShell pour un objet dans l’ **Explorateur d’objets**, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] démarre une session Windows PowerShell dans laquelle les composants logiciels enfichables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell ont été chargés et inscrits. Le chemin d'accès de la session est prédéfini avec l'emplacement de l'objet sur lequel vous avez cliqué avec le bouton droit dans l'Explorateur d'objets. Par exemple, si vous cliquez avec le bouton droit sur l’objet de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] dans l’Explorateur d’objets et que vous sélectionnez **Démarrer PowerShell**, le chemin Windows PowerShell est défini comme suit :  
  
```  
SQLSERVER:\SQL\MyComputer\MyInstance\Databases\AdventureWorks2012>  
```  
  
## <a name="run-powershell"></a>Exécuter PowerShell  
 **Pour exécuter PowerShell à partir de SQL Server Management Studio**  
  
1.  Ouvrez l' **Explorateur d'objets**.  
  
2.  Accédez au nœud de l'objet à utiliser.  
  
3.  Cliquez avec le bouton droit sur l’objet et sélectionnez **Démarrer PowerShell**.  
  
## <a name="permissions"></a>Autorisations  
 S'il a été ouvert à partir de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], PowerShell ne fonctionne pas avec les privilèges d'administrateur, ce qui peut empêcher certaines activités telles que les appels à WMI.  
  
## <a name="see-also"></a> Voir aussi  
 [SQL Server PowerShell](../../relational-databases/scripting/sql-server-powershell.md)  
  
  
