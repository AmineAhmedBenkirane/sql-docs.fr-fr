---
title: SCHEMA_ID (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SCHEMA_ID
- SCHEMA_ID_TSQL
dev_langs: TSQL
helpviewer_keywords:
- identification numbers [SQL Server], schemas
- schemas [SQL Server], IDs
- SCHEMA_ID function
- IDs [SQL Server], schemas
- default schema IDs
ms.assetid: c8e34df5-3eea-459f-ae40-050909ce9fda
caps.latest.revision: "39"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 8ff63abb8b74497b05045a2892067d7b4e49140a
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="schemaid-transact-sql"></a>SCHEMA_ID (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Renvoie l'ID d'un schéma associé à un nom de schéma.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
SCHEMA_ID ( [ schema_name ] )   
```  
  
## <a name="arguments"></a>Arguments  
  
|Terme|Définition|  
|----------|----------------|  
|*schema_name*|Nom du schéma. *schema_name* est un **sysname**. Si *nom_schéma* n’est pas spécifié, SCHEMA_ID renvoie l’ID du schéma par défaut de l’appelant.|  
  
## <a name="return-types"></a>Types de retour  
 **int**  
  
 Valeur NULL est renvoyée si *nom_schéma* n’est pas un schéma valide.  
  
## <a name="remarks"></a>Notes  
 SCHEMA_ID renvoie les ID des schémas système et des schémas définis par l'utilisateur. SCHEMA_ID peut être appelé dans une liste de sélection, dans une clause WHERE et partout où une expression est autorisée.  
  
## <a name="examples"></a>Exemples  
  
### <a name="a-returning-the-default-schema-id-of-a-caller"></a>A. Renvoi de l'ID du schéma par défaut d'un appelant  
  
```  
SELECT SCHEMA_ID();  
```  
  
### <a name="b-returning-the-schema-id-of-a-named-schema"></a>B. Renvoi de l'ID d'un schéma nommé  
  
```  
SELECT SCHEMA_ID('dbo');  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions de métadonnées &#40; Transact-SQL &#41;](../../t-sql/functions/metadata-functions-transact-sql.md)   
 [Schema_name &#40; Transact-SQL &#41;](../../t-sql/functions/schema-name-transact-sql.md)   
 [Sys.Schemas &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/schemas-catalog-views-sys-schemas.md)  
  
  

