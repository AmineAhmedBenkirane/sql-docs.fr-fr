---
title: dbo.sysjobsteps (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 08/09/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-tables
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- dbo.sysjobsteps
- dbo.sysjobsteps_TSQL
- sysjobsteps
- sysjobsteps_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysjobsteps system table
ms.assetid: 978b8205-535b-461c-91f3-af9b08eca467
caps.latest.revision: 
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: f29d3ef22b724abc095da01ea5eef70aa9c447dd
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2018
---
# <a name="dbosysjobsteps-transact-sql"></a>dbo.sysjobsteps (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Contient des informations sur chaque étape d'un travail devant être exécuté par l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Cette table est stockée dans le **msdb** base de données.  
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**job_id**|**uniqueidentifier**|ID du travail.|  
|**step_id**|**int**|ID de l'étape dans le travail|  
|**step_name**|**sysname**|Nom de l'étape du travail|  
|**subsystem**|**nvarchar(40)**|Nom du sous-système utilisé par l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour exécuter l'étape du travail|  
|**commande**|**nvarchar(max)**|Commande à exécuter par **sous-système**.|  
|**flags**|**int**|Réservé.|  
|**additional_parameters**|**ntext**|Réservé.|  
|**cmdexec_success_code**|**int**|Valeur de niveau d’erreur retourné par **CmdExec** les étapes du sous-système pour indiquer une réussite.|  
|**on_success_action**|**tinyint**|Action à exécuter lors du succès d'une étape|  
|**on_success_step_id**|**int**|ID de la prochaine étape à exécuter après le succès d'une étape|  
|**on_fail_action**|**tinyint**|Action à exécuter lors de l'échec d'une étape|  
|**on_fail_step_id**|**int**|ID de l'étape à exécuter après l'échec d'une étape|  
|**server**|**sysname**|Réservé.|  
|**database_name**|**sysname**|Nom de la base de données dans laquelle **commande** est exécutée si **sous-système** TSQL.|  
|**database_user_name**|**sysname**|Nom de l'utilisateur de la base de données dont le compte sera utilisé lors de l'exécution de l'étape|  
|**retry_attempts**|**int**|Nombre de tentatives de reprise en cas d'échec de l'étape|  
|**retry_interval**|**int**|Délai d'attente entre chaque tentative de reprise|  
|**os_run_priority**|**int**|Réservé.|  
|**output_file_name**|**nvarchar(200)**|Nom du fichier dans lequel le résultat de l’étape est sauvegardé lorsque **sous-système** TSQL, PowerShell, ou **CmdExec ***.*|  
|**last_run_outcome**|**int**|Issue de l'exécution précédente de l'étape du travail<br /><br /> **0** = Échec<br /><br /> **1** = a réussi<br /><br /> **2** = nouvelle tentative<br /><br /> **3** = annulée<br /><br /> **5** = inconnu|  
|**last_run_duration**|**int**|Durée (hhmmss) de l'étape lors de sa dernière exécution.|  
|**last_run_retries**|**int**|Nombre de tentatives de reprises lors de la dernière exécution de l'étape du travail|  
|**last_run_date**|**int**|Date (aaaammjj) de début de la dernière exécution de l'étape.|  
|**last_run_time**|**int**|Heure (hhmmss) de début de la dernière exécution de l'étape.|  
|**proxy_id**|**int**|Proxy pour les étapes du travail.|  
|**step_uid**|**uniqueidentifier**|Identificateur de l’étape de travail.|  
  
## <a name="see-also"></a>Voir aussi  
 [Tables de l’Agent SQL Server &#40; Transact-SQL &#41;](../../relational-databases/system-tables/sql-server-agent-tables-transact-sql.md)  
  
  
