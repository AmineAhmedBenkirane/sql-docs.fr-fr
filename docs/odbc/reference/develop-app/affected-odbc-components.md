---
title: Les composants ODBC | Documents Microsoft
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
- upgrading applications [ODBC], affected components
- application upgrades [ODBC], affected components
- compatibility [ODBC], affected components
- ODBC drivers [ODBC], backward compatibility
- backward compatibility [ODBC], affected components
ms.assetid: 71fa6ea4-007c-4c2b-b5af-2cec6ea79b58
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 2329ec013019ed11d63f9400014d718f55d7f217
ms.sourcegitcommit: 7f8aebc72e7d0c8cff3990865c9f1316996a67d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2017
---
# <a name="affected-odbc-components"></a>Composants ODBC affectés
Compatibilité descendante décrit comment les applications, le Gestionnaire de pilotes et les pilotes sont affectés par l’introduction d’une nouvelle version du Gestionnaire de pilotes. Cela affecte les applications et le pilote lorsqu’une ou les deux d'entre eux restent dans l’ancienne version. Il existe, par conséquent, trois types de compatibilité descendante à prendre en compte, comme indiqué dans le tableau suivant.  
  
|Type|Version de l’exploration de données|Version de l’application|Version du pilote|  
|----------|-------------------|----------------------------|-----------------------|  
|Compatibilité descendante du Gestionnaire de pilotes|3*.x*|2.*x*|2.*x*|  
|Compatibilité descendante de pilote [1]|3*.x*|2.*x*|3.*x*|  
|Compatibilité descendante des applications|3.*x*|3.*x*|2.*x*|  
  
 [1] la compatibilité descendante des pilotes est principalement présentée dans l’annexe g : pilote instructions pour la compatibilité descendante.  
  
> [!NOTE]  
>  Une application conforme aux normes, par exemple, une application qui a été écrit conformément aux normes Open Group ou ISO CLI — est garantie pour travailler avec un ODBC 3*.x* pilote par le biais du ODBC 3*.x* du Gestionnaire de pilotes. Il est supposé que la fonctionnalité à l’aide de l’application est disponible dans le pilote. Il est également supposé que l’application conforme aux normes a été compilée avec ODBC 3*.x* fichiers d’en-tête.
