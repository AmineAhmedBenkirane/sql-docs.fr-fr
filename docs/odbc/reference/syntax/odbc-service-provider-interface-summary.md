---
title: "Résumé de Interface du fournisseur de Service ODBC | Documents Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ace6085b-355b-435b-8734-503fc3c12ec2
caps.latest.revision: 4
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 82610a48532970f14800574155db89929e371baf
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="odbc-service-provider-interface-summary"></a>Résumé de Interface du fournisseur de Service ODBC
Le tableau suivant décrit les fonctions d’interface de fournisseur de Service ODBC. Pour plus d’informations sur la syntaxe et la sémantique pour chaque fonction, consultez [référence de l’Interface de fournisseur de Service ODBC (SPI)](../../../odbc/reference/syntax/odbc-service-provider-interface-spi-reference.md).  
  
|Nom de la fonction|Fonction|  
|-------------------|-------------|  
|[SQLSetConnectAttrForDbcInfo](../../../odbc/reference/syntax/sqldatasourcetodriver-function.md)|Identique à [SQLSetConnectAttr](../../../odbc/reference/syntax/sqlsetconnectattr-function.md), mais il définit l’attribut sur le jeton d’informations de connexion à la place de sur le handle de connexion.|  
|[SQLSetDriverConnectInfo](../../../odbc/reference/syntax/sqldrivertodatasource-function.md)|Définit la chaîne de connexion dans le jeton d’informations de connexion pour une application [SQLDriverConnect](../../../odbc/reference/syntax/sqldriverconnect-function.md) appeler.|  
|[SQLSetConnectInfo](../../../odbc/reference/syntax/sqldatasourcetodriver-function.md)|Définit la source de données, un ID d’utilisateur et un mot de passe dans le jeton d’informations de connexion pour une application [SQLConnect](../../../odbc/reference/syntax/sqlconnect-function.md) appeler.|  
|[SQLGetPoolID](../../../odbc/reference/syntax/sqldatasourcetodriver-function.md)|Récupère l’ID de pool.|  
|[SQLRateConnection](../../../odbc/reference/syntax/sqldatasourcetodriver-function.md)|Détermine si un pilote peut réutiliser une connexion existante dans le pool de connexions.|  
|[SQLPoolConnect](../../../odbc/reference/syntax/sqldatasourcetodriver-function.md)|Créer une nouvelle connexion si aucune connexion dans le pool ne peut être réutilisée.|  
|[SQLCleanupConnectionPoolID](../../../odbc/reference/syntax/sqldatasourcetodriver-function.md)|Informe un pilote qui a un ID du pool a été dépassé.|
