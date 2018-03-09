---
title: Fermeture du curseur | Documents Microsoft
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: odbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- cursors [ODBC], closing
- closing cursors [ODBC]
ms.assetid: 4f19bf5e-6d8c-40ae-a975-cfd62a0790ec
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: f2d5c9b47c5e51b68712e7c30f4b2de731f328b5
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="closing-the-cursor"></a>Fermeture du curseur
Lorsqu’une application a terminé à l’aide d’un curseur, il appelle **SQLCloseCursor** pour fermer le curseur. Exemple :  
  
```  
SQLCloseCursor(hstmt);  
```  
  
 Jusqu'à ce que l’application ferme le curseur, l’instruction sur laquelle le curseur est ouvert ne peut pas être utilisée pour la plupart des autres opérations, telles que l’exécution d’une autre instruction SQL. Pour obtenir une liste complète des fonctions qui peut être appelée lorsqu’un curseur est ouvert, consultez [Tables de Transition d’état annexe b : ODBC](../../../odbc/reference/appendixes/appendix-b-odbc-state-transition-tables.md).  
  
> [!NOTE]  
>  Pour fermer un curseur, une application doit appeler **SQLCloseCursor**, et non **SQLCancel**.  
  
 Les curseurs restent ouverts jusqu'à ce qu’ils sont explicitement fermées, sauf lorsqu’une transaction est validée ou restaurée, auquel cas certaines sources de données fermer le curseur. En particulier, la fin du résultat définie, **SQLFetch** retourne SQL_NO_DATA, ne pas fermer un curseur. Même les curseurs de jeux de résultats vides (jeux de résultats créé lorsqu’une instruction exécutée avec succès, mais qui a retourné aucune ligne) doivent être fermés explicitement.
