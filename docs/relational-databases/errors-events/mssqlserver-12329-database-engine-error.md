---
title: MSSQLSERVER_12329 | Microsoft Docs
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords:
- 12329 (Database Engine error)
ms.assetid: 43f90287-36d5-46c2-ac91-a37202dcf6d3
caps.latest.revision: 4
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 47b2380fdb3bf5fbde95bfbd984c3ed6095dcd1f
ms.lasthandoff: 04/11/2017

---
# <a name="mssqlserver12329"></a>MSSQLSERVER_12329
  
## <a name="details"></a>Détails  
  
|||  
|-|-|  
|Nom du produit|SQL Server|  
|ID d'événement|12329|  
|Source de l'événement|MSSQLSERVER|  
|Composant|SQLEngine|  
|Nom symbolique|HK_UNSUPPORTED_NON_LATIN_CODEPAGE|  
|Texte du message|Les types de données char(n) et varchar(n) qui utilisent un classement avec une page de codes différente de 1252 ne sont pas pris en charge par *construction*.|  
  
## <a name="explanation"></a>Explication  
N'utilisez pas les types de données char(n) et varchar(n) qui utilisent un classement avec une page de codes différente de 1252.  
  
## <a name="user-action"></a>Action de l'utilisateur  
Une situation inattendue pouvant générer cette erreur est :  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = 'us_english')  
```  
  
Utilisez ceci à la place :  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
```  
  

