---
title: "Prise en charge d’OLTP en mémoire par Transact-SQL | Microsoft Docs"
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine-imoltp
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b1cc7c30-1747-4c21-88ac-e95a5e58baac
caps.latest.revision: 52
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: cc975fbbdb4118158e4beacef63f45a63c479d38
ms.contentlocale: fr-fr
ms.lasthandoff: 04/11/2017

---
# <a name="transact-sql-support-for-in-memory-oltp"></a>Prise en charge d'OLTP en mémoire par Transact-SQL
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  Les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes incluent des options de syntaxe pour prendre en charge l’OLTP en mémoire :  
  
-   [Options de fichiers et de groupes de fichiers ALTER DATABASE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql-file-and-filegroup-options.md) (ajout de **MEMORY_OPTIMIZED_DATA**)  
  
-   [ALTER TRIGGER &#40;Transact-SQL&#41;](../../t-sql/statements/alter-trigger-transact-sql.md)  
  
-   [CRÉER une base de données &#40; SQL Server Transact-SQL &#41;](../../t-sql/statements/create-database-sql-server-transact-sql.md) (ajout de **MEMORY_OPTIMIZED_DATA**)  
  
-   [CREATE PROCEDURE &#40;Transact-SQL&#41;](../../t-sql/statements/create-procedure-transact-sql.md)  
  
-   [CREATE TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/create-table-transact-sql.md)  
  
-   [CREATE TRIGGER &#40;Transact-SQL&#41;](../../t-sql/statements/create-trigger-transact-sql.md)  
  
-   [CREATE TYPE &#40;Transact-SQL&#41;](../../t-sql/statements/create-type-transact-sql.md)  
  
-   [DECLARE @local_variable &#40;Transact-SQL&#41;](../../t-sql/language-elements/declare-local-variable-transact-sql.md)   
    Dans une procédure stockée compilée en mode natif, vous pouvez déclarer une variable comme étant **NOT NULL**. Vous ne pouvez pas le faire dans une procédure stockée standard.  
  
 **AUTO_UPDATE_STATISTICS** peut avoir la valeur **ON** pour les tables optimisées en mémoire, à compter de SQL Server 2016. Pour plus d’informations, consultez [sp_autostats &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-autostats-transact-sql.md).  
  
 [SET STATISTICS XML &#40;Transact-SQL&#41;](../../t-sql/statements/set-statistics-xml-transact-sql.md) L’option ON n’est pas prise en charge avec les procédures stockées compilées en mode natif.  
  
 Pour plus d’informations sur les fonctionnalités non prises en charge, consultez [Les constructions Transact-SQL ne sont pas prises en charge par l’OLTP en mémoire](../../relational-databases/in-memory-oltp/transact-sql-constructs-not-supported-by-in-memory-oltp.md).  
  
 Pour plus d’informations sur les constructions prises en charge dans et sur les procédures stockées compilées en mode natif, consultez [Fonctionnalités prises en charge pour les modules T-SQL compilés en mode natif](../../relational-databases/in-memory-oltp/supported-features-for-natively-compiled-t-sql-modules.md) et [Constructions prises en charge dans les procédures stockées compilées en mode natif](../../relational-databases/in-memory-oltp/supported-ddl-for-natively-compiled-t-sql-modules.md).  
  
## <a name="see-also"></a>Voir aussi  
 [OLTP en mémoire &#40;optimisation en mémoire&#41;](../../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)   
 [Problèmes de migration pour les procédures stockées compilées en mode natif](../../relational-databases/in-memory-oltp/migration-issues-for-natively-compiled-stored-procedures.md)   
 [Fonctionnalités SQL Server non prises en charge pour l’OLTP en mémoire](../../relational-databases/in-memory-oltp/unsupported-sql-server-features-for-in-memory-oltp.md)   
 [Procédures stockées compilées en mode natif](../../relational-databases/in-memory-oltp/natively-compiled-stored-procedures.md)  
  
  
