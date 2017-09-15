---
title: "Propriété SQLState | Documents Microsoft"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- Error::GetSQLState
- Error::SQLState
- Error::get_SQLState
helpviewer_keywords:
- SQLState property
ms.assetid: f9e25967-54b0-444d-af2a-0d2c75365d3e
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: f65624cc9393a1ce676530102d41eb1655bcf79b
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="sqlstate-property"></a>SQLState, propriété
Indique l’état SQL d’une donnée [erreur](../../../ado/reference/ado-api/error-object.md) objet.  
  
## <a name="return-value"></a>Valeur retournée  
 Retourne les cinq caractères **chaîne** valeur respecte la norme SQL ANSI et indique le code d’erreur.  
  
## <a name="remarks"></a>Notes  
 Utilisez le **SQLState** propriété à lire le code d’erreur à cinq caractères renvoyé par le fournisseur lorsqu’une erreur se produit pendant le traitement d’une instruction SQL. Par exemple, lorsque vous utilisez le fournisseur Microsoft OLE DB pour ODBC avec une base de données Microsoft SQL Server, codes d’erreur SQL état issus de ODBC, basé sur les erreurs spécifiques à ODBC ou sur les erreurs qui proviennent de Microsoft SQL Server, puis sont mappés vers ODBC erreurs. Ces codes d’erreur sont documentés dans la norme SQL ANSI, mais peuvent être implémentés différemment par différentes sources de données.  
  
## <a name="applies-to"></a>S'applique à  
 [Objet Error](../../../ado/reference/ado-api/error-object.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Description, HelpContext, HelpFile, Native Error, nombre, Source et SQLState, propriétés-exemple (VB)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vb.md)   
 [Description, HelpContext, HelpFile, Native Error, nombre, Source et SQLState, propriétés-exemple (VC ++)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vc.md)   

