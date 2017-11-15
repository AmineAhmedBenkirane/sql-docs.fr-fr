---
title: MSSQLSERVER_1406 | Microsoft Docs
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords: 1406 (Database Engine error)
ms.assetid: 915f97de-9b74-41f8-8bd5-b2d061416718
caps.latest.revision: "16"
author: edmacauley
ms.author: edmaca
manager: cguyer
ms.workload: Inactive
ms.openlocfilehash: 543a02aceaaed5e6398d7b9e54b3918cc720d683
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="mssqlserver1406"></a>MSSQLSERVER_1406
  
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID d'événement|1406|  
|Source de l'événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|DBM_BADSTATEFORFORCESERVICE|  
|Texte du message|Impossible de forcer le service en toute sécurité. Supprimez la mise en miroir de bases de données et récupérez la base de données "%.*ls" pour y accéder.|  
  
## <a name="explanation"></a>Explication  
Le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] ne peut pas forcer le service car l'état de la mise en miroir ne peut pas garantir le bon fonctionnement du processus impliqué pour forcer le service.  
  
## <a name="user-action"></a>Action de l'utilisateur  
Supprimez la mise en miroir de bases de données. Vous pouvez ensuite récupérer la base de données miroir pour y accéder.  
  
## <a name="see-also"></a>Voir aussi  
[Forcer le service dans une session de mise en miroir de bases de données &#40;Transact-SQL&#41;](~/database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md)  
[Suppression d’une mise en miroir des bases de données &#40;SQL Server&#41;](~/database-engine/database-mirroring/removing-database-mirroring-sql-server.md)  
  
