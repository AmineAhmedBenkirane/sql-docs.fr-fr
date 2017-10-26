---
title: "En-têtes (XMLA) | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- XMLA, headers
- SOAP headers [XML for Analysis]
- XML for Analysis, headers
- headers [XML for Analysis]
ms.assetid: 36407b5c-d98d-47e4-8d36-d8896e15a748
caps.latest.revision: 14
author: jeannt
ms.author: jeannt
manager: erikre
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: b12c8b2b22d51069998b4b49d1c9aceb43f063a5
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="xml-elements---headers"></a>Éléments XML - en-têtes
  Le protocole XMLA (XML for Analysis) utilise des éléments XML dans l'en-tête SOAP pour gérer des fonctionnalités au niveau du protocole, telles que la prise en charge de la session et la négociation des fonctionnalités prises en charge.  
  
## <a name="in-this-section"></a>Dans cette section  
 Les rubriques suivantes décrivent les éléments d’en-tête XMLA implémentés par [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].  
  
|Méthode| Description|  
|------------|-----------------|  
|[Élément BeginSession &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-headers/beginsession-element-xmla.md)|Utilise un en-tête SOAP dans un message de demande SOAP pour démarrer une nouvelle session sur une instance de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].|  
|[Élément EndSession &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-headers/endsession-element-xmla.md)|Utilise l'en-tête SOAP dans un message de demande SOAP pour terminer une session existante sur une instance de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].|  
|[Élément session &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-headers/session-element-xmla.md)|Utilise l'en-tête SOAP dans un message de demande SOAP pour identifier une session explicite existante sur une instance de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].|  
|[Élément ProtocolCapabilities &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-headers/protocolcapabilities-element-xmla.md)|Utilise l'en-tête SOAP dans un message de demande SOAP pour identifier des fonctionnalités de protocole entre une instance de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] et une application cliente.|  
  
## <a name="see-also"></a>Voir aussi  
 [Éléments XML &#40; XMLA &#41;](http://msdn.microsoft.com/library/40ab2360-efb6-4ba6-bf23-e84964e51008)   
 [Types de données XML &#40; XMLA &#41;](../../../analysis-services/xmla/xml-data-types/xml-data-types-xmla.md)   
 [Éléments XML &#40; XMLA &#41;](http://msdn.microsoft.com/library/40ab2360-efb6-4ba6-bf23-e84964e51008)  
  
  

