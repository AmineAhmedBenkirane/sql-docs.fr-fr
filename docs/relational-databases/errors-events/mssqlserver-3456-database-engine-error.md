---
title: MSSQLSERVER_3456 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: errors-events
ms.reviewer: ''
ms.suite: sql
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: language-reference
helpviewer_keywords:
- 3456 (Database Engine error)
ms.assetid: d11b2b2c-3ae4-4023-b82f-05b561bfacce
caps.latest.revision: 10
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: d06739b8d95741295c5f401fa96f9733d3d1cbc4
ms.sourcegitcommit: f1caaa156db2b16e817e0a3884394e7b30fb642f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="mssqlserver3456"></a>MSSQLSERVER_3456
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID d'événement|3456|  
|Source de l'événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|REC_REDOLSNMISMATCH|  
|Texte du message|Impossible de rétablir l'enregistrement du journal %S_LSN, pour l'ID de transaction %S_XID, à la page %S_PGID, base de données '%.*ls' (ID de base de données %d). Page : numéro de séquence d'enregistrement = %S_LSN, type = %ld. Journal : OpCode = %ld, contexte %ld, PrevPageLSN : %S_LSN. Effectuez une restauration à partir d'une sauvegarde de la base de données ou réparez la base de données.|  
  
## <a name="explanation"></a>Explication  
L'opération de restauration n'a pas pu rétablir le journal des transactions. Cette erreur a placé la base de données dans l'état SUSPECT. Le groupe de fichiers primaire et éventuellement d'autres groupes de fichiers sont suspects et peut-être endommagés. La base de données ne peut pas être récupérée au démarrage de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et n'est par conséquent pas disponible. Une action est requise de la part de l'utilisateur pour résoudre le problème.  
  
Notez que si cette erreur se produit pour **tempdb**, l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'arrête.  
  
## <a name="user-action"></a>Action de l'utilisateur  
Cette erreur peut être provoquée par une situation temporaire qui existait sur le système lors d'une tentative donnée de démarrer l'instance du serveur ou de récupérer une base de données. Cette erreur peut également être provoquée par un échec permanent qui se produit à chaque tentative de démarrage de la base de données. Pour plus d'informations sur la cause, examinez le journal des événements Windows pour rechercher une erreur précédente qui indique l'échec spécifique.  
  
Pour plus d’informations sur la cause de l’occurrence de l’erreur 3456, examinez le journal des événements Windows pour rechercher une erreur précédente qui indique l’échec spécifique. L'action utilisateur appropriée varie selon que les informations dans le Journal des événements Windows indiquent que l'erreur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a été provoquée par une condition transitoire ou un échec permanent. Pour plus d’informations sur les actions utilisateur requises pour le dépannage de l’erreur 3456, consultez la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="see-also"></a> Voir aussi  
[ALTER DATABASE &#40;Transact-SQL&#41;](~/t-sql/statements/alter-database-transact-sql-set-options.md)  
[DBCC CHECKDB &#40;Transact-SQL&#41;](~/t-sql/database-console-commands/dbcc-checkdb-transact-sql.md)  
[Restaurations complètes de bases de données &#40;mode de récupération simple&#41;](~/relational-databases/backup-restore/complete-database-restores-simple-recovery-model.md)  
[MSSQLSERVER_824](~/relational-databases/errors-events/mssqlserver-824-database-engine-error.md)  
[sys.databases &#40;Transact-SQL&#41;](~/relational-databases/system-catalog-views/sys-databases-transact-sql.md)  
  
