---
title: MSSQLSERVER_9003 | Microsoft Docs
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords: 9003 (Database Engine error)
ms.assetid: 7fdfb391-5c6f-428b-b434-6c3d0b30fd7b
caps.latest.revision: "15"
author: edmacauley
ms.author: edmaca
manager: cguyer
ms.workload: Inactive
ms.openlocfilehash: 7a383a9f0ac779c37d4fe9cb56dd2233ccc59215
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="mssqlserver9003"></a>MSSQLSERVER_9003
  
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID d'événement|9003|  
|Source de l'événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|LOG_INVALID_LSN|  
|Texte du message|Le numéro d'analyse du journal % S_LSN transmis à l'analyse du journal dans la base de données '%.*ls' n'est pas valide. Cette erreur peut indiquer les données sont endommagées ou que le fichier journal (.ldf) ne correspond pas au fichier de données (.mdf). Si cette erreur s'est produite pendant la réplication, recréez la publication. Sinon, restaurez les données à partir d'une sauvegarde si le problème se traduit par une défaillance lors du démarrage.|  
  
## <a name="explanation"></a>Explication  
Un composant a passé un numéro séquentiel dans le journal non valide au gestionnaire de fichiers journaux de la base de données. Il peut s'agir d'une réplication, d'une altération ou d'une incohérence entre le fichier de données primaires et le journal.  
  
## <a name="user-action"></a>Action de l'utilisateur  
Si cela s’est produit pendant la réplication, recréez la publication. Sinon, effectuez une restauration à partir de la sauvegarde.  
  
