---
title: TRIM (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 01/20/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TRIM
- TRIM_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- TRIM function
ms.assetid: a00245aa-32c7-4ad4-a0d1-64f3d6841153
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Active
ms.openlocfilehash: 88ba00513a8f76ae560ed717801150aa9b80046e
ms.sourcegitcommit: 6b4aae3706247ce9b311682774b13ac067f60a79
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/18/2018
---
# <a name="trim-transact-sql"></a>TRIM (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2017-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2017-asdb-xxxx-xxx-md.md)]

Supprime le caractère espace `char(32)` ou d’autres caractères spécifiés à partir du début ou la fin d’une chaîne.  
 
## <a name="syntax"></a>Syntaxe   
```
TRIM ( [ characters FROM ] string ) 
```
[//]: # "[LES DEUX | DÉBUT | FIN] ne pas encore disponible."

## <a name="arguments"></a>Arguments   

caractères   
Est un littéral, une variable ou un appel de fonction de n’importe quel type de caractère de non LOB (`nvarchar`, `varchar`, `nchar`, ou `char`) contenant des caractères qui doivent être supprimés. `nvarchar(max)`et `varchar(max)` les types ne sont pas autorisés.

chaîne   
Est une expression de n’importe quel type de caractère (`nvarchar`, `varchar`, `nchar`, ou `char`) où les caractères doivent être supprimés.

## <a name="return-types"></a>Types de retour   
Retourne une expression de caractères avec un type d’argument de chaîne dans laquelle le caractère espace `char(32)` ou autres caractères spécifiées sont supprimés des deux côtés. Retourne `NULL` si la chaîne d’entrée est `NULL`.

## <a name="remarks"></a>Notes   
Par défaut `TRIM` fonction supprime le caractère espace `char(32)` des deux côtés. Ceci équivaut à `LTRIM(RTRIM(@string))`. Comportement de `TRIM ` fonction avec des caractères spécifiés est identique au comportement de `REPLACE` fonction où les caractères de début ou de fin sont remplacées par des chaînes vides.


## <a name="examples"></a>Exemples
### <a name="a--removes-the-space-character-from-both-sides-of-string"></a>A.  Supprime l’espace des deux côtés de la chaîne   
L’exemple suivant supprime les espaces avant et après le mot `test`.   
```sql
SELECT TRIM( '     test    ') AS Result;
```

[!INCLUDE[ssResult_md](../../includes/ssresult-md.md)]   

`test`


### <a name="b--removes-specified-characters-from-both-sides-of-string"></a>B.  Supprime caractères spécifiés dans les deux côtés de la chaîne   
L’exemple suivant supprime un point final et les espaces de fin.
```sql
SELECT TRIM( '.,! ' FROM  '#     test    .') AS Result;
```

[!INCLUDE[ssResult_md](../../includes/ssresult-md.md)]   
`#     test`


## <a name="see-also"></a>Voir aussi
 [LEFT &#40;Transact-SQL&#41;](../../t-sql/functions/left-transact-sql.md)  
 [LTRIM &#40;Transact-SQL&#41;](../../t-sql/functions/ltrim-transact-sql.md)  
 [RIGHT &#40;Transact-SQL&#41;](../../t-sql/functions/right-transact-sql.md)  
 [RTRIM &#40;Transact-SQL&#41;](../../t-sql/functions/rtrim-transact-sql.md)  
 [STRING_SPLIT &#40;Transact-SQL&#41;](../../t-sql/functions/string-split-transact-sql.md)  
 [SUBSTRING &#40;Transact-SQL&#41;](../../t-sql/functions/substring-transact-sql.md)  
 [Fonctions de chaîne &#40; Transact-SQL &#41;](../../t-sql/functions/string-functions-transact-sql.md)   
