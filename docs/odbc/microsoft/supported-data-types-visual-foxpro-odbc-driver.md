---
title: "Prise en charge des Types de données (le pilote ODBC Visual FoxPro) | Documents Microsoft"
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
- Visual FoxPro ODBC driver [ODBC], data types
- FoxPro ODBC driver [ODBC], data types
- data types [ODBC], Visual FoxPro ODBC driver
ms.assetid: ab529cc6-d157-4b35-b6f9-6ffd09af098c
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 6e80a4f6f079620e4a5a3ee82d87342e87591001
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="supported-data-types-visual-foxpro-odbc-driver"></a>Types de données pris en charge (le pilote ODBC Visual FoxPro)
La liste des types de données pris en charge par le pilote sont présentées via l’API ODBC et dans Microsoft Query.  
  
## <a name="data-types-in-c-applications"></a>Types de données dans les Applications C  
 Vous pouvez obtenir une liste des types de données pris en charge par le pilote ODBC Visual FoxPro à l’aide de la [SQLGetTypeInfo](../../odbc/microsoft/sqlgettypeinfo-visual-foxpro-odbc-driver.md) fonction dans les applications C ou C++.  
  
## <a name="data-types-in-applications-using-microsoft-query"></a>Types de données dans les Applications à l’aide de Microsoft Query  
 Si votre application utilise Microsoft Query pour créer une nouvelle table sur une source de données Visual FoxPro, Microsoft Query affiche le **nouvelle définition de la Table** boîte de dialogue. Sous **champ Description**, le **Type** zone listes [types de données Visual FoxPro](../../odbc/microsoft/visual-foxpro-field-data-types.md), représenté par les caractères uniques.
