---
title: Sys.sp_rda_reconcile_batch (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: dbe-stretch
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.sp_rda_reconcile_batch
- sys.sp_rda_reconcile_batch_TSQL
dev_langs: TSQL
helpviewer_keywords: sys.sp_rda_reconcile_batch stored procedure
ms.assetid: 6d21eac3-7b6c-4fe0-8bc4-bf503f3948a6
caps.latest.revision: "12"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 8aa52f107c3ba3c7332ea207ad0f3fc07e0dd03b
ms.sourcegitcommit: 2208a909ab09af3b79c62e04d3360d4d9ed970a7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/02/2018
---
# <a name="syssprdareconcilebatch-transact-sql"></a>Sys.sp_rda_reconcile_batch (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  Rapproche l’ID de lot stocké dans la table compatible Stretch SQL Server avec l’ID de lot stocké dans la table Azure distante.  
  
 En général, vous devez uniquement exécuter **sp_rda_reconcile_batch** si vous avez supprimé manuellement des données plus récemment migrées à partir de la table distante. Lorsque vous supprimez manuellement les données à distance qui inclut le traitement de la plus récent, les ID de lot ne sont pas synchronisées, et la migration s’arrête.  
 
 Pour supprimer des données qui a déjà été migrées vers Azure, consultez les notes sur cette page.
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
   
## <a name="syntax"></a>Syntaxe  
  
```  
  
sp_rda_reconcile_batch @objname = '@objname'  
  
```  
  
## <a name="arguments"></a>Arguments  
 @objname = '*@objname*'  
 Le nom de la table SQL Server compatible Stretch.  
  
## <a name="permissions"></a>Autorisations  
 Nécessite les autorisations db_owner.  
  
## <a name="remarks"></a>Notes   
 Si vous souhaitez supprimer des données qui a déjà été migrées vers Azure, procédez comme suit.  
  
1.  Suspendre la migration des données. Pour plus d’informations, consultez [suspendre et reprendre la migration des données &#40; Stretch Database &#41; ](../../sql-server/stretch-database/pause-and-resume-data-migration-stretch-database.md).  
  
2.  Supprimer les données de la table intermédiaire de SQL Server en exécutant une commande de suppression avec l’indicateur STAGE_ONLY. Pour plus d’informations, consultez [effectuer des mises à jour administratives et les suppressions](../../sql-server/stretch-database/manage-and-troubleshoot-stretch-database.md#adminHints).
  
3.  Supprimez les données de la table Azure distante en exécutant une commande de suppression avec l’indicateur REMOTE_ONLY.  
  
4.  Exécutez **sp_rda_reconcile_batch**.  
  
5.  Reprendre la migration des données. Pour plus d’informations, consultez [suspendre et reprendre la migration des données &#40; Stretch Database &#41; ](../../sql-server/stretch-database/pause-and-resume-data-migration-stretch-database.md).  
  
## <a name="example"></a> Exemple  
 Pour rapprocher l’ID de lot, exécutez l’instruction suivante.  
  
```sql  
EXEC sp_rda_reconcile_batch @objname = N'StretchEnabledTableName';  
```  
  
  
