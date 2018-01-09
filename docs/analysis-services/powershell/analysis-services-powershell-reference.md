---
title: "Référence PowerShell Analysis Services | Documents Microsoft"
ms.custom: 
ms.date: 06/21/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 6c435e40-bfaf-4073-8cef-bc3260602246
caps.latest.revision: "9"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: On Demand
ms.openlocfilehash: 4064f8eb4d2dfd37d0ae201977739fff9df67f1a
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2018
---
# <a name="analysis-services-powershell-reference"></a>Référence PowerShell Analysis Services
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]

  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]Applets de commande PowerShell sont inclus dans le [module SqlServer](https://www.powershellgallery.com/packages/SqlServer/21.0.17099). 
  
>[!NOTE] 
> Les opérations de base de données Analysis Services Azure utilisent le même module SqlServer comme SQL Server Analysis Services. Toutefois, pas toutes les applets de commande sont pris en charge pour Azure Analysis Services. Pour plus d’informations, consultez [gérer Azure Analysis Services avec PowerShell](https://docs.microsoft.com/azure/analysis-services/analysis-services-powershell).
  
##  <a name="bkmk_cmdlets"></a> Applets de commande Analysis Services  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] fournit des applets de commande correspondant aux méthodes indiquées dans l’espace de noms **Microsoft.AnalysisServices** . Le tableau suivant décrit chaque applet de commande et fournit un lien vers la méthode AMO correspondante.  
  
 Si vous souhaitez utiliser PowerShell pour effectuer une tâche qui n’est pas représentée dans la liste suivante (par exemple, pour créer ou synchroniser une base de données), vous pouvez écrire le script TMSL ou XMLA de cette action, puis l’exécuter à l’aide de l’applet de commande **Invoke-ASCmd** .  
  
|Applet de commande|Description|Méthodes AMO équivalentes|  
|------------|-----------------|----------------------------|  
|[Applet de commande Add-RoleMember](../../analysis-services/powershell/add-rolemember-cmdlet.md)|Ajoutez un membre à un rôle de base de données.|<xref:Microsoft.AnalysisServices.RoleMemberCollection.Add%2A>|  
|[Applet de commande Backup-ASDatabase](../../analysis-services/powershell/backup-asdatabase-cmdlet.md)|Sauvegardez une base de données Analysis Services.|[Database.Backup](https://msdn.microsoft.com/library/microsoft.analysisservices.database.backup.aspx)|  
|[Invoke-ASCmd, applet de commande](../../analysis-services/powershell/invoke-ascmd-cmdlet.md)|Exécutez une requête ou un script au format XMLA ou TSML (JSON).|<xref:Microsoft.AnalysisServices.Core.Server.Execute%2A>|  
|[Invoke-ProcessASDatabase](../../analysis-services/powershell/invoke-processasdatabase.md)|Traitez une base de données.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Invoke-ProcessCube, applet de commande](../../analysis-services/powershell/invoke-processcube-cmdlet.md)|Traitez un cube.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Invoke-ProcessDimension, applet de commande](../../analysis-services/powershell/invoke-processdimension-cmdlet.md)|Traitez une dimension.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Applet de commande Invoke-ProcessPartition](../../analysis-services/powershell/invoke-processpartition-cmdlet.md)|Traitez une partition.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Invoke-ProcessTable, applet de commande](../../analysis-services/powershell/invoke-processtable-cmdlet.md)|Traitez une table dans un modèle tabulaire, le modèle de compatibilité 1200 ou supérieur.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Merge-Partition, applet de commande](../../analysis-services/powershell/merge-partition-cmdlet.md)|Fusionnez une partition.|<xref:Microsoft.AnalysisServices.Partition.Merge%2A>|  
|[New-RestoreFolder, applet de commande](../../analysis-services/powershell/new-restorefolder-cmdlet.md)|Créer un dossier pour contenir une sauvegarde de base de données.|<xref:Microsoft.AnalysisServices.RestoreFolder>|  
|[Applet de commande New-RestoreLocation](../../analysis-services/powershell/new-restorelocation-cmdlet.md)|Spécifier un ou plusieurs serveurs distants sur lesquels restaurer la base de données.|<xref:Microsoft.AnalysisServices.RestoreLocation>|  
|[Applet de commande Remove-RoleMember](../../analysis-services/powershell/remove-rolemember-cmdlet.md)|Supprimer un membre d'un rôle de base de données.|<xref:Microsoft.AnalysisServices.RoleMemberCollection.Remove%2A>|  
|[Restore-ASDatabase, applet de commande](../../analysis-services/powershell/restore-asdatabase-cmdlet.md)|Restaurer une base de données sur une instance de serveur.|<xref:Microsoft.AnalysisServices.Core.Server.Restore%2A>|  
  

  
  
