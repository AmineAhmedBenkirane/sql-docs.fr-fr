---
title: Exemple de méthode (VB) de suppression de procédures | Documents Microsoft
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: ado
ms.technology:
- drivers
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- Delete method [ADOX], Visual Basic example
ms.assetid: 94f1ac93-e778-4a40-a85e-94bce5316ac7
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: d4bf17efacbcc9c0523e402a870bf5c430fe013e
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="procedures-delete-method-example-vb"></a>Exemple de méthode (VB) de suppression de procédures
Le code suivant montre comment supprimer une procédure à l’aide de la [supprimer](../../../ado/reference/adox-api/delete-method-adox-collections.md) méthode de la [procédures](../../../ado/reference/adox-api/procedures-collection-adox.md) collection.  
  
```  
' BeginDeleteProcedureVB  
Sub Main()  
    On Error GoTo DeleteProcedureError  
  
    Dim cat As New ADOX.Catalog  
  
    ' Open the catalog.  
    cat.ActiveConnection = _  
        "Provider='Microsoft.Jet.OLEDB.4.0';" & _  
        "Data Source='Northwind.mdb';"  
  
    ' Delete the procedure.  
    cat.Procedures.Delete "CustomerById"  
  
    'Clean up.  
    Set cat.ActiveConnection = Nothing  
    Set cat = Nothing  
    Exit Sub  
  
DeleteProcedureError:  
    Set cat = Nothing  
  
    If Err <> 0 Then  
        MsgBox Err.Source & "-->" & Err.Description, , "Error"  
    End If  
End Sub  
' EndDeleteProcedureVB  
```  
  
## <a name="see-also"></a>Voir aussi  
 [ActiveConnection, propriété (ADOX)](../../../ado/reference/adox-api/activeconnection-property-adox.md)   
 [Objet catalogue (ADOX)](../../../ado/reference/adox-api/catalog-object-adox.md)   
 [DELETE, méthode (Collections ADOX)](../../../ado/reference/adox-api/delete-method-adox-collections.md)   
 [Objet Procedure (ADOX)](../../../ado/reference/adox-api/procedure-object-adox.md)   
 [Procedures, collection (ADOX)](../../../ado/reference/adox-api/procedures-collection-adox.md)
