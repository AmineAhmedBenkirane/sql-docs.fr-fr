---
title: Enfants, propriété (ADO MD) | Documents Microsoft
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: ado
ms.technology:
- drivers
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Member::Children
- Children
helpviewer_keywords:
- Children property [ADO MD]
ms.assetid: 61d36468-1ccd-467a-9cb5-17d0bfacc766
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 872d9d125cc1f397d0f9b6e8cbd66c32308b5072
ms.sourcegitcommit: bb044a48a6af9b9d8edb178dc8c8bd5658b9ff68
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="children-property-ado-md"></a>Enfants, propriété (ADO MD)
Retourne un [membres](../../../ado/reference/ado-md-api/members-collection-ado-md.md) collection pour laquelle actuel [membre](../../../ado/reference/ado-md-api/member-object-ado-md.md) est le parent dans la hiérarchie.  
  
## <a name="return-values"></a>Valeurs de retour  
 Retourne un **membres** collection et est en lecture seule.  
  
## <a name="remarks"></a>Notes  
 Le **enfants** propriété contient un **membres** collection pour laquelle actuel **membre** est le parent hiérarchique. Niveau de feuille **membre** objets n’ont aucun membre enfant le **membres** collection. Cette propriété est uniquement prise en charge sur **membre** objets appartenant à un [niveau](../../../ado/reference/ado-md-api/level-object-ado-md.md) objet. Une erreur se produit lorsque cette propriété est référencée à partir de **membre** objets appartenant à un [Position](../../../ado/reference/ado-md-api/position-object-ado-md.md) objet.  
  
## <a name="applies-to"></a>S'applique à  
 [Member, objet (ADO MD)](../../../ado/reference/ado-md-api/member-object-ado-md.md)  
  
## <a name="see-also"></a>Voir aussi  
 [ChildCount, propriété (ADO MD)](../../../ado/reference/ado-md-api/childcount-property-ado-md.md)
