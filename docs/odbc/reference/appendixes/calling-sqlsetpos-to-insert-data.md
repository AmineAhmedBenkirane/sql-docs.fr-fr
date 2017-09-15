---
title: "L’appel de SQLSetPos pour insérer des données | Documents Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- compatibility [ODBC], SQLSetPos
- SQLSetPos function [ODBC], inserting data
- backward compatibility [ODBC], SqlSetPos
ms.assetid: 03e5c4d0-2bb3-4649-9781-89cab73f78eb
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: e9d768ea5c16b199dc316726cb425b75d409bf1f
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="calling-sqlsetpos-to-insert-data"></a>L’appel de SQLSetPos pour insérer des données
Lorsqu’une application ODBC 2. *x* application utilisant une ODBC 3*.x* pilote appelle **SQLSetPos** avec un *opération* argument de SQL_ADD, le Gestionnaire de pilotes n’est pas mappé cet appel à **SQLBulkOperations**. Si un ODBC 3*.x* pilote doit fonctionner avec une application qui appelle **SQLSetPos** avec SQL_ADD, le pilote doit prendre en charge cette opération.  
  
 Une différence majeure dans le comportement lorsque **SQLSetPos** est appelée avec SQL_ADD se produit lorsqu’elle est appelée dans un état S6. Dans ODBC 2. *x*, le pilote a renvoyé S1010 lorsque **SQLSetPos** a été appelée avec SQL_ADD état S6 (une fois que le curseur a été positionné avec **SQLFetch**). Dans ODBC 3*.x*, **SQLBulkOperations** avec un *opération* de SQL_ADD peut être appelée dans un état S6. Une deuxième différence de comportement est que **SQLBulkOperations** avec un *opération* de SQL_ADD peut être appelée dans un état S5, tandis que **SQLSetPos** avec un **opération** de SQL_ADD ne peut pas. Pour les transitions de l’instruction qui peuvent se produire pour le même appel dans ODBC 3*.x*, consultez [Tables de Transition d’état annexe b : ODBC](../../../odbc/reference/appendixes/appendix-b-odbc-state-transition-tables.md).
