---
title: "Propriétés de SQL Server Agent (page Historique) | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.ag.agent.history.f1
ms.assetid: dc73734c-b3c3-407f-bbd1-8714b4fa47b0
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 51839ab3d459e2350c582810fe003fc5086de3eb
ms.lasthandoff: 04/11/2017

---
# <a name="sql-server-agent-properties-history-page"></a>Propriétés de SQL Server Agent (page Historique)
Utilisez cette page pour afficher et modifier des paramètres de gestion du journal d'historique du service [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent.  
  
## <a name="options"></a>Options  
**Limiter la taille du journal d'historique des travaux.**  
Limite la quantité d'informations d'historique des travaux que l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] conserve dans le journal.  
  
**Taille maximale du journal d'historique des travaux (lignes)**  
Spécifie le nombre maximal de lignes que l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] conserve. Lorsque le journal a atteint le nombre de lignes indiqué, l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] supprime les lignes les plus anciennes à mesure que de nouvelles lignes sont insérées.  
  
**Nombre  maximal de lignes d'historique des travaux par travail**  
Spécifie le nombre maximal de lignes que l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] conserve par travail. Lorsque l'historique d'un travail particulier a atteint le nombre de lignes indiqué, l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] supprime les lignes les plus anciennes à mesure que de nouvelles lignes sont insérées.  
  
**Supprimer l'historique de l'agent**  
Indique que l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] va supprimer les entrées présentes dans le journal depuis plus longtemps que la période spécifiée. Il s'agit d'une exécution ponctuelle pour supprimer l'historique. Si vous préférez un travail récurrent, créez et planifiez un plan de maintenance avec un travail de nettoyage.  
  
**Antérieur à**  
Spécifie la période pendant laquelle l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] conserve les entrées.  
  
## <a name="see-also"></a>Voir aussi  
[Journal des erreurs de SQL Server Agent](../../ssms/agent/sql-server-agent-error-log.md)  
  

