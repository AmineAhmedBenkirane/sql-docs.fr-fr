---
title: sp_kill_filestream_non_transacted_handles (Transact-SQL) | Documents Microsoft
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
- sp_kill_filestream_non_transacted_handles_TSQL
- sp_kill_filestream_non_transacted_handles
dev_langs: TSQL
helpviewer_keywords: sp_kill_filestream_non_transacted_handles
ms.assetid: 7188353e-ab29-49a0-8f25-7fb8ab122589
caps.latest.revision: "13"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 7958e7a6513363030d8962774a28992bd055661d
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="filestream-and-filetable---spkillfilestreamnontransactedhandles"></a>FileStream et FileTable - sp_kill_filestream_non_transacted_handles
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Ferme des descripteurs de fichiers non transactionnels aux données de FileTable.  
  
## <a name="syntax"></a>Syntaxe  
  
```tsql  
sp_kill_filestream_non_transacted_handles [[ @table_name = ] ‘table_name’, [[ @handle_id = ] @handle_id]]  
```  
  
## <a name="arguments"></a>Arguments  
 *table_name*  
 Nom de la table dans laquelle fermer des descripteurs non transactionnels.  
  
 Vous pouvez passer *table_name* sans *handle_id* pour fermer tous les descripteurs non transactionnels d’ouverts pour le FileTable.  
  
 Vous pouvez passer NULL pour la valeur de *table_name* pour fermer tous les ouvrir des descripteurs non transactionnels pour tous les FileTables dans la base de données actuelle. NULL est la valeur par défaut.  
  
 *handle_id*  
 ID facultatif du descripteur individuel à fermer. Vous pouvez obtenir le *handle_id* à partir de la [sys.dm_filestream_non_transacted_handles &#40; Transact-SQL &#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql.md) vue de gestion dynamique. Chaque ID est unique dans une instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Si vous spécifiez *handle_id*, vous devez également fournir une valeur pour *table_name*.  
  
 Vous pouvez passer NULL pour la valeur de *handle_id* pour fermer tous les descripteurs non transactionnels d’ouverts pour le FileTable spécifié par *table_name*. NULL est la valeur par défaut.  
  
## <a name="return-code-value"></a>Valeur de Code de retour  
 **0** (réussite) ou **1** (échec)  
  
## <a name="result-set"></a>Jeu de résultats  
 Aucun.  
  
## <a name="general-remarks"></a>Remarques d'ordre général  
 Le *handle_id* requis par **sp_kill_filestream_non_transacted_handles** n’est pas lié à session_id ou de l’unité de travail qui est utilisé dans d’autres **kill** commandes.  
  
 Pour plus d’informations, consultez [Gérer des FileTables](../../relational-databases/blob/manage-filetables.md).  
  
## <a name="metadata"></a>Métadonnées  
 Pour plus d’informations sur les descripteurs de fichiers non transactionnels ouverts, interrogez la vue de gestion dynamique [sys.dm_filestream_non_transacted_handles &#40; Transact-SQL &#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql.md).  
  
## <a name="security"></a>Sécurité  
  
### <a name="permissions"></a>Permissions  
 Vous devez avoir **VIEW DATABASE STATE** autorisation pour obtenir des descripteurs de fichiers à partir de la **sys.dm_FILESTREAM_non_transacted_handles** vue de gestion dynamique et d’exécuter **sp_kill_filestream_non_transacted_handles**.  
  
## <a name="examples"></a>Exemples  
 Les exemples suivants montrent comment appeler **sp_kill_filestream_non_transacted_handles** pour fermer des descripteurs de fichiers non transactionnels pour les données FileTable.  
  
```tsql  
-- Close all open handles in the current database.  
sp_kill_filestream_non_transacted_handles  
  
-- Close all open handles in myFileTable.  
sp_kill_filestream_non_transacted_handles @table_name = ’myFileTable’  
  
-- Close a specific handle in myFileTable.  
sp_kill_filestream_non_transacted_handles @table_name = ’myFileTable’, @handle_id = 0xFFFAAADD  
```  
  
 L’exemple suivant montre comment utiliser un script pour obtenir un *handle_id* et fermez-le.  
  
```tsql  
DECLARE @handle_id varbinary(16);  
DECLARE @table_name sysname;  
  
SELECT TOP 1 @handle_id = handle_id, @table_name = Object_name(table_id)  
FROM sys.dm_FILESTREAM_non_transacted_handles;  
  
EXEC sp_kill_filestream_non_transacted_handles @dbname, @table_name, @handle_id;  
GO  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gérer des FileTables](../../relational-databases/blob/manage-filetables.md)  
  
  
