---
title: Fonction de SQLSetDriverConnectInfo | Documents Microsoft
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQLSetDriverConnectInfo function [ODBC]
ms.assetid: bfd4dfc2-fbca-4ef3-81e5-2706f2389256
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 970fec5219fed803439fc05c3f6fe56a300617f0
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="sqlsetdriverconnectinfo-function"></a>SQLSetDriverConnectInfo (fonction)
**Mise en conformité**  
 Version introduite : La mise en conformité des normes 3,81 ODBC : ODBC  
  
 **Résumé**  
 **SQLSetDriverConnectInfo** est utilisée pour définir la chaîne de connexion dans le jeton d’informations de connexion pour une application **SQLDriverConnect** appeler.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
SQLRETURN SQLSetDriverConnectInfo(  
                SQLHDBC_INFO_TOKEN   hDbcInfoToken,  
                WCHAR *              InConnectionString,  
                SQLSMALLINT          StringLength1 );  
```  
  
## <a name="arguments"></a>Arguments  
 *TokenHandle*  
 [Entrée] Descripteur du jeton.  
  
 *InConnectionString*  
 [Entrée] Une chaîne de connexion complète (consultez la syntaxe dans « Commentaires » dans [SQLDriverConnect](../../../odbc/reference/syntax/sqldriverconnect-function.md)), une chaîne de connexion partielle, ou une chaîne vide.  
  
 *StringLength1*  
 [Entrée] Longueur de **InConnectionString*, en caractères, si la chaîne est Unicode ou octets si la chaîne est ANSI ou DBCS.  
  
## <a name="returns"></a>Valeur renvoyée  
 SQL_SUCCESS, SQL_SUCCESS_WITH_INFO, SQL_ERROR ou SQL_INVALID_HANDLE.  
  
## <a name="diagnostics"></a>Diagnostics  
 Identique à [SQLDriverConnect](../../../odbc/reference/syntax/sqldriverconnect-function.md) liés à toute erreur de validation d’entrée, sauf que le Gestionnaire de pilotes utilisera un **HandleType** de SQL_HANDLE_DBC_INFO_TOKEN et un **gérer** de *hDbcInfoToken*.  
  
## <a name="remarks"></a>Notes  
 Chaque fois qu’un pilote retourne SQL_ERROR ou SQL_INVALID_HANDLE, le Gestionnaire de pilotes retourne l’erreur à l’application (dans [SQLConnect](../../../odbc/reference/syntax/sqlconnect-function.md) ou [SQLDriverConnect](../../../odbc/reference/syntax/sqldriverconnect-function.md)).  
  
 Chaque fois qu’un pilote retourne SQL_SUCCESS_WITH_INFO, le Gestionnaire de pilotes obtiendra les informations de diagnostic à partir de *hDbcInfoToken*et retourne SQL_SUCCESS_WITH_INFO, à l’application dans [SQLConnect](../../../odbc/reference/syntax/sqlconnect-function.md) et [SQLDriverConnect](../../../odbc/reference/syntax/sqldriverconnect-function.md).  
  
 Les applications ne doivent pas appeler cette fonction directement. Un pilote ODBC qui prend en charge le regroupement de connexions prenant en charge les pilotes doit implémenter cette fonction.  
  
 Inclure sqlspi.h pour le développement du pilote ODBC.  
  
## <a name="see-also"></a>Voir aussi  
 [Développement d’un pilote ODBC](../../../odbc/reference/develop-driver/developing-an-odbc-driver.md)   
 [Le regroupement de connexions prenant en charge les pilotes](../../../odbc/reference/develop-app/driver-aware-connection-pooling.md)   
 [Développement de reconnaissance du Pool de connexions dans un pilote ODBC](../../../odbc/reference/develop-driver/developing-connection-pool-awareness-in-an-odbc-driver.md)

