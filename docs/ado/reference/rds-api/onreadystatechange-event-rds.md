---
title: "onReadyStateChange, événement (RDS) | Documents Microsoft"
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
helpviewer_keywords: onReadyStateChange event [ADO]
ms.assetid: bf2ae3ac-bfe4-4709-b50a-ea7c282c3164
caps.latest.revision: "16"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 7912a623ac6fabbbf2460025f38e2c76238af1e9
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="onreadystatechange-event-rds"></a>onReadyStateChange, événement (RDS)
Le **onReadyStateChange** événement est appelé chaque fois que la valeur de la [ReadyState](../../../ado/reference/rds-api/readystate-property-rds.md) de propriété est modifiée.  
  
> [!IMPORTANT]
>  À compter de Windows 8 et Windows Server 2012, les composants de serveur Services Bureau à distance ne sont plus inclus dans le système d’exploitation Windows (consultez Windows 8 et [Cookbook de compatibilité de Windows Server 2012](https://www.microsoft.com/en-us/download/details.aspx?id=27416) pour plus de détails). Composants du client Bureau à distance seront supprimées dans une future version de Windows. Évitez d'utiliser cette fonctionnalité dans de nouveaux travaux de développement, et prévoyez de modifier les applications qui utilisent actuellement cette fonctionnalité. La migration vers les applications qui utilisent des services Bureau à distance [Service de données WCF](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
onReadyStateChange  
```  
  
#### <a name="parameters"></a>Paramètres  
 Aucun.  
  
## <a name="remarks"></a>Notes  
 Le **ReadyState** propriété reflète la progression d’une [RDS. DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md) de l’objet qu’il récupère de manière asynchrone des données dans son [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) objet. Utilisez le **onReadyStateChange** événement pour surveiller les modifications dans le **ReadyState** propriété chaque fois qu’ils se produisent. Cela est plus efficace que de vérifier régulièrement la valeur de propriété.  
  
## <a name="applies-to"></a>S'applique à  
 [DataControl, objet (RDS)](../../../ado/reference/rds-api/datacontrol-object-rds.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple de modèle d’événements ADO (VC ++)](../../../ado/reference/ado-api/ado-events-model-example-vc.md)   
 [Présentation rapide du gestionnaire d’événements ADO](../../../ado/guide/data/ado-event-handler-summary.md)


