---
title: Interface de ADOStreamConstruction | Documents Microsoft
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
- ADOStreamConstruction
helpviewer_keywords:
- ADOStreamConstruction interface [ADO]
ms.assetid: 92f5a939-3e1a-4b14-a9dd-90e6ce2dec74
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 693ccde4f48d5c358f65b83654d137745f97acff
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="adostreamconstruction-interface"></a>Interface de ADOStreamConstruction
Le **ADOStreamConstruction** interface est utilisée pour construire un ADO **flux** objet OLE DB **IStream** objet dans une application C/C++.  
  
## <a name="properties"></a>Propriétés  
  
|||  
|-|-|  
|[Stream, propriété](../../../ado/reference/ado-api/stream-property.md)|En lecture/écriture. Obtient ou définit un OLE DB **flux** objet.|  
  
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
 [Informations de référence sur l’API ADO](../../../ado/reference/ado-api/ado-api-reference.md)
