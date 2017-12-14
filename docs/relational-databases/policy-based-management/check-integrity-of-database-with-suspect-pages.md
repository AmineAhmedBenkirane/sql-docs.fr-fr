---
title: "Vérifier l’intégrité d’une base de données contenant des pages suspectes | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: performance-monitor
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Best Practices [Database Engine]
ms.assetid: 3b1ec9fe-f6c5-46f7-aa63-6e671be1572d
caps.latest.revision: "10"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: a6999acc42dac211b14b22489fc6941043f98d48
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="check-integrity-of-database-with-suspect-pages"></a>Vérifier l'intégrité d'une base de données contenant des pages suspectes
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)] Cette règle recherche les bases de données utilisateur dont l’état de base de données a la valeur suspect. Lorsque le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] lit une page de la base de données contenant une erreur 824, cette page est jugée suspecte, son ID est enregistré dans la table suspect_pages dans msdb et la base de données contenant cette page prend la valeur suspecte.  
  
 L'erreur 824 indique qu'une erreur de cohérence logique a été détectée au cours d'une opération de lecture. Cette erreur indique généralement que des données ont été endommagées par un composant défectueux du sous-système d'E/S. Il s'agit d'une condition d'erreur grave qui menace l'intégrité de la base de données et qui doit être immédiatement corrigée.  
  
## <a name="best-practices-recommendations"></a>Meilleures pratiques recommandées  
  
-   Examinez les détails de l'erreur 824 pour cette base de données dans le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
-   Effectuez une vérification complète de la cohérence de la base de données ([DBCC CHECKDB](../../t-sql/database-console-commands/dbcc-checkdb-transact-sql.md)).  
  
-   Implémentez les actions utilisateur définies dans [MSSQLSERVER_824](http://go.microsoft.com/fwlink/?LinkId=81397).  
  
## <a name="for-more-information"></a>Pour plus d'informations  
 [Gérer la table suspect_pages &#40;SQL Server&#41;](../../relational-databases/backup-restore/manage-the-suspect-pages-table-sql-server.md)  
  
  
