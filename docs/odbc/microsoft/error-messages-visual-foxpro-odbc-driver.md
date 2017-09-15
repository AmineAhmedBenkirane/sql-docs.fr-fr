---
title: "Messages d’erreur (le pilote ODBC Visual FoxPro) | Documents Microsoft"
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
- error messages [ODBC], Visual FoxPro ODBC driver
- Visual FoxPro ODBC driver [ODBC], error messages
- SQLSTATE [ODBC]
- FoxPro ODBC driver [ODBC], error messages
ms.assetid: 58ea9734-4edf-44da-ba80-938aa7b340e4
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: e561aab3359acb1f236aea38e76da33289e630ef
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="error-messages-visual-foxpro-odbc-driver"></a>Messages d’erreur (le pilote ODBC Visual FoxPro)
Lorsqu’une erreur se produit, le pilote Visual FoxPro renvoie les informations suivantes :  
  
-   Le numéro d’erreur natif et le texte du message d’erreur  
  
-   Le SQLSTATE (un code d’erreur ODBC) et le texte du message d’erreur  
  
 Pour accéder à ces informations d’erreur en appelant [SQLError](../../odbc/microsoft/sqlerror-visual-foxpro-odbc-driver.md).  
  
## <a name="native-errors"></a>Erreurs natives  
 Pour les erreurs qui se produisent dans la source de données, le pilote Visual FoxPro retourne le numéro d’erreur natif et le texte du message d’erreur. Pour obtenir la liste des numéros d’erreur natif, consultez [Visual FoxPro ODBC Driver natif Messages d’erreur](../../odbc/microsoft/visual-foxpro-odbc-driver-native-error-messages.md).  
  
## <a name="sqlstate-odbc-error-codes"></a>SQLSTATE (codes d'erreur ODBC)  
 Pour les erreurs qui sont détectées et retournées par le pilote Visual FoxPro, le pilote mappe le numéro d’erreur natif retourné avec le SQLSTATE approprié. Si un numéro d’erreur natif n’a pas un code d’erreur ODBC pour mapper à, le pilote Visual FoxPro retourne SQLSTATE S1000 (erreur générale).  
  
 Pour obtenir la liste de valeurs SQLSTATE générés par le pilote ODBC Visual FoxPro pour les erreurs de Visual FoxPro correspondants, consultez [Codes d’erreur ODBC](../../odbc/microsoft/odbc-error-codes-visual-foxpro-odbc-driver.md).  
  
## <a name="syntax"></a>Syntaxe  
 Messages d’erreur ont le format suivant :  
  
 **[** *fournisseur* **] [** *ODBC_component* **]** *error_message*  
  
 Les préfixes de crochets ([]) identifient la source de l’erreur, tel que défini dans le tableau suivant.  
  
|Source de données|Préfixe|Valeur|  
|-----------------|------------|-----------|  
|Gestionnaire de pilote|[fournisseur]<br />[ODBC_component]<br />[data_source]|[Microsoft]<br />[Gestionnaire de pilotes ODBC]<br />Néant|  
|Pilote Visual FoxPro|fournisseur]<br />[ODBC_component]<br />[data_source]|[Microsoft]<br />[Pilote ODBC Visual FoxPro]<br />Néant|  
  
 Par exemple, si le pilote ODBC Visual FoxPro n’a pas trouvé le fichier employee.dbf, elle peut retourner le message d’erreur suivant :  
  
 « [*Microsoft*] [*le pilote ODBC Visual FoxPro*] fichier 'employee.dbf' n’existe pas »
