---
title: "GetSchemaObject, méthode (ADO MD) | Documents Microsoft"
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
- GetSchemaObject
- Cellset::GetSchemaObject
helpviewer_keywords:
- GetSchemaObject method [ADO MD]
ms.assetid: 36b754b4-6b17-4dd1-a925-bca46938b7c4
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 2f7dca37be4fdebaab7bb16f82086b01a90a3665
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="getschemaobject-method-ado-md"></a>GetSchemaObject, méthode (ADO MD)
Récupère un objet de schéma ADO MD ([Dimension](../../../ado/reference/ado-md-api/dimension-object-ado-md.md), [hiérarchie](../../../ado/reference/ado-md-api/hierarchy-object-ado-md.md), [niveau](../../../ado/reference/ado-md-api/level-object-ado-md.md), ou [membre](../../../ado/reference/ado-md-api/member-object-ado-md.md)) par son [UniqueName](../../../ado/reference/ado-md-api/uniquename-property-ado-md.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Set object = CubeDef.GetSchemaObject (ObjType, UniqueName)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *Type de l’objet*  
 A [SchemaObjectTypeEnum](../../../ado/reference/ado-md-api/schemaobjecttypeenum.md) valeur qui spécifie le type d’objet de schéma (Dimension, hiérarchie, niveau ou membre) à récupérer.  
  
 *UniqueName*  
 A **chaîne** spécifiant le **UniqueName** valeur de la propriété de l’objet à récupérer.  
  
## <a name="remarks"></a>Notes  
 **GetSchemaObject** récupère des objets à l’aide de leurs noms uniques, comme spécifié par le **UniqueName** propriété. Les noms des objets parents n’avez pas besoin de connaître et collections de parent n’avez pas besoin d’être rempli pour récupérer un objet de schéma.  
  
## <a name="applies-to"></a>S'applique à  
 [CubeDef, objet (ADO MD)](../../../ado/reference/ado-md-api/cubedef-object-ado-md.md)  
  
## <a name="see-also"></a>Voir aussi  
 [CubeDef, objet (ADO MD)](../../../ado/reference/ado-md-api/cubedef-object-ado-md.md)
