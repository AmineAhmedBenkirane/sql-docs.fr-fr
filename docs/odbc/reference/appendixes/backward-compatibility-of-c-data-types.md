---
title: Compatibilité descendante des Types de données C | Documents Microsoft
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
- backward compatibility [ODBC], C data types
- compatibility [ODBC], C data types
- data types [ODBC], backward compatibility
- C data types [ODBC], backward compatibility
ms.assetid: b1453a65-ae03-4061-b0cf-a8434d8bc40b
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 1b4a4e8679596c1b2bca9aed13ff548373a7450f
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="backward-compatibility-of-c-data-types"></a>Compatibilité descendante des Types de données C
SQL_C_SHORT, SQL_C_LONG et SQL_C_TINYINT ont été remplacés dans ODBC en types signés et non signés : SQL_C_SSHORT et SQL_C_USHORT, SQL_C_SLONG et SQL_C_ULONG et SQL_C_STINYINT et SQL_C_UTINYINT. Un ODBC 3*.x* pilote doit fonctionner avec ODBC 2. *x* applications doivent prendre en charge SQL_C_SHORT, SQL_C_LONG et SQL_C_TINYINT, étant donné que lorsqu’elles sont appelées, le Gestionnaire de pilotes transmet via le pilote.
