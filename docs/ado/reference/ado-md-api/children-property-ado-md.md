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
ms.openlocfilehash: 630ddeaf83b09dfe502cf07efd7a4185011cff41
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
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
