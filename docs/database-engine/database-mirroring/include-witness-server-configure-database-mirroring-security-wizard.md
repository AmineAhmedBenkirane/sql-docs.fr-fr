---
title: "Inclure un serveur t&#233;moin (Configurer l&#39;Assistant S&#233;curit&#233; de mise en miroir de bases de donn&#233;es) | Microsoft Docs"
ms.custom: ""
ms.date: "03/07/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-high-availability"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.swb.configdbmsecurwiz.inclwitness.f1"
ms.assetid: f04b38a4-f4e2-4d4c-bdac-7cc70e5a5684
caps.latest.revision: 32
author: "MikeRayMSFT"
ms.author: "mikeray"
manager: "jhubbard"
caps.handback.revision: 32
---
# Inclure un serveur t&#233;moin (Configurer l&#39;Assistant S&#233;curit&#233; de mise en miroir de bases de donn&#233;es)
  Utilisez cette page pour indiquer si vous voulez inclure un serveur témoin dans cette configuration de sécurité pour la mise en miroir de bases de données.  
  
 **Pour configurer la mise en miroir de bases de données à l'aide de SQL Server Management Studio**  
  
-   [Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server Management Studio&#41;](../../database-engine/database-mirroring/establish database mirroring session - windows authentication.md)  
  
-   [Démarrer l’Assistant Configuration de la sécurité de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;](../../database-engine/database-mirroring/start the configuring database mirroring security wizard.md)  
  
## Options  
 **Oui**  
 Cliquez sur Oui pour inclure une instance de serveur témoin dans la configuration de sécurité. Ce serveur témoin est nécessaire en mode haute sécurité avec basculement automatique, ce qui permet la prise en charge du basculement automatique vers l'instance de serveur miroir en cas de défaillance de l'instance de serveur principal.  
  
 **Non**  
 Cliquez sur Non pour ne pas inclure de serveur témoin dans la configuration de sécurité.  
  
## Voir aussi  
 [Propriétés de la base de données &#40;page Mise en miroir&#41;](../../relational-databases/databases/database-properties-mirroring-page.md)   
 [Mise en miroir de bases de données &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md)   
 [Témoin de mise en miroir de base de données](../../database-engine/database-mirroring/database-mirroring-witness.md)  
  
  