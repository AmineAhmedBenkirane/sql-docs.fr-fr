---
title: "Passage de paramètres à une commande nommée | Documents Microsoft"
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology: drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- named commands [ADO]
- commands [ADO], passing parameters to a named command
ms.assetid: 36e0cdbe-7f50-40f5-af0d-700f5d8dc75a
caps.latest.revision: "12"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 5e0db27250c2f095c31aa5bca95b738fa64ca922
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="passing-parameters-to-a-named-command"></a>Passage de paramètres à une commande nommée
Tout comme le résultat de la commande est transmis en tant qu’une *out* variable de la commande nommée, les paramètres pour une commande paramétrée peut été passé en tant que *dans* variables à la commande nommée.  
  
 Le code suivant exemple essaie de récupérer toutes les commandes passées par le client dont **CustomerID** est « ALKFI » à partir de la base de données Northwind. La valeur de **CustomerID** est fournie au moment lorsque la commande nommée est appelée.  
  
```  
Const DS = "MySqlServer"  
Const DB = "Northwind"  
Const DP = "SQLOLEDB"  
  
Dim objConn As New ADODB.Connection  
Dim objRs As New ADODB.Recordset  
Dim objComm As New ADODB.Command  
  
CommandText = "SELECT OrderID, OrderDate, " & _  
                     "RequiredDate, ShippedDate " & _  
                     "FROM Orders " & _  
                     "WHERE CustomerID = ? " & _  
                     "ORDER BY OrderID"  
  
ConnectionString = "Provider=" & DP & _  
                   ";Data Source=" & DS & _  
                   ";Initial Catalog=" & DB & _  
                   ";Integrated Security=SSPI;"  
  
' Connect to the data source.  
objConn.Open ConnectionString  
  
' Set a named command.  
objComm.CommandText = CommandText  
objComm.CommandType = adCmdText  
objComm.Name = "GetOrdersOf"  
Set objComm.ActiveConnection = objConn  
  
' Call the named command, passing a CustomerID value  
' as the input parameter.   
'    "ALFKI" is the required input parameter,  
'    objRs is the resultant output variable.  
objConn.GetOrdersOf "ALKFI", objRs  
  
' Display the result.  
Debug.Print "All orders by ALFKI:"  
Do While Not objRs.EOF  
    Debug.Print vbTab & objRs(0) & vbTab & objRs(1) & vbTab & _  
                objRs(2) & vbTab & objRs(3)  
    objRs.MoveNext  
Loop  
  
' Clean up.  
objRs.Close  
objConn.Close  
Set objRs = Nothing  
Set objConn = Nothing  
Set objComm = Nothing  
```  
  
 Notez que tous les paramètres d’entrée doivent précéder n’importe quelle variable de sortie et les types de données de paramètres doivent correspondre à ou peuvent être converties à ceux des champs correspondants. L’instruction suivante :  
  
```  
objConn.GetOrdersOf 12345, objRs  
```  
  
 — entraîne une erreur de types de données ne correspondent pas, car le paramètre d’entrée obligatoire est d’un **chaîne** type, pas d’un **entier** type.  
  
 L’appel suivant :  
  
```  
objConn.GetOrdersOf "12345", objRs  
```  
  
 — est valide, mais génère un jeu, car aucun enregistrement n’existe dans la base de données de résultats vide.  
  
## <a name="see-also"></a>Voir aussi  
 [Connection, objet (ADO MD)](../../../ado/reference/ado-api/connection-object-ado.md)
