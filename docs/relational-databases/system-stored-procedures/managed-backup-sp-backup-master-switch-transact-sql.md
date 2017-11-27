---
title: managed_backup.sp_ backup_master_switch (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_ backup_master_switch
- smart_admin.sp_ backup_master_switch
- sp_ backup_master_switch_TSQL
- smart_admin.sp_ backup_master_switch_TSQL
dev_langs: TSQL
helpviewer_keywords:
- sp_ backup_master_switch
- smart_admin.sp_ backup_master_switch
ms.assetid: 1ed2b2b2-c897-41cc-bed5-1c6bc47b9dd2
caps.latest.revision: "12"
author: MikeRayMSFT
ms.author: mikeray
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 0d7567235212388b477abcbfddca8049f2ada735
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="managedbackupsp-backupmasterswitch-transact-sql"></a>managed_backup.sp_ backup_master_switch (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  Interrompt ou reprend la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].  
  
 Utilisez cette procédure stockée pour interrompre temporairement et reprendre la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]. De cette façon, tous les paramètres de configuration sont conservés et pourront être appliqués à la reprise des opérations. Lorsque la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] est interrompue, la période de rétention n'est pas appliquée. Cela signifie qu'il n'y a pas de vérification pour déterminer si les fichiers doivent être supprimés du stockage ou s'il existe des fichiers de sauvegarde corrompus ou une rupture dans la séquence de journaux de transactions consécutifs.  
  

  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```tsql  
EXEC managed_backup.sp_backup_master_switch   
                     [@state = ] { 0 | 1}  
```  
  
##  <a name="Arguments"></a> Arguments  
 @state  
 Définissez l'état de la [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]. Le @state paramètre est **bits**. Si la valeur 0 est définie, les opérations sont interrompues, et si la valeur est 1, l'opération reprend.  
  
## <a name="return-code-value"></a>Valeur de Code de retour  
 0 (réussite) ou 1 (échec)  
  
## <a name="security"></a>Sécurité  
 Décrit les problèmes de sécurité relatifs à l'instruction qui inclut les autorisations sous la forme d'une sous-section (en-tête H3). Envisagez d'inclure d'autres sous-sections pour le chaînage des propriétés et l'audit, le cas échéant.  
  
### <a name="permissions"></a>Permissions  
 Nécessite l’appartenance au **db_backupoperator** de la base de données de rôle, avec **ALTER ANY CREDENTIAL** autorisations, et **EXECUTE** autorisations sur **sp_delete_backuphistory**procédure stockée.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant peut être utilisé pour interrompre le service de [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] sur l'instance sur laquelle il est exécuté :  
  
```  
Use msdb;  
GO  
EXEC managed_backup.sp_master_switch @state=0;  
Go  
  
```  
  
 L’exemple suivant peut être utilisé pour reprendre [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].  
  
```  
Use msdb;  
GO  
EXEC managed_backup.sp_master_switch @state=1;  
Go  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Sauvegarde managée SQL Server sur Microsoft Azure](../../relational-databases/backup-restore/sql-server-managed-backup-to-microsoft-azure.md)  
  
  
