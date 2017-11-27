---
title: "À l’aide des Applications 32 bits avec les pilotes 32 bits | Documents Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: microsoft
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ODBC drivers [ODBC], 32-bit applications
- 32-bit applications with 32-bit drivers [ODBC]
ms.assetid: 0cdd5788-5642-4280-8d53-b4ec461aafa1
caps.latest.revision: "13"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: b04226eeab2adde4a36f93fb5630f3097741a6d6
ms.sourcegitcommit: 7f8aebc72e7d0c8cff3990865c9f1316996a67d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2017
---
# <a name="using-32-bit-applications-with-32-bit-drivers"></a>À l’aide des Applications 32 bits avec les pilotes 32 bits
Vous pouvez exécuter des applications 32 bits avec les pilotes 32 bits. Les applications 32 bits et les pilotes 32 bits utilisent l’API Win32®.  
  
## <a name="architecture"></a>Architecture  
 L’illustration suivante montre comment aux applications 32 bits communiquent avec les pilotes 32 bits. L’application appelle le Gestionnaire de pilotes 32 bits, qui appelle à son tour les pilotes 32 bits.  
  
 ![Comment 32 &#45; applications bits communiquent avec les 32 &#45; bit pilotes](../../odbc/microsoft/media/sdka6.gif "sdka6")  
  
> [!IMPORTANT]  
>  N’utilisez pas le programme d’installation 32 bits thunking DLL sous Windows NT/Windows 2000. Bien qu’il ait le même nom de fichier que le programme d’installation 32 bits DLL, il est une autre DLL.  
  
## <a name="administration"></a>Administration  
 Vous pouvez gérer les sources de données pour les pilotes 32 bits à l’aide de l’administrateur de Source de données ODBC. Pour ouvrir l’administrateur ODBC sur des ordinateurs exécutant Windows 2000, ouvrez le panneau de configuration Windows, double-cliquez sur **outils d’administration**, puis double-cliquez sur **des Sources de données (ODBC)**. Sur les ordinateurs exécutant des versions antérieures de Microsoft Windows, l’icône est nommé **ODBC 32 bits** ou simplement **ODBC**.  
  
## <a name="components"></a>Components  
 Le composant ODBC inclut les fichiers suivants pour exécuter des applications 32 bits avec les pilotes 32 bits. Ces composants sont dans le répertoire \Redist.  
  
|Nom de fichier| Description|  
|---------------|-----------------|  
|ODBC32.dll|Gestionnaire de pilotes 32 bits|  
|Odbccp32.dll|programme d’installation 32 bits DLL|  
|Odbcad32.exe|programme de l’administrateur ODBC 32 bits|  
|ODBCINST.hlp|Fichier d’aide du programme d’installation|  
|Msvcrt40.dll|Bibliothèque C run-time|
