---
title: ADCPROP_ASYNCTHREADPRIORITY_ENUM | Documents Microsoft
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: reference
ms.technology: drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords: ADCPROP_ASYNCTHREADPRIORITY_ENUM
helpviewer_keywords: ADCPROP_ASYNCTHREADPRIORITY_ENUM [ADO]
ms.assetid: f0965617-17d8-41e0-98d0-f824274735a6
caps.latest.revision: "10"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 39e10a6563e33ae1d1235bc220d7bd82826be853
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="adcpropasyncthreadpriorityenum"></a>ADCPROP_ASYNCTHREADPRIORITY_ENUM
Pour un RDS [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) d’objet, spécifie la priorité d’exécution du thread asynchrone qui extrait des données.  
  
 Utilisez ces constantes avec la **Recordset** »**Background Thread Priority**« propriété dynamique, qui est référencée dans l’index de base de données des propriétés dynamiques ADO-vers-OLE et expliquée dans la [ Le Service de curseur Microsoft pour OLE DB](../../../ado/guide/appendixes/microsoft-cursor-service-for-ole-db-ado-service-component.md) documentation.  
  
|Constante|Valeur| Description|  
|--------------|-----------|-----------------|  
|**adPriorityAboveNormal**|4|Définit la priorité entre normal et le plus élevé.|  
|**adPriorityBelowNormal**|2|Définit la priorité entre la plus faible et normal.|  
|**adPriorityHighest**|5|Définit la priorité le plus élevé possible.|  
|**AdPriorityLowest**|1|Définit la priorité le plus bas possible.|  
|**adPriorityNormal**|3|Définit la priorité normale.|  
  
## <a name="adowfc-equivalent"></a>ADO/WFC équivalent  
 Package : **com.ms.wfc.data**  
  
|Constante|  
|--------------|  
|AdoEnums.AdcPropAsyncThreadPriority.ABOVENORMAL|  
|AdoEnums.AdcPropAsyncThreadPriority.BELOWNORMAL|  
|AdoEnums.AdcPropAsyncThreadPriority.HIGHEST|  
|AdoEnums.AdcPropAsyncThreadPriority.LOWEST|  
|AdoEnums.AdcPropAsyncThreadPriority.NORMAL|
