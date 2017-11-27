---
title: "Gestion des erreurs dans l’API TOM (Analysis Services AMO-TOM) | Documents Microsoft"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: tabular-models
ms.reviewer: 
ms.suite: sql
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ec44daa0-a90e-42ad-b70d-6a7a7a4e4b7b
caps.latest.revision: "4"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 30d824c54359a7f7db0d57f7a4a7922329a0e89b
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="handling-errors-in-the-tom-api-analysis-services-amo-tom"></a>Gestion des erreurs dans l’API TOM (Analysis Services AMO-TOM)

[!INCLUDE[ssas-appliesto-sql2016-later-aas](../../includes/ssas-appliesto-sql2016-later-aas.md)]

Une pratique courante pour les bibliothèques managées, telles que le modèle d’objet tabulaire (TOM) Analysis Services Management Objects (AMO) est d’utiliser des exceptions comme un mécanisme pour signaler des conditions d’erreur à l’utilisateur.  

Lorsqu’une erreur est détectée dans AMO-TOM, en plus de lever des exceptions .NET standard quelques comme **ArgumentException** et **InvalidOperationException**, TOM peut lever plusieurs exceptions spécifiques à TOM.  

TOM exceptions sont dérivées de [AmoException classe](http://msdn.microsoft.com/library/microsoft.analysisservices.amoexception.aspx), couvrant les deux exceptions spécifiques TOM et AMO. 

Pour illustrer la gestion des exceptions dans TOM, passons en revue une des exceptions plus communes, qui est [OperationException classe](http://msdn.microsoft.com/library/microsoft.analysisservices.operationexception.aspx).

**OperationException** est levée lorsqu’un utilisateur initie une opération sur le serveur Analysis Services et le serveur ne parvient pas à effectuer une opération, car l’action est non conforme, ou en raison d’une autre erreur interne ou externe. 

Lors de la levée, ** OperationException ** objet contient une liste d’erreurs XMLA retournés par le serveur. 

Notez que le serveur n’accepte pas les modifications qui ne sont pas valides. Si cela se produit, rétablissez le **modèle** arborescence dans la dernière configuration correcte connue à l’aide du [UndoLocalChanges méthode](http://msdn.microsoft.com/library/microsoft.analysisservices.tabular.model.undolocalchanges.aspx), corrigez le modèle, puis soumettez à nouveau. 

## <a name="code-example-handle-exceptions"></a>L’exemple de code : gérer les exceptions 
 
```
 try 
 { 
  // Change the Model, for example create a table. 
  // … 
   model.saveChanges(); 
 } 
  catch(operationException ex) 
 { 
  foreach(XmlaError err in ex.Results.OfType<XmlaError>().cast<XmlaError>()) 
  { 
   Console.WriteLine(“Error returned from the server:” + err.Messsage ); 
  } 
 } 
```

## <a name="next-steps"></a>Étapes suivantes

D’autres exceptions pertinentes sont les suivantes :

- [Classe de TomInternalException](http://msdn.microsoft.com/library/microsoft.analysisservices.tabular.tominternalexception.aspx)
- [Classe de TomValidationException](http://msdn.microsoft.com/library/microsoft.analysisservices.tabular.tomvalidationexception.aspx)
- [Classe de JsonSerializationException](http://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_JsonSerializationException.htm)
