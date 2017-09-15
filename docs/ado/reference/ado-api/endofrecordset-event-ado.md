---
title: "L’événement EndOfRecordset (ADO) | Documents Microsoft"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- EndOfRecordset
- Recordset::EndOfRecordset
helpviewer_keywords:
- EndOfRecordset event [ADO]
ms.assetid: 475de5e2-f634-4954-9edf-0027a6ba38d6
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 4cf00efb278f6ea9937bd0fa87f929d45b8294cb
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="endofrecordset-event-ado"></a>Événement EndOfRecordset (ADO)
Le **EndOfRecordset** événement est appelé lorsqu’une tentative de déplacement vers une ligne après la fin de la [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
EndOfRecordset fMoreData, adStatus, pRecordset  
```  
  
#### <a name="parameters"></a>Paramètres  
 *fMoreData*  
 A **VARIANT_BOOL** valeur de la valeur VARIANT_TRUE, indique plusieurs lignes ont été ajoutés à la **Recordset**.  
  
 *N'*  
 Un [il ne](../../../ado/reference/ado-api/eventstatusenum.md) valeur d’état.  
  
 Lorsque **EndOfRecordset** est appelée, ce paramètre est défini sur **adStatusOK** si l’opération qui a provoqué l’événement a réussi. Il est défini sur **adStatusCantDeny** si cet événement ne peut pas demander l’annulation de l’opération qui a provoqué cet événement.  
  
 Avant de **EndOfRecordset** retourne, définissez ce paramètre sur **adStatusUnwantedEvent** pour éviter toute notification.  
  
 *Connection*  
 A **Recordset** objet. Le **Recordset** pour laquelle cet événement s’est produit.  
  
## <a name="remarks"></a>Notes  
 Un **EndOfRecordset** événement peut se produire si le [MoveNext](../../../ado/reference/ado-api/movefirst-movelast-movenext-and-moveprevious-methods-ado.md) échoue.  
  
 Ce gestionnaire d’événements est appelé lorsqu’une tentative est faite pour déplacer après la fin de la **Recordset** objet, par exemple suite à l’appel **MoveNext**. Toutefois, alors que dans ce cas, vous pouvez récupérer plusieurs enregistrements d’une base de données et les ajouter à la fin de la **Recordset**. Dans ce cas, définissez *fMoreData* à VARIANT_TRUE et à retourner **EndOfRecordset**. Appelez ensuite **MoveNext** à nouveau pour accéder aux nouveaux enregistrements récupérés.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple de modèle d’événements ADO (VC ++)](../../../ado/reference/ado-api/ado-events-model-example-vc.md)   
 [Résumé du Gestionnaire d’événements ADO](../../../ado/guide/data/ado-event-handler-summary.md)
