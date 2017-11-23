---
title: "Par défaut du pilote sous-clé | Documents Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: reference
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- default subkey [ODBC]
- registry entries for components [ODBC], default subkey
- subkeys [ODBC], default subkey
- drivers subkey [ODBC]
ms.assetid: 9e58b24f-ebfc-4286-a272-0843b4d6f2d5
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 6abe4c5b5b07ea59b18c1bd298225ca33db2a65b
ms.sourcegitcommit: 7f8aebc72e7d0c8cff3990865c9f1316996a67d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2017
---
# <a name="default-driver-subkey"></a>Sous-clé du pilote par défaut
La sous-clé par défaut contient une valeur unique qui décrit le pilote utilisé par la source de données par défaut. Le format de cette valeur est illustré dans le tableau suivant.  
  
|Nom|Type de données|data|  
|----------|---------------|----------|  
|**Pilote**|REG_SZ|*description du pilote par défaut*|  
  
 Le *description du pilote par défaut* nom est le même que le nom de la valeur sous la sous-clé de pilotes ODBC qui décrit le pilote.  
  
 Par exemple, si la source de données par défaut utilise le pilote SQL Server, la valeur sous la sous-clé par défaut peut être :  
  
```  
Driver : REG_SZ : SQL Server  
```  
  
> [!NOTE]  
>  Le pilote par défaut contenu dans la sous-clé par défaut peut faire référence à un utilisateur par défaut DSN ou à un source de données du système par défaut. Si un utilisateur par défaut (DSN) et un système par défaut DSN a été créée, le pilote par défaut est déterminé par la source de données qui a été créée, elle peut donc pas être une entrée valide pour la source de données qui a été créé en premier.
