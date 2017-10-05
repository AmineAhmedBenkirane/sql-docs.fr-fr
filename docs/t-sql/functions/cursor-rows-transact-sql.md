---
title: '@@CURSOR_ROWS (Transact-SQL) | Documents Microsoft'
ms.custom: 
ms.date: 08/18/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '@@CURSOR_ROWS'
- '@@CURSOR_ROWS_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- '@@CURSOR_ROWS function'
- cursors [SQL Server], last-opened
- last-opened cursor
- asynchronous cursors [SQL Server]
ms.assetid: 31bd7a97-7f28-42a8-ba24-24d16d22973d
caps.latest.revision: 36
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: c6ea46c5187f00190cb39ba9a502b3ecb6a28bc6
ms.openlocfilehash: 10a3a6cabae8d25de670cbacb037a62f4c5a2d54
ms.contentlocale: fr-fr
ms.lasthandoff: 09/19/2017

---
# <a name="x40x40cursorrows-transact-sql"></a>& #x 40 ; & #x 40 ; CURSOR_ROWS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Retourne le nombre de lignes éligibles se trouvant actuellement dans le dernier curseur ouvert sur la connexion. Afin d'améliorer les performances, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut charger de grands curseurs pilotés par jeux de clés et curseurs statiques de manière asynchrone. @@CURSOR_ROWS peut être appelée pour déterminer que le nombre de lignes qui se qualifient pour un curseur est récupéré en temps @@CURSOR_ROWS est appelée.
  
![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntaxe  
  
```
@@CURSOR_ROWS  
```  
  
## <a name="return-types"></a>Types de retour
**entier**
  
## <a name="return-value"></a>Valeur retournée  
  
|Valeur retournée| Description|  
|---|---|
|-*m*|Le curseur est rempli de façon asynchrone. La valeur retournée (-*m*) est le nombre de lignes figurant actuellement dans le jeu de clés.|  
|-1|Le curseur est dynamique. Puisque les curseurs dynamiques reflètent toutes les modifications, le nombre de lignes qui se qualifient pour le curseur varie constamment. On ne peut jamais affirmer définitivement que toutes les lignes qualifiées ont été extraites.|  
|0|Aucun curseur n'a été ouvert, aucune ligne n'a été qualifiée pour le dernier curseur ouvert ou le dernier curseur ouvert est fermé ou désalloué.|  
|*n*|Le curseur est totalement rempli. La valeur retournée (*n*) est le nombre total de lignes dans le curseur.|  
  
## <a name="remarks"></a>Notes  
Le nombre retourné par@CURSOR_ROWS est un nombre négatif si le dernier curseur a été ouvert de façon asynchrone. Keyset ou les curseurs statiques sont ouverts de façon asynchrone si la valeur de sp_configure cursor threshold est supérieure à 0 et le nombre de lignes dans le jeu de résultats du curseur est supérieur au seuil du curseur.
  
## <a name="examples"></a>Exemples  
L'exemple suivant déclare un curseur et utilise `SELECT` pour afficher la valeur de `@@CURSOR_ROWS`. La valeur du paramètre est `0` avant l'ouverture du curseur, et `-1` pour indiquer que le jeu de clés du curseur est rempli de façon asynchrone.
  
```sql
USE AdventureWorks2012;  
GO  
SELECT @@CURSOR_ROWS;  
DECLARE Name_Cursor CURSOR FOR  
SELECT LastName ,@@CURSOR_ROWS FROM Person.Person;  
OPEN Name_Cursor;  
FETCH NEXT FROM Name_Cursor;  
SELECT @@CURSOR_ROWS;  
CLOSE Name_Cursor;  
DEALLOCATE Name_Cursor;  
GO             
```  
  
Voici les jeux de résultats obtenus.
  
```
-----------
0  
```

```
LastName
---------------
Sanchez
```

```
-----------
-1
```  
  
## <a name="see-also"></a>Voir aussi
[Fonctions de curseur &#40; Transact-SQL &#41;](../../t-sql/functions/cursor-functions-transact-sql.md)  
[Ouvrir &#40; Transact-SQL &#41;](../../t-sql/language-elements/open-transact-sql.md)
  
  

