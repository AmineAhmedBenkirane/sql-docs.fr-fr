---
title: "Configurer les journaux d’erreurs de SQL Server Agent (page Général) | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology: tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: sql13.ag.errorlog.configure.f1
ms.assetid: e08de622-6f87-470c-aee0-b2d6cb6cca88
caps.latest.revision: "4"
author: stevestein
ms.author: sstein
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 25c3ed7443a670d44a82ddc04bafedb62d9fe4eb
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="configure-sql-server-agent-error-logs-general-page"></a>Configurer les journaux d’erreurs de SQL Server Agent (page Général)
Utilisez cet écran pour afficher et mettre à jour les paramètres du journal des erreurs de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] .  
  
## <a name="options"></a>Options  
**Fichier journal des erreurs**  
Spécifie le nom du fichier dans lequel l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] consigne les erreurs.  
  
**...**  
Permet de parcourir l'arborescence à la recherche du fichier journal des erreurs.  
  
**Écrire dans le fichier journal des erreurs OEM**  
Écrit le fichier journal des erreurs comme un fichier non-Unicode. Cela réduit l'espace disque utilisé par le fichier journal. Toutefois, si vous activez cette option, sachez que les messages incluant des données Unicode peuvent être plus difficiles à lire.  
  
**Erreurs**  
Écrit uniquement les erreurs et les messages d'information dans le fichier journal.  
  
**Avertissements**  
Écrit uniquement les avertissements et les messages d'information dans le fichier journal.  
  
**Informations**  
Écrit uniquement les messages d'information dans le fichier journal.  
  
## <a name="see-also"></a>Voir aussi  
[Journal des erreurs de l'Agent SQL Server](../../ssms/agent/sql-server-agent-error-log.md)  
  
