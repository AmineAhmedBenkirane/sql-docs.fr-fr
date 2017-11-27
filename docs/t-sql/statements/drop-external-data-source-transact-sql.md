---
title: "SUPPRIMER la SOURCE de données externe (Transact-SQL) | Documents Microsoft"
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.prod_service: sql-data-warehouse, pdw, sql-database
ms.service: 
ms.component: t-sql|statements
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: TSQL
ms.assetid: 3f65a2f5-a6c6-4be5-8ca4-6057078fe10e
caps.latest.revision: "14"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 79562a0e736758c8ce3c54954e82459510b0b7d2
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="drop-external-data-source-transact-sql"></a>SUPPRIMER la SOURCE de données externe (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2016-xxxx-asdw-pdw-md.md)]

  Supprime une source de données externe PolyBase.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
-- Drop an external data source  
DROP EXTERNAL DATA SOURCE external_data_source_name  
[;]  
```  
  
## <a name="arguments"></a>Arguments  
 *external_data_source_name*  
 Le nom de la source de données externes à supprimer.  
  
## <a name="metadata"></a>Métadonnées  
 Pour afficher une liste de données externes sources utilisent la vue système sys.external_data_sources.  
  
```  
SELECT * FROM sys.external_data_sources;  
```  
  
## <a name="permissions"></a>Permissions  
 Requiert modifier n’importe quelle SOURCE de données externe.  
  
## <a name="locking"></a>Verrouillage  
 Acquiert un verrou partagé sur l’objet de source de données externe.  
  
## <a name="general-remarks"></a>Remarques d'ordre général  
 Suppression d’une source de données ne supprime pas les données externes.  
  
## <a name="examples"></a>Exemples  
  
### <a name="a-using-basic-syntax"></a>A. À l’aide de la syntaxe de base  
  
```  
DROP EXTERNAL DATA SOURCE mydatasource;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [CREATE EXTERNAL DATA SOURCE &#40;Transact-SQL&#41;](../../t-sql/statements/create-external-data-source-transact-sql.md)  
  
  

