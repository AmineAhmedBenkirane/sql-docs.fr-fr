---
title: MSSQLSERVER_12329 | Microsoft Docs
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords: 12329 (Database Engine error)
ms.assetid: 43f90287-36d5-46c2-ac91-a37202dcf6d3
caps.latest.revision: "4"
author: edmacauley
ms.author: edmaca
manager: cguyer
ms.workload: Inactive
ms.openlocfilehash: 772e884f81d682f72eb919db72f7a38330a89f60
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
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
  
