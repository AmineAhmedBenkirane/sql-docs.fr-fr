---
title: "MaxRecords, propriété (ADO) | Documents Microsoft"
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
- Recordset15::MaxRecords
helpviewer_keywords:
- MaxRecords property [ADO]
ms.assetid: 20c76571-8c9a-482c-a99e-726ab1d93f8b
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 232f515c2250e1ec40fbb28bdff767baf9cf81c5
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="maxrecords-property-ado"></a>MaxRecords, propriété (ADO)
Indique le nombre maximal d’enregistrements à renvoyer à un [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) à partir d’une requête.  
  
## <a name="settings-and-return-values"></a>Paramètres et valeurs de retour  
 Définit ou retourne un **Long** valeur qui indique le nombre maximal d’enregistrements à retourner. Valeur par défaut est zéro (**0**), ce qui ne signifie aucune limite.  
  
## <a name="remarks"></a>Notes  
 Utilisez le **MaxRecords** propriété afin de limiter le nombre d’enregistrements renvoyé par le fournisseur à partir de la source de données. Le paramètre par défaut de cette propriété est zéro, ce qui signifie que le fournisseur retourne que tous les enregistrements demandés.  
  
 Le **MaxRecords** propriété est en lecture/écriture lorsque le **Recordset** est fermé et en lecture seule lorsqu’il est ouvert.  
  
## <a name="applies-to"></a>S'applique à  
 [Objet Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple de propriété MaxRecords (VB)](../../../ado/reference/ado-api/maxrecords-property-example-vb.md)   
 [Exemple de propriété MaxRecords (VC ++)](../../../ado/reference/ado-api/maxrecords-property-example-vc.md)   

