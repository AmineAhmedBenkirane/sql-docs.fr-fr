---
title: cursor (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 7/23/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|data-types
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- cursor data type
ms.assetid: fbea16ef-f2cc-4734-9149-ec2598fd3cca
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: b9fa1c8e8fea6aabf8fe8a0e6e84f82f7220facf
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="cursor-transact-sql"></a>cursor (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Type de données pour les variables ou les paramètres OUTPUT des procédures stockées contenant une référence à un curseur.
  
## <a name="remarks"></a>Notes   
Les opérations suivantes peuvent référencer des variables et des paramètres ayant un type de données **cursor** :
-   les instructions DECLARE *@local_variable* et SET *@local_variable* ;  
-   les instructions de curseur OPEN, FETCH, CLOSE et DEALLOCATE ;  
-   les paramètres de sortie des procédures stockées ;  
-   la fonction CURSOR_STATUS ;  
-   les procédures stockées système **sp_cursor_list**, **sp_describe_cursor**, **sp_describe_cursor_tables** et **sp_describe_cursor_columns**.  
  
La colonne de sortie **cursor_name** de **sp_cursor_list** et **sp_describe_cursor** retourne le nom de la variable de curseur.
  
Toutes les variables créées avec le type de données **cursor** acceptent la valeur Null.
  
Il n’est pas possible d’utiliser le type de données **cursor** dans une colonne d’une instruction CREATE TABLE.
  
## <a name="see-also"></a>Voir aussi
[CAST et CONVERT &#40;Transact-SQL&#41;](../../t-sql/functions/cast-and-convert-transact-sql.md)  
[CURSOR_STATUS &#40;Transact-SQL&#41;](../../t-sql/functions/cursor-status-transact-sql.md)  
[Conversion de type de données &#40;moteur de base de données&#41;](../../t-sql/data-types/data-type-conversion-database-engine.md)  
[Types de données &#40;Transact-SQL&#41;](../../t-sql/data-types/data-types-transact-sql.md)  
[DECLARE CURSOR &#40;Transact-SQL&#41;](../../t-sql/language-elements/declare-cursor-transact-sql.md)  
[DECLARE @local_variable &#40;Transact-SQL&#41;](../../t-sql/language-elements/declare-local-variable-transact-sql.md)  
[SET @local_variable &#40;Transact-SQL&#41;](../../t-sql/language-elements/set-local-variable-transact-sql.md)
  
  
