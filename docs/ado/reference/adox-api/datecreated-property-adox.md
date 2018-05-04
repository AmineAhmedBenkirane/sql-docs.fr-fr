---
title: DateCreated, propriété (ADOX) | Documents Microsoft
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
- _Table::get_DateCreated
- _Table::DateCreated
- _Table::GetDateCreated
helpviewer_keywords:
- DateCreated property [ADOX]
ms.assetid: 2bf4b00d-045c-444e-8af7-8af6297ed418
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 4c7504f93093291e2a8863367a5f05b18d9214ae
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="datecreated-property-adox"></a>DateCreated, propriété (ADOX)
Indique la date de que création de l’objet.  
  
## <a name="return-values"></a>Valeurs de retour  
 Retourne un **Variant** valeur qui spécifie la date de création. La valeur est null si **DateCreated** n’est pas pris en charge par le fournisseur.  
  
## <a name="remarks"></a>Notes  
 Le **DateCreated** propriété est null pour les objets récemment ajoutés. Après avoir ajouté un nouvel [vue](../../../ado/reference/adox-api/view-object-adox.md) ou [procédure](../../../ado/reference/adox-api/procedure-object-adox.md), vous devez appeler la [Actualiser](../../../ado/reference/ado-api/refresh-method-ado.md) méthode de la [vues](../../../ado/reference/adox-api/views-collection-adox.md) ou [procédures](../../../ado/reference/adox-api/procedures-collection-adox.md) collection pour obtenir les valeurs de la **DateCreated** propriété.  
  
## <a name="applies-to"></a>S'applique à  
  
||||  
|-|-|-|  
|[Procedure, objet (ADOX)](../../../ado/reference/adox-api/procedure-object-adox.md)|[Table, objet (ADOX)](../../../ado/reference/adox-api/table-object-adox.md)|[View, objet (ADOX)](../../../ado/reference/adox-api/view-object-adox.md)|  
  
## <a name="see-also"></a>Voir aussi  
 [DateCreated et DateModified, propriétés-exemple (VB)](../../../ado/reference/adox-api/datecreated-and-datemodified-properties-example-vb.md)   
 [DateModified, propriété (ADOX)](../../../ado/reference/adox-api/datemodified-property-adox.md)
