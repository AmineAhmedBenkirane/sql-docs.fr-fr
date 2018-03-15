---
title: CHECKSUM_AGG (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/24/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- CHECKSUM_AGG
- CHECKSUM_AGG_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- checksum values
- CHECKSUM_AGG function
- groups [SQL Server], checksum values
ms.assetid: cdede70c-4eb5-4c92-98ab-b07787ab7222
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 3499cd8fb118d12fdbf450c23f2919fd0003cee7
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="checksumagg-transact-sql"></a>CHECKSUM_AGG (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Renvoie la somme de contrôle des valeurs d'un groupe. Les valeurs NULL sont ignorées. Cette fonction peut être suivie par la [clause OVER](../../t-sql/queries/select-over-clause-transact-sql.md).
  
![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntaxe  
  
```sql
CHECKSUM_AGG ( [ ALL | DISTINCT ] expression )  
```  
  
## <a name="arguments"></a>Arguments  
**ALL**  
Applique la fonction d'agrégation à toutes les valeurs. ALL est l'argument par défaut.
  
DISTINCT  
Spécifie que CHECKSUM_AGG renvoie la somme de contrôle de valeurs uniques.
  
*expression*  
[Expression](../../t-sql/language-elements/expressions-transact-sql.md) entière. Les fonctions d'agrégation et les sous-requêtes ne sont pas autorisées.
  
## <a name="return-types"></a>Types de retour
Renvoie la somme de contrôle de toutes les valeurs d’*expression* en tant que **int**.
  
## <a name="remarks"></a>Notes   
CHECKSUM_AGG peut être utilisé pour détecter les modifications effectuées dans une table.
  
L'ordre des lignes dans la table n'influe pas sur le résultat de CHECKSUM_AGG. Les fonctions CHECKSUM_AGG peuvent être également utilisées avec le mot clé DISTINCT et la clause GROUP BY.
  
Si l'une des valeurs de la liste d'expressions change, en général, la somme de contrôle de la liste change également. Il existe toutefois une faible probabilité pour que la somme de contrôle ne change pas.
  
CHECKSUM_AGG a des fonctionnalités similaires à celles des autres fonctions d'agrégation. Pour plus d’informations, consultez les [fonctions d’agrégation &#40;Transact-SQL&#41;](../../t-sql/functions/aggregate-functions-transact-sql.md).
  
## <a name="examples"></a>Exemples  
L'exemple suivant utilise `CHECKSUM_AGG` pour détecter des modifications dans la colonne `Quantity` de la table `ProductInventory` de la base de données [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].
  
```sql
--Get the checksum value before the column value is changed.  
SELECT CHECKSUM_AGG(CAST(Quantity AS int))  
FROM Production.ProductInventory;  
GO  
```  
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]
  
```sql
------------------------  
262  
```  
  
```sql
UPDATE Production.ProductInventory   
SET Quantity=125  
WHERE Quantity=100;  
GO  
--Get the checksum of the modified column.  
SELECT CHECKSUM_AGG(CAST(Quantity AS int))  
FROM Production.ProductInventory;  
```  
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]
  
```sql
------------------------  
287  
```  
  
## <a name="see-also"></a>Voir aussi
[CHECKSUM &#40;Transact-SQL&#41;](../../t-sql/functions/checksum-transact-sql.md)  
[OVER, clause &#40;Transact-SQL&#41;](../../t-sql/queries/select-over-clause-transact-sql.md)
  
  
