---
title: SQLDriverConnect (dBASE Driver) | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: odbc
ms.reviewer: 
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DBase driver [ODBC], SQLDriverConnect
- SQLDriverConnect function [ODBC], dBASE Driver
ms.assetid: c837aa31-068e-4fa3-bc00-aae09bec21de
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 59ffc1188c1d98dc5697a65f69ab8792145f1ea3
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2018
---
# <a name="sqldriverconnect-dbase-driver"></a>SQLDriverConnect (dBASE Driver)
> [!NOTE]  
>  Cette rubrique fournit des informations spécifiques au pilote de dBASE. Pour obtenir des informations générales sur cette fonction, consultez la rubrique appropriée sous [référence de l’API ODBC](../../odbc/reference/syntax/odbc-api-reference.md).  
  
 **SQLDriverConnect** vous permet de se connecter à un pilote sans création d’une source de données (DSN).  
  
 Les mots clés suivants sont pris en charge dans la chaîne de connexion pour tous les pilotes : **DSN**, **DBQ**, et **FIL**.  
  
 Lorsque le pilote Paradox est utilisé, une fois un fichier protégé par mot de passe a été ouvert par un utilisateur, les autres utilisateurs ne sont pas autorisés à ouvrir le même fichier.  
  
 Le tableau suivant montre les mots clés minimales requises pour se connecter à chaque pilote et fournit un exemple de paires mot clé/valeur utilisées avec **SQLDriverConnect**. Pour obtenir une liste complète des valeurs DRIVERID, consultez [SQLConfigDataSource](../../odbc/microsoft/sqlconfigdatasource-dbase-driver.md).  
  
> [!NOTE]  
>  Si DBQ ou DefaultDir n’est pas spécifié pour le dBASEdriver, le pilote se connecte au répertoire actif.  
  
|Pilote|Mots clés requis|Exemples|  
|------------|-----------------------|--------------|  
|dBASE|Driver, DriverID|Driver={Microsoft dBASE Driver (*.dbf)}; DBQ=c:\temp; DriverID=277|
