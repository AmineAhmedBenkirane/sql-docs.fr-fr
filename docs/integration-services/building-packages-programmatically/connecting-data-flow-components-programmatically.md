---
title: "Connexion par programme des composants de flux de données | Documents Microsoft"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data flow task [Integration Services], components
- paths [Integration Services], components
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: 404ecab7-7698-447b-93d6-dd256beb11ff
caps.latest.revision: 43
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 4a8ade977c971766c8f716ae5f33cac606c8e22d
ms.openlocfilehash: 40869328965e049b5981e94655226bc0a78dc37f
ms.contentlocale: fr-fr
ms.lasthandoff: 08/03/2017

---
# <a name="connecting-data-flow-components-programmatically"></a>Connexion de composants de flux de données par programme
  Après avoir ajouté des composants à la tâche de flux de données, vous devez les connecter pour créer une arborescence d'exécution qui représente le flux de données des sources vers des destinations en passant par des transformations. Ces objets <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> permettent de connecter les composants du flux de données.  
  
## <a name="creating-a-path"></a>Création d'un chemin d'accès  
 Appeler la nouvelle méthode de la <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.PathCollection%2A> propriété de la <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipe> interface pour créer un nouveau chemin d’accès et l’ajouter à la collection de chemins d’accès dans la tâche de flux de données. Cette méthode retourne un nouvel objet <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> déconnecté, que vous utilisez alors pour connecter deux composants.  
  
 Appelez la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100.AttachPathAndPropagateNotifications%2A> pour connecter le chemin d'accès et indiquer aux composants faisant partie du chemin d'accès qu'ils ont été connectés. Cette méthode accepte un <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> du composant en amont et un <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> du composant en aval en tant que paramètres. Par défaut, l'appel à la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> du composant crée une entrée unique pour les composants qui possèdent des entrées, et une sortie unique pour les composants qui possèdent des sorties. L'exemple suivant utilise cette sortie par défaut de la source et cette entrée par défaut de la destination.  
  
## <a name="next-step"></a>Étape suivante  
 Après avoir établi un chemin d’accès entre deux composants, l’étape suivante consiste à mapper les colonnes d’entrée dans le composant en aval, qui est décrite dans la rubrique suivante, [sélection d’entrée colonnes par programmation](../../integration-services/building-packages-programmatically/selecting-input-columns-programmatically.md).  
  
## <a name="sample"></a>Exemple  
 L'exemple de code suivant indique comment établir un chemin d'accès entre deux composants.  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package package = new Package();  
      Executable e = package.Executables.Add("STOCK:PipelineTask");  
      TaskHost thMainPipe = e as TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;  
  
      // Create the source component.    
      IDTSComponentMetaData100 source =  
        dataFlowTask.ComponentMetaDataCollection.New();  
      source.ComponentClassID = "DTSAdapter.OleDbSource";  
      CManagedComponentWrapper srcDesignTime = source.Instantiate();  
      srcDesignTime.ProvideComponentProperties();  
  
      // Create the destination component.  
      IDTSComponentMetaData100 destination =  
        dataFlowTask.ComponentMetaDataCollection.New();  
      destination.ComponentClassID = "DTSAdapter.OleDbDestination";  
      CManagedComponentWrapper destDesignTime = destination.Instantiate();  
      destDesignTime.ProvideComponentProperties();  
  
      // Create the path.  
      IDTSPath100 path = dataFlowTask.PathCollection.New();  
      path.AttachPathAndPropagateNotifications(source.OutputCollection[0],  
        destination.InputCollection[0]);  
    }  
  }  
```  
  
 }  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Microsoft.SqlServer.Dts.Runtime.Package = _  
      New Microsoft.SqlServer.Dts.Runtime.Package()  
    Dim e As Executable = package.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As Microsoft.SqlServer.Dts.Runtime.TaskHost = _  
      CType(e, Microsoft.SqlServer.Dts.Runtime.TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
    ' Create the source component.    
    Dim source As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    source.ComponentClassID = "DTSAdapter.OleDbSource"  
    Dim srcDesignTime As CManagedComponentWrapper = source.Instantiate()  
    srcDesignTime.ProvideComponentProperties()  
  
    ' Create the destination component.  
    Dim destination As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    destination.ComponentClassID = "DTSAdapter.OleDbDestination"  
    Dim destDesignTime As CManagedComponentWrapper = destination.Instantiate()  
    destDesignTime.ProvideComponentProperties()  
  
    ' Create the path.  
    Dim path As IDTSPath100 = dataFlowTask.PathCollection.New()  
    path.AttachPathAndPropagateNotifications(source.OutputCollection(0), _  
      destination.InputCollection(0))  
  
  End Sub  
  
End Module  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Sélectionner les colonnes d’entrée par programme](../../integration-services/building-packages-programmatically/selecting-input-columns-programmatically.md)  
  
  
