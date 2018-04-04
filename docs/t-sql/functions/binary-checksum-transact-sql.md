---
title: BINARY_CHECKSUM  (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 07/24/2017
ms.prod: sql-non-specified
ms.prod_service: sql-data-warehouse, database-engine, sql-database
ms.service: ''
ms.component: t-sql|functions
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- BINARY_CHECKSUM
- BINARY_CHECKSUM_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- BINARY_CHECKSUM function
- binary [SQL Server], checksum values
ms.assetid: 07fece4d-58e3-446e-a3b5-92fe24d2d1fb
caps.latest.revision: 21
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 9ff8368877b3fb2153685554f1484b5fbbcc7c3a
ms.sourcegitcommit: 059fc64ba858ea2adaad2db39f306a8bff9649c2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/04/2018
---
# <a name="binarychecksum--transact-sql"></a>BINARY_CHECKSUM  (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-asdw-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-asdw-xxx-md.md)]

Retourne la valeur de total de contrôle binaire calculée à partir d'une ligne d'une table ou d'une liste d'expressions.
  
![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntaxe  
  
```sql
BINARY_CHECKSUM ( * | expression [ ,...n ] )   
```  
  
## <a name="arguments"></a>Arguments  
*\**  
Indique que le calcul englobe toutes les colonnes de la table. BINARY_CHECKSUM ignore les colonnes de types de données incomparables dans son calcul. Les types de données non comparables incluent **text**, **ntext**, **image**, **cursor**, **xml** et les types définis par l’utilisateur CLR (Common Language Runtime) non comparables.
  
*expression*  
[Expression](../../t-sql/language-elements/expressions-transact-sql.md) de tout type. BINARY_CHECKSUM ignore les expressions de types de données incomparables dans son calcul.

## <a name="return-types"></a>Types de retour  
 **Int**
  
## <a name="remarks"></a>Notes   
BINARY_CHECKSUM(*), calculé à partir de n'importe quelle ligne d'une table, retourne la même valeur tant que la ligne ne subit aucune modification. BINARY_CHECKSUM a les propriétés d’une fonction de hachage : lorsque BINARY_CHECKSUM est appliqué à deux listes d’expressions, la même valeur est retournée si les éléments correspondants dans les deux listes sont du même type et ont une valeur égale lorsqu’ils sont comparés à l’aide de l’opérateur d’égalité (=). Pour cette définition, les valeurs NULL d'un type spécifié sont considérées comme ayant une valeur de comparaison égale. Si l'une des valeurs de la liste d'expressions change, en général, la somme de contrôle de la liste change également. Il existe toutefois une faible probabilité pour que la somme de contrôle ne change pas. Pour cette raison, nous déconseillons d’utiliser BINARY_CHECKSUM pour vérifier si des valeurs ont changé, à moins que votre application accepte de manquer parfois une modification. Envisagez d’utiliser HashBytes à la place. Lorsqu’un algorithme de hachage MD5 est spécifié, la probabilité que HashBytes retourne le même résultat pour deux entrées différentes est beaucoup plus faible que pour BINARY_CHECKSUM.
  
BINARY_CHECKSUM peut porter sur une liste d'expressions et retourne la même valeur pour une liste spécifiée. Lorsque la fonction BINARY_CHECKSUM porte sur deux listes d'expressions, elle retourne la même valeur si les éléments correspondants des deux listes sont de type et de représentation en octets identiques. Pour cette définition, les valeurs NULL d'un type spécifié sont considérées comme utilisant la même représentation en octets.
  
Les fonctions BINARY_CHECKSUM et CHECKSUM sont similaires : elles peuvent être utilisées pour calculer une somme de contrôle dans une liste d'expressions, et l'ordre des expressions affecte la valeur résultante. L'ordre des colonnes utilisé pour BINARY_CHECKSUM(*) est celui spécifié dans la définition de la table ou de la vue, Elles incluent les colonnes calculées.
  
CHECKSUM et BINARY_CHECKSUM retournent des valeurs différentes pour les types de données de chaînes de caractères. Avec les paramètres régionaux, des chaînes dont la représentation est différente peuvent apparaître comme étant équivalentes. Les types de données de chaîne sont **char**, **varchar**, **nchar**, **nvarchar** ou **sql_variant** (si le type de base de **sql_variant** est un type de données de chaîne). Par exemple, les valeurs BINARY_CHECKSUM des chaînes « McCavity » et « Mccavity » sont différentes. Si CHECKSUM est utilisé sur un serveur qui ne distingue pas les majuscules des minuscules, les mêmes valeurs de checksum sont retournées pour ces chaînes. Les valeurs de CHECKSUM ne doivent pas être comparées à celles de BINARY_CHECKSUM.
 
BINARY_CHECKSUM prend en charge jusqu’à 8 000 caractères de type **varbinary(max)** et jusqu’à 255 caractères de type **nvarchar(max)**.
  
## <a name="examples"></a>Exemples  
L'exemple suivant utilise `BINARY_CHECKSUM` pour détecter des modifications dans une ligne d'une table.
  
```sql
USE AdventureWorks2012;  
GO  
CREATE TABLE myTable (column1 int, column2 varchar(256));  
GO  
INSERT INTO myTable VALUES (1, 'test');  
GO  
SELECT BINARY_CHECKSUM(*) from myTable;  
GO  
UPDATE myTable set column2 = 'TEST';  
GO  
SELECT BINARY_CHECKSUM(*) from myTable;  
GO  
```  
  
## <a name="see-also"></a>Voir aussi
[Fonctions d’agrégation &#40;Transact-SQL&#41;](../../t-sql/functions/aggregate-functions-transact-sql.md)  
[CHECKSUM &#40;Transact-SQL&#41;](../../t-sql/functions/checksum-transact-sql.md)  
[CHECKSUM_AGG &#40;Transact-SQL&#41;](../../t-sql/functions/checksum-agg-transact-sql.md)
  
  
