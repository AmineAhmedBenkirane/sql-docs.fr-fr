---
title: SQLSetConnectOption (le pilote ODBC Visual FoxPro) | Documents Microsoft
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
- SQLSetConnectOption function [ODBC], Visual FoxPro ODBC Driver
ms.assetid: 5a35449e-4694-4ee5-9fa1-45d5a8fe7823
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 14e3708e58d87a1ab38f4b22e9917320969c105b
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="sqlsetconnectoption-visual-foxpro-odbc-driver"></a>SQLSetConnectOption (le pilote ODBC Visual FoxPro)
> [!NOTE]  
>  Cette rubrique contient des informations spécifiques au pilote ODBC Visual FoxPro. Pour obtenir des informations générales sur cette fonction, consultez la rubrique appropriée sous [référence de l’API ODBC](../../odbc/reference/syntax/odbc-api-reference.md).  
  
 Prise en charge : partielle  
  
 Conformité d’API ODBC : Niveau 1  
  
 Définit les options qui régissent les aspects de connexions. Cette fonction est partiellement disponible : le pilote prend en charge toutes les valeurs pour le *fOption* argument, mais ne prend ne pas en charge certaines des *vParam* les valeurs pour le *fOption* argument SQL_TXN_ISOLATION.  
  
 Le tableau suivant décrit uniquement les arguments avec un comportement spécifique à l’implémentation du pilote ODBC Visual FoxPro de **SQLSetConnectOption**.  
  
|*fOption*|Notes|  
|---------------|-------------|  
|SQL_AUTOCOMMIT|Si vous choisissez SQL_AUTOCOMMIT_OFF, votre application doit explicitement valider ou annuler les transactions avec [SQLTransact](../../odbc/microsoft/sqltransact-visual-foxpro-odbc-driver.md); le pilote ODBC Visual FoxPro ne valide pas automatiquement une instruction transactable à l’achèvement. Le pilote commence une transaction si l’instruction est transactable.|  
|SQL_CURRENT_QUALIFIER|Peut être qualifié complet [base de données](../../odbc/microsoft/visual-foxpro-terminology.md) nom ou chemin d’accès complet d’un répertoire contenant zéro ou plusieurs [libre tables](../../odbc/microsoft/visual-foxpro-terminology.md).|  
|SQL_LOGINTIMEOUT|Retourne « Pilote non compatibles avec » erreur.|  
|SQL_CURSORS|Retourne « Pilote non compatibles avec » erreur.|  
|SQL_PACKET_SIZE|Retourne « Pilote non compatibles avec » erreur.|  
|SQL_TXN_ISOLATION|Le pilote permet uniquement de SQL_TXN_READ_COMMITTED.<br /><br /> Les éléments suivants *vParam*s ne sont pas prises en charge :<br /><br /> SQL_TXN_READ_UNCOMMITTED<br /><br /> SQL_TXN_REAPEATABLE_READ<br /><br /> SQL_TXN_SERIALIZABLE|  
  
 Pour plus d’informations, consultez [SQLSetConnectOption](../../odbc/reference/syntax/sqlsetconnectoption-function.md) dans les *de référence du programmeur ODBC*.

