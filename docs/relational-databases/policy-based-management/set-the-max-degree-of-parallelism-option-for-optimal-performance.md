---
title: "Définir l’option max degree of parallelism pour des performances optimales | Microsoft Docs"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: performance-monitor
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: ec908006-67ae-4674-9a61-25ea741d6197
caps.latest.revision: 
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 20adae41c9cb1913f9c03fa0e4c2257583743475
ms.sourcegitcommit: dcac30038f2223990cc21775c84cbd4e7bacdc73
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/18/2018
---
# <a name="set-the-max-degree-of-parallelism-option-for-optimal-performance"></a>Définir l'option max degree of parallelism pour des performances optimales
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)] Cette règle détermine si l’option Max Degree Of Parallelism (MAXDOP) (degré maximum de parallélisme) est définie sur une valeur supérieure à 8. La définition d'une valeur supérieure à 8 conduit souvent à la consommation inutile de ressources et à la dégradation des performances.  
  
## <a name="best-practices-recommendations"></a>Meilleures pratiques recommandées  
 Définissez l'option max degree of parallelism sur 8 ou une valeur supérieure à l'aide de sp_configure.  
  
## <a name="for-more-information"></a>Pour plus d'informations  
 [Article 329204 de la Base de connaissances Microsoft](http://go.microsoft.com/fwlink/?linkid=117786)  
  
 [Configurer l'option de configuration du serveur Degré maximal de parallélisme](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md)  
  
 [sp_configure &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)  
  
  
