---
title: sysmail_help_queue_sp (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/04/2017
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
- sysmail_help_queue_sp
- sysmail_help_queue_sp_TSQL
dev_langs: TSQL
helpviewer_keywords: sysmail_help_queue_sp
ms.assetid: 94840482-112c-4654-b480-9b456c4c2bca
caps.latest.revision: "17"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 233187d223f7d22c5a950fcb2d29063f37be7c7d
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="sysmailhelpqueuesp-transact-sql"></a>sysmail_help_queue_sp (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Il existe deux files d'attente dans la messagerie de base de données : la file d'attente des messages et la file d'attente des états.. La file d'attente des messages stocke les éléments de messagerie en attente d'envoi. La file d'attente des états stocke l'état des éléments qui ont déjà été envoyés. Cette procédure stockée permet d'afficher l'état de la file d'attente des messages ou des états. Si le paramètre  **@queue_type**  n’est pas spécifié, la procédure stockée renvoie une ligne pour chaque file d’attente.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
sysmail_help_queue_sp  [ @queue_type = ] 'queue_type'  
```  
  
## <a name="arguments"></a>Arguments  
 [  **@queue_type**  =] **'***queue_type***'**  
 Argument facultatif qui supprime les messages électroniques du type spécifié en tant que le *queue_type*. *queue_type* est **nvarchar(6)** sans valeur par défaut. Les entrées valides sont **mail** et **état**.  
  
## <a name="return-code-values"></a>Valeurs des codes de retour  
 **0** (réussite) ou **1** (échec)  
  
## <a name="result-set"></a>Jeu de résultats  
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**queue_type**|**nvarchar(6)**|Type de file d'attente. Les valeurs possibles sont **mail** et **état**.|  
|**longueur**|**int**|Nombre d'éléments de messagerie dans la file d'attente spécifiée.|  
|**état**|**nvarchar (64)**|État du moniteur. Les valeurs possibles sont **inactif** (file d’attente est inactive), **notifiés** (file d’attente a été notifié de réception va se produire), et **RECEIVES_OCCURRING** (file d’attente reçoit).|  
|**last_empty_rowset_time**|**DATE/HEURE**|Date et heure à laquelle la file d'attente était vide pour la dernière fois. Format 24 heures et fuseau horaire GMT.|  
|**last_activated_time**|**DATE/HEURE**|Date et heure de la dernière activation de la file d'attente. Format 24 heures et fuseau horaire GMT.|  
  
## <a name="remarks"></a>Notes  
 Lors du dépannage de la messagerie de base de données, utilisez **sysmail_help_queue_sp** pour voir combien d’éléments dans la file d’attente, l’état de la file d’attente, et lorsqu’il a été activé.  
  
## <a name="permissions"></a>Permissions  
 Par défaut, seuls les membres de la **sysadmin** rôle serveur fixe peut accéder à cette procédure.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant renvoie la file d'attente des messages ainsi que celle des états.  
  
```  
EXECUTE msdb.dbo.sysmail_help_queue_sp ;  
GO  
```  
  
 Il s'agit d'un exemple de jeu de résultats qui a été remis en forme pour des raisons de longueur.  
  
```  
queue_type length      state              last_empty_rowset_time  last_activated_time  
---------- -------- ------------------ ----------------------- -----------------------  
mail       0        RECEIVES_OCCURRING 2005-10-07 21:14:47.010 2005-10-10 20:52:51.517  
status     0        INACTIVE           2005-10-07 21:04:47.003 2005-10-10 21:04:47.003  
  
(2 row(s) affected)  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Messagerie de base de données](../../relational-databases/database-mail/database-mail.md)  
  
  