---
title: sysmail_stop_sp (Transact-SQL) | Documents Microsoft
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
- sysmail_stop_sp_TSQL
- sysmail_stop_sp
dev_langs: TSQL
helpviewer_keywords: sysmail_stop_sp
ms.assetid: 045ee36f-5bf0-4626-b5ee-e84db06ce16f
caps.latest.revision: "28"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 0f707d12e77f366d34f48663f623145867bff5c5
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/27/2017
---
# <a name="sysmailstopsp-transact-sql"></a>sysmail_stop_sp (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Arrête la messagerie de base de données en arrêtant les objets [!INCLUDE[ssSB](../../includes/sssb-md.md)] utilisés par le programme externe.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
sysmail_stop_sp  
```  
  
## <a name="arguments"></a>Arguments  
 Aucune  
  
## <a name="return-code-values"></a>Valeurs des codes de retour  
 **0** (réussite) ou **1** (échec)  
  
## <a name="remarks"></a>Notes  
 Cette procédure stockée se trouve dans le **msdb** base de données.  
  
 Elle arrête la file d'attente de la messagerie de base de données contenant les demandes de messages sortants et désactive [!INCLUDE[ssSB](../../includes/sssb-md.md)] pour le programme externe.  
  
 Dès que les files d'attente sont arrêtées, le programme externe de la messagerie de base de données ne traite plus les messages. Cette procédure stockée vous permet d'arrêter la messagerie de base de données pour résoudre des problèmes ou effectuer des tâches de maintenance.  
  
 Pour démarrer la messagerie de base de données, utilisez **sysmail_start_sp**. Notez que **sp_send_dbmail** accepte toujours les messages lorsque le [!INCLUDE[ssSB](../../includes/sssb-md.md)] objets sont arrêtés.  
  
> [!NOTE]  
>  Cette procédure stockée arrête simplement les files d'attente de la messagerie de base de données. Elle ne désactive pas la remise de messages [!INCLUDE[ssSB](../../includes/sssb-md.md)] dans la base de données. Cette procédure stockée ne désactive pas les procédures stockées étendues de la messagerie de base de données pour réduire la zone de surface. Pour désactiver les procédures stockées étendues, consultez la [option Database Mail XPs](../../database-engine/configure-windows/database-mail-xps-server-configuration-option.md) de la **sp_configure** procédure stockée système.  
  
## <a name="permissions"></a>Permissions  
 Autorisations d’exécution de cette procédure reviennent par défaut aux membres de la **sysadmin** rôle serveur fixe.  
  
## <a name="examples"></a>Exemples  
 L’exemple suivant montre comment arrêter la messagerie de base de données dans le **msdb** base de données. Il suppose que la messagerie de base de données a été activée.  
  
```  
USE msdb ;  
GO  
  
EXECUTE dbo.sysmail_stop_sp ;  
GO  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Messagerie de base de données](../../relational-databases/database-mail/database-mail.md)   
 [sysmail_start_sp &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sysmail-start-sp-transact-sql.md)   
 [Messagerie de base de données stockée procédures &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/database-mail-stored-procedures-transact-sql.md)  
  
  
