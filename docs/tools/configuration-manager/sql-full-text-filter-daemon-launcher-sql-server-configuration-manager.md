---
title: "Lanceur de démon de filtre de texte intégral SQL (Gestionnaire de Configuration SQL Server) | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: configuration-manager
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0dc03db-5f76-4558-b041-1ac7b9b5bb16
caps.latest.revision: "8"
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 324fc9e1d780d885aa90b2147ef563742dedcb43
ms.sourcegitcommit: b6116b434d737d661c09b78d0f798c652cf149f3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/17/2018
---
# <a name="sql-full-text-filter-daemon-launcher-sql-server-configuration-manager"></a>Lanceur de démon de filtre de texte intégral SQL (Gestionnaire de configuration SQL Server)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]À compter de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], le service Lanceur de démon de filtre de texte intégral SQL (Lanceur FDHOST) est utilisé par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recherche en texte intégral pour démarrer le processus hôte du démon de filtre, qui gère l’analyse lexicale et le filtrage de recherche en texte intégral. Ce service doit être en cours d'exécution pour que la recherche en texte intégral puisse être utilisée. Le service du lanceur FDHOST est un service dépendant d’une instance qui est associé à une instance spécifique de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Le service du lanceur FDHOST propage les informations sur le compte de service à chaque processus hôte de démon de filtre démarré. Pour plus d’informations sur les processus hôte de démon de filtre, consultez « Architecture de la recherche en texte intégral » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
  
