---
title: "Obtention de descripteur gère | Documents Microsoft"
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
helpviewer_keywords: descriptors [ODBC], retrieving or setting field values
ms.assetid: 936f983f-c7e9-43f3-97ea-dd4b1bbf4654
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 921d3e9bc76ff49b35b58d3b519a4adcc227d241
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="obtaining-descriptor-handles"></a>Obtention de descripteur gère
Une application obtient le handle du descripteur de n’importe quel explicitement alloué comme un argument de sortie de l’appel à **SQLAllocHandle**. Le handle d’un descripteur implicitement alloué est obtenu en appelant **SQLGetStmtAttr**.
