---
title: Mappage de SQLFreeConnect | Documents Microsoft
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: odbc
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- mapping deprecated functions [ODBC], SQLFreeConnect
- SQLFreeConnect function [ODBC], mapping
ms.assetid: 8a844538-93c0-4709-bab6-35c45e771d80
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 5e22a01271bab030fa0036bb5669a2bf7ef15c00
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="sqlfreeconnect-mapping"></a>Mappage de SQLFreeConnect
Lorsqu’une application appelle **SQLFreeConnect** via un ODBC 3*.x* pilote, l’appel à  
  
```  
SQLFreeConnect(hdbc)   
```  
  
 est mappée à  
  
```  
SQLFreeHandle(SQL_HANDLE_DBC,Handle)  
```  
  
 avec la *gérer* affectée à la valeur de l’argument *pas*.
