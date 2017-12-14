---
title: "Exécuter une mise à jour factice pour un article de fusion (programmation Transact-SQL de la réplication) | Microsoft Docs"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: replication
ms.reviewer: 
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: TSQL
helpviewer_keywords:
- sp_mergedummyupdate
- dummy updates [SQL Server replication]
ms.assetid: 2f339210-4d85-4843-bd94-e86f7100d3ef
caps.latest.revision: "31"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: d058cd7faeaccb781bcebf1968ac32c4400cf106
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="perform-a-dummy-update-for-a-merge-article-replication-transact-sql-programming"></a>Exécuter une mise à jour factice pour un article de fusion (programmation Transact-SQL de la réplication)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)] La réplication de fusion utilise des déclencheurs dans le cadre du processus de réplication. Lorsqu’une mise à jour est effectuée sur la table publiée, un déclencheur de mise à jour est exécuté. Dans certains cas, les données peuvent être mises à jour sans exécution du déclencheur, comme lors des opérations WRITETEXT et UPDATETEXT. Dans ces cas-là, vous devez ajouter explicitement une instruction UPDATE factice pour répliquer la modification. Vous pouvez ajouter une instruction UPDATE factice à l'aide de procédures stockées de réplication.  
  
### <a name="to-add-a-dummy-update-statement"></a>Pour ajouter une instruction UPDATE factice  
  
1.  Exécutez l'opération (par exemple, UPDATETEXT) sur une ligne d'une table de fusion publiée qui requiert une mise à jour factice.  
  
2.  Sur le serveur (serveur de publication ou Abonné) de la base de données où la modification a été effectuée, exécutez [sp_mergedummyupdate &#40;Transact-SQL&#41;](../../../relational-databases/system-stored-procedures/sp-mergedummyupdate-transact-sql.md). Spécifiez la table sur laquelle la modification a été apportée pour **@source_object**et l'identificateur unique de la ligne modifiée pour **@rowguid**.  
  
3.  Synchronisez l'abonnement pour répliquer la ligne modifiée.  
  
  
