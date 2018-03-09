---
title: sys.sp_rda_reconcile_indexes (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology:
- dbe-stretch
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_rda_reconcile_indexes
- sp_rda_reconcile_indexes_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.sp_rda_reconcile_indexes stored procedure
ms.assetid: 96b31ab9-bf84-46d6-9990-81f5c51f885a
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 9a8fd2d58b8df3555da488e9a90b750c9ff583a7
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2018
---
# <a name="syssprdareconcileindexes-transact-sql"></a>sys.sp_rda_reconcile_indexes (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  Les files d’attente une tâche de schéma pour réconcilier les index sur la table distante. Une fois cette tâche se termine correctement, la table distante a les mêmes index qui existent sur la table locale prenant en charge Stretch.  
  
 S’il existe une autre tâche en file d’attente pour réconcilier les index lorsque vous appelez **sp_rda_reconcile_indexes**, cette procédure stockée n’en file d’attente une tâche en double.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
sp_rda_reconcile_indexes [@objname = ] 'objname'  
  
```  
  
## <a name="arguments"></a>Arguments  
 [@objname = ] *'objname'*  
 Est le nom qualifié ou non qualifié de la table compatible Stretch pour lequel vous souhaitez réconcilier les index. Guillemets sont requis uniquement si vous spécifiez un objet qualifié.  
  
## <a name="return-code-values"></a>Valeurs des codes de retour  
 0 (réussite) ou >0 (échec)  
  
## <a name="see-also"></a>Voir aussi  
 [Stretch Database](../../sql-server/stretch-database/stretch-database.md)  
  
  
