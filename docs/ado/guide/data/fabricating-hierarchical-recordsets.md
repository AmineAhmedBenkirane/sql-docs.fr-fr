---
title: "Fabrication de jeux d’enregistrements | Documents Microsoft"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Recordset fabrication [ADO]
- hierarchical Recordsets [ADO]
- fabricating hierarchical Recordsets [ADO]
- data shaping [ADO], hierarchical Recordsets
ms.assetid: a584e642-a4a3-418e-bc20-3aff81a5625a
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: f8b01b8cd08c46f641fbd713f4acbdeca53db5c6
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="fabricating-hierarchical-recordsets"></a>Fabrication de jeux d’enregistrements
L’exemple suivant montre comment créer un jeu d’enregistrements hiérarchique sans source de données sous-jacente en utilisant les données de mise en forme pour définir les colonnes pour les parents, enfants et petits-enfants **jeux d’enregistrements**.  
  
 Pour créer une liste hiérarchique **Recordset**, vous devez spécifier le [Service de mise en forme des données Microsoft pour OLE DB (fournisseur de services ADO)](../../../ado/guide/appendixes/microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) (MSDataShape), et vous pouvez spécifier une valeur de fournisseur de données None dans le paramètre de chaîne de connexion de la [ouvrir](../../../ado/reference/ado-api/open-method-ado-connection.md) méthode de la [connexion](../../../ado/reference/ado-api/connection-object-ado.md) objet. Pour plus d’informations, consultez [fournisseur de mise en forme des données](../../../ado/guide/data/required-providers-for-data-shaping.md).  
  
```  
Dim cn As New ADODB.Connection  
Dim rsCustomers As New ADODB.Recordset  
  
cn.Open "Provider=MSDataShape;Data Provider=NONE;"  
  
strShape = _  
"SHAPE APPEND NEW adInteger AS CustID," & _  
            " NEW adChar(25) AS FirstName," & _  
            " NEW adChar(25) AS LastName," & _  
            " NEW adChar(12) AS SSN," & _  
            " NEW adChar(50) AS Address," & _  
         " ((SHAPE APPEND NEW adChar(80) AS VIN_NO," & _  
                        " NEW adInteger AS CustID," & _  
                        " NEW adChar(20) AS BodyColor, " & _  
                     " ((SHAPE APPEND NEW adChar(80) AS VIN_NO," & _  
                                    " NEW adChar(20) AS Make, " & _  
                                    " NEW adChar(20) AS Model," & _  
                                    " NEW adChar(4) AS Year) " & _  
                        " AS VINS RELATE VIN_NO TO VIN_NO))" & _  
            " AS Vehicles RELATE CustID TO CustID) "  
  
rsCustomers.Open strShape, cn, adOpenStatic, adLockOptimistic, -1  
```  
  
 Dès que le **Recordset** a été créé, il peut être rempli, manipulé ou conservé dans un fichier.  
  
## <a name="see-also"></a>Voir aussi  
 [L’accès aux lignes dans un jeu d’enregistrements hiérarchique](../../../ado/guide/data/accessing-rows-in-a-hierarchical-recordset.md)   
 [Grammaire de mise en forme formelle](../../../ado/guide/data/formal-shape-grammar.md)   
 [Fournisseurs requis pour la mise en forme des données](../../../ado/guide/data/required-providers-for-data-shaping.md)   
 [Clause APPEND de forme](../../../ado/guide/data/shape-append-clause.md)   
 [En général, les commandes de forme](../../../ado/guide/data/shape-commands-in-general.md)