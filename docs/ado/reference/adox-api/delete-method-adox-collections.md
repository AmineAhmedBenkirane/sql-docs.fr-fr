---
title: "DELETE, méthode (Collections ADOX) | Documents Microsoft"
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
- Views::Delete
- Groups::Delete
- Indexes::raw_Delete
- Columns::raw_Delete
- Tables::Delete
- Keys::Delete
- Users::Delete
- Users::raw_Delete
- Keys::raw_Delete
- Procedures::raw_Delete
- Views::raw_Delete
- Indexes::Delete
- Procedures::Delete
- Groups::raw_Delete
- Tables::raw_Delete
- Columns::Delete
helpviewer_keywords:
- delete method [ADOX]
ms.assetid: e6b6e3a4-8952-4d79-81f4-51019c338374
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 4efe8d4528d0085d2bef7f97bf9b1958be208547
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2018
---
# <a name="delete-method-adox-collections"></a>DELETE, méthode (Collections ADOX)
Supprime un objet d’une collection.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Collection.Delete Name  
```  
  
#### <a name="parameters"></a>Paramètres  
 *Nom*  
 A **Variant** qui spécifie le nom ou la position ordinale (index) de l’objet à supprimer.  
  
## <a name="remarks"></a>Notes  
 Une erreur se produit si le *nom* n’existe pas dans la collection.  
  
 Pour [Tables](../../../ado/reference/adox-api/tables-collection-adox.md) et [utilisateurs](../../../ado/reference/adox-api/users-collection-adox.md) collections, une erreur se produit si le fournisseur ne prend pas en charge suppression des tables ou des utilisateurs, respectivement. Pour [procédures](../../../ado/reference/adox-api/procedures-collection-adox.md) et [vues](../../../ado/reference/adox-api/views-collection-adox.md) collections, **supprimer** échoue si le fournisseur ne prend pas en charge les commandes persistantes.  
  
## <a name="applies-to"></a>S'applique à  
  
||||  
|-|-|-|  
|[Columns, collection (ADOX)](../../../ado/reference/adox-api/columns-collection-adox.md)|[Groups, collection (ADOX)](../../../ado/reference/adox-api/groups-collection-adox.md)|[Indexes, collection (ADOX)](../../../ado/reference/adox-api/indexes-collection-adox.md)|  
|[Keys, collection (ADOX)](../../../ado/reference/adox-api/keys-collection-adox.md)|[Procedures, collection (ADOX)](../../../ado/reference/adox-api/procedures-collection-adox.md)|[Tables, collection (ADOX)](../../../ado/reference/adox-api/tables-collection-adox.md)|  
|[Users, collection (ADOX)](../../../ado/reference/adox-api/users-collection-adox.md)|[Views, collection (ADOX)](../../../ado/reference/adox-api/views-collection-adox.md)||  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple de méthode (VB) de suppression de procédures](../../../ado/reference/adox-api/procedures-delete-method-example-vb.md)   
 [Views, exemple de méthode Delete (VB)](../../../ado/reference/adox-api/views-delete-method-example-vb.md)
