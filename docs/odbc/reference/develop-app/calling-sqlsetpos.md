---
title: "L’appel de SQLSetPos | Documents Microsoft"
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
- SQLSetPos function [ODBC], calling
- upgrading applications [ODBC], SQLSetPos
- backward compatibility [ODBC], SqlSetPos
- application upgrades [ODBC], SQLSetPos
ms.assetid: 846354b8-966c-4c2c-b32f-b0c8e649cedd
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 434031a496faae19ee37b8273341cc0ede6d0313
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="calling-sqlsetpos"></a>L’appel de SQLSetPos
Dans ODBC 2. *x*, le pointeur vers le tableau d’état de ligne a été l’argument de **SQLExtendedFetch**. Le tableau d’état de ligne a été suite mis à jour par un appel à **SQLSetPos**. Certains pilotes reposait sur le fait que ce tableau ne changeant pas entre **SQLExtendedFetch** et **SQLSetPos**. Dans ODBC 3. *x*, le pointeur vers le tableau d’état est un champ de descripteur et par conséquent, l’application peut facilement le modifier pour pointer vers un tableau différent. Cela peut poser un problème lorsqu’un ODBC 3. *x* application fonctionne avec une API ODBC 2.* x* pilote mais appelle **SQLSetStmtAttr** pour définir le pointeur d’état du tableau et appelle **SQLFetchScroll** pour extraire des données. Le Gestionnaire de pilotes est mappé comme une séquence d’appels à **SQLExtendedFetch**. Dans le code suivant, une erreur normalement est déclenchée lorsque le Gestionnaire de pilotes mappe le deuxième **SQLSetStmtAttr** appel lorsque vous travaillez avec une API ODBC 2*.x* pilote :  
  
```  
SQLSetStmtAttr(hstmt, SQL_ATTR_ROW_STATUS_PTR, rgfRowStatus, 0);  
SQLFetchScroll(hstmt, fFetchType, iRow);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ROW_STATUS_PTR, rgfRowStat1, 0);  
SQLSetPos(hstmt, iRow, fOption, fLock);  
```  
  
 L’erreur est générée s’il n’y a aucun moyen de modifier le pointeur d’état de ligne d’ODBC 2. *x* entre les appels à **SQLExtendedFetch**. Au lieu de cela, le Gestionnaire de pilotes effectue les étapes suivantes lorsque vous travaillez avec une API ODBC 2*.x* pilote :  
  
1.  Initialise un indicateur de gestionnaire de pilotes interne *fSetPosError* sur TRUE.  
  
2.  Lorsqu’une application appelle **SQLFetchScroll**, le Gestionnaire de pilotes définit *fSetPosError* sur FALSE.  
  
3.  Lorsque l’application appelle **SQLSetStmtAttr** pour définir SQL_ATTR_ROW_STATUS_PTR, définit le Gestionnaire de pilotes *fSetPosError* toTRUE égale.  
  
4.  Lorsque l’application appelle **SQLSetPos**, avec *fSetPosError* égale à TRUE, le Gestionnaire de pilotes déclenche SQL_ERROR avec SQLSTATE HY011 (attribut ne peut pas être défini maintenant) pour indiquer que l’application a tenté d’appeler **SQLSetPos** après avoir modifié le pointeur d’état de ligne, mais avant d’appeler **SQLFetchScroll**.

