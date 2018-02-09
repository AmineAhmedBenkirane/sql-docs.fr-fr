---
title: "State, propriété (ADO MD) | Documents Microsoft"
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- State
- Cellset::State
helpviewer_keywords:
- State property [ADO MD]
ms.assetid: 06d480ca-9eb6-4570-a45d-a73539bddd32
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 1886dae43bdb764a67fa5e44b1e8fe9744c0cb5f
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2018
---
# <a name="state-property-ado-md"></a>State, propriété (ADO MD)
Indique l’état actuel de l’ensemble de cellules.  
  
## <a name="return-values"></a>Valeurs de retour  
 Retourne un **Long** entier qui indique l’état actuel de la [ensemble de cellules](../../../ado/reference/ado-md-api/cellset-object-ado-md.md) de l’objet et est en lecture seule. Les valeurs suivantes sont valides : **adStateClosed** (0) et **adStateOpen** (1).  
  
## <a name="remarks"></a>Notes  
 Pour utiliser le [ObjectStateEnum](../../../ado/reference/ado-api/objectstateenum.md) les noms de constantes, vous devez disposer de la bibliothèque de types ADO référencée dans votre projet. Consultez [à l’aide d’ADO avec ADO MD](../../../ado/guide/multidimensional/using-ado-with-ado-md.md) pour plus d’informations.  
  
## <a name="applies-to"></a>S'applique à  
 [Cellset, objet (ADO MD)](../../../ado/reference/ado-md-api/cellset-object-ado-md.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Close (méthode) (ADO MD)](../../../ado/reference/ado-md-api/close-method-ado-md.md)   
 [Open, méthode (ADO MD)](../../../ado/reference/ado-md-api/open-method-ado-md.md)
