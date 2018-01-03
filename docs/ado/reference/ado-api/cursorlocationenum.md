---
title: CursorLocationEnum | Documents Microsoft
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
apitype: COM
f1_keywords: CursorLocationEnum
helpviewer_keywords: CursorLocationEnum enumeration [ADO]
ms.assetid: acb255ff-1734-4b70-89bb-aef862b4c63b
caps.latest.revision: "12"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: ce5f769988d0cf548ea47fb8278fc13c04ff16af
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cursorlocationenum"></a>CursorLocationEnum
Spécifie l’emplacement du service de curseur.  
  
|Constante|Valeur|Description|  
|--------------|-----------|-----------------|  
|**adUseClient**|3|Utilise des curseurs côté client fournis par une bibliothèque de curseurs locaux. Les services de curseur local permet souvent de nombreuses fonctionnalités fournies par le pilote les curseurs ne peuvent pas, donc à l’aide de ce paramètre peut fournir un avantage en ce qui concerne les fonctionnalités qui seront activés. Pour la compatibilité descendante, le synonyme **adUseClientBatch** est également pris en charge.|  
|**adUseNone**| 1|N’utilise pas les services de curseur. (Cette constante est obsolète et s’affiche uniquement pour des raisons de compatibilité descendante).|  
|**adUseServer**|2|Valeur par défaut. Utilise des curseurs fournis par le fournisseur de données ou le pilote. Ces curseurs sont parfois très flexibles et permettant plus facilement les modifications apportées à la source de données. Toutefois, certaines fonctionnalités de la [le Service de curseur Microsoft pour OLE DB](../../../ado/guide/data/the-microsoft-cursor-service-for-ole-db.md), tel que dissocié<br /><br /> [Jeu d’enregistrements](../../../ado/reference/ado-api/recordset-object-ado.md) objets, ne peut pas être simulés avec des curseurs côté serveur et de ces fonctionnalités ne seront pas disponibles avec ce paramètre.|  
  
## <a name="adowfc-equivalent"></a>ADO/WFC équivalent  
 Package : **com.ms.wfc.data**  
  
|Constante|  
|--------------|  
|AdoEnums.CursorLocation.CLIENT|  
|AdoEnums.CursorLocation.NONE|  
|AdoEnums.CursorLocation.SERVER|  
  
## <a name="applies-to"></a>S'applique à  
 [CursorLocation, propriété (ADO)](../../../ado/reference/ado-api/cursorlocation-property-ado.md)
