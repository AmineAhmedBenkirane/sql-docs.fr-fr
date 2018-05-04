---
title: SQLPrepare (le pilote ODBC Visual FoxPro) | Documents Microsoft
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
ms.topic: conceptual
helpviewer_keywords:
- SQLPrepare function [ODBC], Visual FoxPro ODBC Driver
ms.assetid: 0c4cb5a4-9729-4b2e-a0c6-52027b92e8fc
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 42eabe40eb5324cf82c543525ce286dadc2a510a
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="sqlprepare-visual-foxpro-odbc-driver"></a>SQLPrepare (le pilote ODBC Visual FoxPro)
> [!NOTE]  
>  Cette rubrique contient des informations spécifiques au pilote ODBC Visual FoxPro. Pour obtenir des informations générales sur cette fonction, consultez la rubrique appropriée sous [référence de l’API ODBC](../../odbc/reference/syntax/odbc-api-reference.md).  
  
 Prise en charge : complet  
  
 Conformité d’API ODBC : Niveau principal  
  
 Prépare une instruction SQL en planifiant comment optimiser et exécutez l’instruction. L’instruction SQL est compilée pour l’exécution par [SQLExecDirect](../../odbc/microsoft/sqlexecdirect-visual-foxpro-odbc-driver.md).  
  
 Si votre table, vue ou les noms de champs contiennent des espaces, placez les noms à l’arrière-plan entre guillemets les marques ('). Par exemple, si votre base de données contient une table nommée My Table et le champ My Field, placez chaque élément de l’identificateur comme suit :  
  
```  
SELECT * FROM `My Table`.`My Field`  
```  
  
 Pour plus d’informations, consultez [SQLPrepare](../../odbc/reference/syntax/sqlprepare-function.md) dans les *de référence du programmeur ODBC*.
