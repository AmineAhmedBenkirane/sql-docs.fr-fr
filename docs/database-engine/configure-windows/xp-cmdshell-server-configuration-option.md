---
title: xp_cmdshell (option de configuration de serveur) | Microsoft Docs
ms.custom: 
ms.date: 03/02/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: configure-windows
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- TSQL
helpviewer_keywords:
- xp_cmdshell
ms.assetid: c147c9e1-b81d-49c8-b800-3019f4d86a13
caps.latest.revision: 16
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Active
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: b32eef170d0834b44932f753075bbd2df67762a2
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="xpcmdshell-server-configuration-option"></a>xp_cmdshell (option de configuration de serveur)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

  L’option **xp_cmdshell** est une option de configuration de serveur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui permet aux administrateurs système de contrôler l’autorisation d’exécuter la procédure stockée étendue **xp_cmdshell** sur un système. Par défaut, l’option **xp_cmdshell** est désactivée sur toutes les nouvelles installations et peut être activée au moyen de la gestion basée sur une stratégie ou en exécutant la procédure stockée système **sp_configure** comme dans l’exemple de code suivant :  
  
```  
-- To allow advanced options to be changed.  
EXEC sp_configure 'show advanced options', 1;  
GO  
-- To update the currently configured value for advanced options.  
RECONFIGURE;  
GO  
-- To enable the feature.  
EXEC sp_configure 'xp_cmdshell', 1;  
GO  
-- To update the currently configured value for this feature.  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Options de configuration de serveur &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md)   
 [Administrer des serveurs à l'aide de la Gestion basée sur des stratégies](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  

