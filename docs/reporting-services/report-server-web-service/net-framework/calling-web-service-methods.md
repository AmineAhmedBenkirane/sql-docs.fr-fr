---
title: "Appel des méthodes de service web | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: reference
applies_to: SQL Server 2016 Preview
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- Web service [Reporting Services], calls
- calling Web service
- Report Server Web service, SOAP
- XML Web service [Reporting Services], calls
- Report Server Web service, calls
- XML Web service [Reporting Services], SOAP
- SOAP [Reporting Services], calls
ms.assetid: f6f0c6e3-8bb5-4c44-9d19-1872edc72746
caps.latest.revision: "38"
author: guyinacube
ms.author: asaxton
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: eae7dc1f7e673f332f5c85db89b9a247f0a36d35
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="calling-web-service-methods"></a>Appel des méthodes de service Web
  Quand vous utilisez une classe proxy [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] pour appeler des opérations de service web, vous le faites en utilisant les méthodes de cette classe. Ces méthodes répondent comme toute autre méthode de classe incluse dans la bibliothèque de classes [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]. Toutes les méthodes de service Web disposent d'un accès public et requièrent que vous fournissiez le nombre approprié d'arguments et de types d'arguments. Après avoir créé une instance de la classe proxy dans votre projet, vous pouvez appeler les méthodes pour effectuer des opérations de création de rapports via le serveur de rapports. Le code C# suivant illustre l’utilisation de la méthode <xref:ReportService2010.ReportingService2010.ListChildren%2A> de la classe proxy <xref:ReportService2010.ReportingService2010>. Le code est utilisé pour effectuer un appel récurrent du service Web qui renvoie un tableau d'objets <xref:ReportService2010.CatalogItem> qui contient la liste de tous les éléments contenus dans la base de données du serveur de rapports :  
  
```vb  
Dim rs As New ReportingService2010()  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
Dim items As CatalogItem() = rs.ListChildren("/", True)  
```  
  
```csharp  
ReportingService2010 rs = new ReportingService2010();  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
CatalogItem[] items = rs.ListChildren("/", true);  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Génération d’applications à l’aide du service web et du .NET Framework](../../../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)   
 [Service web Report Server](../../../reporting-services/report-server-web-service/report-server-web-service.md)   
 [Informations techniques de référence &#40;SSRS&#41;](../../../reporting-services/technical-reference-ssrs.md)  
  
  
