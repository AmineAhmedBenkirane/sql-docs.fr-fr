---
title: Suppression de SSMA pour les composants de DB2 (DB2ToSQL) | Documents Microsoft
ms.prod: sql-non-specified
ms.prod_service: sql-non-specified
ms.service: 
ms.component: ssma-db2
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.technology: sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 4ee0d698-6246-48eb-b963-d62be81cab6a
caps.latest.revision: "6"
author: Shamikg
ms.author: Shamikg
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: a5015a66df18f74e0c0490f9ba1b1bd57bef7846
ms.sourcegitcommit: b2d8a2d95ffbb6f2f98692d7760cc5523151f99d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2017
---
# <a name="removing-ssma-for-db2-components-db2tosql"></a>Suppression de SSMA pour les composants de DB2 (DB2ToSQL)
Lorsque vous avez terminé bases de données de migration à partir de DB2 pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)], vous souhaiterez peut-être désinstaller les composants SSMA. Vous pouvez désinstaller les composants du client à tout moment. Toutefois, vous ne devez pas désinstaller le pack d’extension à partir de [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] , sauf si vos bases de données migrés ne plus utilisent les fonctions dans le **ssma_DB2** schéma de la **sysdb** base de données.  
  
## <a name="uninstalling-the-ssma-for-db2-client"></a>Désinstallation de SSMA pour Client DB2  
Vous pouvez désinstaller SSMA à l’aide de **Ajout / Suppression de programmes**.  
  
**Pour désinstaller SSMA**  
  
1.  Dans le panneau de configuration, ouvrez **Ajout / Suppression de programmes**.  
  
2.  Sélectionnez  **[!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] l’Assistant de Migration pour DB2**, puis cliquez sur **supprimer**.  
  
3.  Pour confirmer que vous souhaitez désinstaller SSMA, cliquez sur **Oui**.  
  
## <a name="uninstalling-the-extension-pack"></a>Désinstallation du Pack d’Extension  
Si vous êtes sûr de vos bases de données migrées n’utilisent pas les objets dans le **sysdb.ssma_DB2** schéma, vous pouvez supprimer le Pack d’extension en le supprimant du schéma : il n’y a aucune désinstallation de Windows  
  
## <a name="see-also"></a>Voir aussi  
[L’installation de SSMA pour DB2 Client &#40; DB2ToSQL &#41;](../../ssma/db2/installing-ssma-for-db2-client-db2tosql.md)  
[L’installation des composants SSMA SQL Server &#40; DB2ToSQL &#41;](../../ssma/db2/installing-ssma-components-on-sql-server-db2tosql.md)  
  
