---
title: NumericScale, propriété (ADOX) | Documents Microsoft
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
- _Column::PutNumericScale
- _Column::GetNumericScale
- _Column::NumericScale
- _Column::put_NumericScale
- _Column::get_NumericScale
helpviewer_keywords:
- NumericScale property [ADOX]
ms.assetid: 573ee5d1-57c7-4a27-be79-a0e12944ad9b
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 227abf011a72d18210424def292cc9a620033356
ms.sourcegitcommit: bb044a48a6af9b9d8edb178dc8c8bd5658b9ff68
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="numericscale-property-adox"></a>NumericScale, propriété (ADOX)
Indique l’échelle d’une valeur numérique dans la colonne.  
  
## <a name="settings-and-return-values"></a>Paramètres et valeurs de retour  
 Définit et renvoie un **octets** valeur qui correspond à l’échelle des valeurs de données dans la colonne lorsque le [Type](../../../ado/reference/adox-api/type-property-column-adox.md) propriété est **adNumeric** ou **adDecimal**. **NumericScale** est ignoré pour toutes les autres types de données.  
  
## <a name="remarks"></a>Notes  
 La valeur par défaut est zéro (0).  
  
 **NumericScale** est en lecture seule pour [colonne](../../../ado/reference/adox-api/column-object-adox.md) objets déjà ajoutés à une collection.  
  
## <a name="applies-to"></a>S'applique à  
 [Column, objet (ADOX)](../../../ado/reference/adox-api/column-object-adox.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple de Code ADOX : NumericScale et Precision, propriétés-exemple (VB)](../../../ado/reference/adox-api/adox-code-example-numericscale-and-precision-properties-example-vb.md)   
 [Type, propriété (colonne) (ADOX)](../../../ado/reference/adox-api/type-property-column-adox.md)
