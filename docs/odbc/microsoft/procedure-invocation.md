---
title: "Appel de procédure | Documents Microsoft"
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
- SQL grammar [ODBC], procedure invocation
- procedure invocation [ODBC]
ms.assetid: b9ff2c3a-2003-4832-adbe-08dd0f5ad948
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: fd42836285c29e36e6bb64ebe594df570876ff6e
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="procedure-invocation"></a>Appel de procédure
Lorsque le pilote Microsoft Access est utilisé, les procédures peuvent être appelées à partir du pilote à l’aide de la **SQLExecDirect** ou **SQLPrepare** fonction avec la syntaxe suivante : {appeler *-nom de la procédure* [(*paramètre*[,*paramètre*]...)]}. Notez que les expressions ne sont pas prises en charge en tant que paramètres à une procédure appelée.  
  
 Si un nom de procédure comprend un tiret, le nom doit être délimité avec guillemets précédent (').  
  
 Une requête paramétrable peut être appelée à l’aide de l’instruction précédente.

