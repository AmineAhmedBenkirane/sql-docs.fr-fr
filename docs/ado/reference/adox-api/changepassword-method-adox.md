---
title: "ChangePassword, méthode (ADOX) | Documents Microsoft"
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology: drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- _User25::raw_ChangePassword
- _User25::ChangePassword
helpviewer_keywords: ChangePassword method [ADOX]
ms.assetid: d187fbc6-5fac-4abb-803d-bf344dcf0302
caps.latest.revision: "12"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 4df8c533048ae51662369b66361fb6b642c97f03
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="changepassword-method-adox"></a>ChangePassword, méthode (ADOX)
Modifie le mot de passe pour un [utilisateur](../../../ado/reference/adox-api/user-object-adox.md) compte.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
User.ChangePassword OldPassword, NewPassword  
```  
  
#### <a name="parameters"></a>Paramètres  
 *OldPassword*  
 A **chaîne** valeur qui spécifie le mot de passe existant. Si l’utilisateur ne possède pas un mot de passe, utilisez une chaîne vide (« ») pour *OldPassword*.  
  
 *NewPassword*  
 A **chaîne** valeur qui spécifie le nouveau mot de passe.  
  
## <a name="remarks"></a>Notes   
 Pour des raisons de sécurité, l’ancien mot de passe doit être spécifié en plus du nouveau mot de passe.  
  
 Une erreur se produit si le fournisseur ne prend pas en charge l’administration des propriétés de tiers de confiance.  
  
## <a name="applies-to"></a>S'applique à  
 [User, objet (ADOX)](../../../ado/reference/adox-api/user-object-adox.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Append (méthode) sur les collections Groups et Users, ChangePassword, exemple de méthodes (VB)](../../../ado/reference/adox-api/groups-and-users-append-changepassword-methods-example-vb.md)
