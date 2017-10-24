---
title: Interface de ADOStreamConstruction | Documents Microsoft
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
- ADOStreamConstruction
helpviewer_keywords:
- ADOStreamConstruction interface [ADO]
ms.assetid: 92f5a939-3e1a-4b14-a9dd-90e6ce2dec74
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 9090cd99a7a43645165b9b1095f9cd9e789788f3
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="adostreamconstruction-interface"></a>Interface de ADOStreamConstruction
Le **ADOStreamConstruction** interface est utilisée pour construire un ADO **flux** objet OLE DB **IStream** objet dans une application C/C++.  
  
## <a name="properties"></a>Propriétés  
  
|||  
|-|-|  
|[Propriété de flux de données](../../../ado/reference/ado-api/stream-property.md)|En lecture/écriture. Obtient ou définit un OLE DB **flux** objet.|  
  
## <a name="methods"></a>Méthodes  
 Aucun.  
  
## <a name="events"></a>Événements  
 Aucun.  
  
## <a name="remarks"></a>Notes  
 Étant donné un OLE DB **IStream** objet (`pStream`), la construction de ADO **flux** objet (`adoStr`) s’élève à trois opérations ci-après :  
  
1.  Créer un ADO **flux** objet :  
  
    ```  
    Stream20Ptr adoStr;  
    adoStr.CreateInstance(__uuidof(Stream));  
    ```  
  
2.  Requête le **IADOStreamConstruction** de l’interface sur le **flux** objet :  
  
    ```  
    adoStreamConstructionPtr adoStrConstruct=NULL;  
    adoStr->QueryInterface(__uuidof(ADOStreamConstruction),  
                         (void**)&adoStrConstruct);  
    ```  
  
 Appelez le `IADOStreamConstruction::get_Stream` méthode propriété OLE DB **IStream** objet ADO **flux** objet :  
  
```  
IUnknown *pUnk=NULL;  
pRowset->QueryInterface(IID_IUnknown, (void**)&pUnk);  
adoStrConstruct->put_Stream(pUnk);  
```  
  
 Résultant `adoStr` objet représente maintenant l’ADO **flux** objet construit à partir d’OLE DB **IStream** objet.  
  
## <a name="requirements"></a>Spécifications  
 **Version :** ADO 2.0 ou version ultérieure  
  
 **Bibliothèque :** msado15.dll  
  
 **UUID :** 00000283-0000-0010-8000-00AA006D2EA4  
  
## <a name="see-also"></a>Voir aussi  
 [Référence des API ADO](../../../ado/reference/ado-api/ado-api-reference.md)

