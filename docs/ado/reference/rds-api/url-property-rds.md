---
title: "URL, propriété (RDS) | Documents Microsoft"
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
helpviewer_keywords:
- URL property [ADO]
ms.assetid: 8c56b233-1be8-442c-8d0e-a4c96465bc99
caps.latest.revision: 15
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: feda106c2ce5450fa86550dbc83fd40c928c1510
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="url-property-rds"></a>URL, propriété (RDS)
Indique une chaîne qui contient une URL relative ou absolue.  
  
 Vous pouvez définir le **URL** propriété au moment du design dans le [DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md) de l’objet de balise ou au moment de l’exécution dans le code de script.  
  
> [!IMPORTANT]
>  À compter de Windows 8 et Windows Server 2012, les composants de serveur Services Bureau à distance ne sont plus inclus dans le système d’exploitation Windows (consultez Windows 8 et [Cookbook de compatibilité de Windows Server 2012](https://www.microsoft.com/en-us/download/details.aspx?id=27416) pour plus de détails). Composants du client Bureau à distance seront supprimées dans une future version de Windows. Évitez d'utiliser cette fonctionnalité dans de nouveaux travaux de développement, et prévoyez de modifier les applications qui utilisent actuellement cette fonctionnalité. La migration vers les applications qui utilisent des services Bureau à distance [Service de données WCF](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Design time: <PARAM NAME="URL" VALUE="Server">  
Run time: DataControl.URL="Server"  
```  
  
#### <a name="parameters"></a>Paramètres  
 *Server*  
 A **chaîne** valeur contenant une URL valide.  
  
 *DataControl*  
 Une variable objet qui représente un **DataControl** objet.  
  
## <a name="remarks"></a>Notes  
 En règle générale, l’URL identifie un fichier de Page ASP (.asp) qui peut produire et renvoyer un [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md). Par conséquent, l’utilisateur peut obtenir un **Recordset** sans avoir à invoquer le côté serveur [DataFactory](../../../ado/reference/rds-api/datafactory-object-rdsserver.md) de l’objet, ou programmer un objet métier personnalisé.  
  
 Si le **URL** propriété a été définie, [SubmitChanges](../../../ado/reference/rds-api/submitchanges-method-rds.md) soumettra des modifications à l’emplacement spécifié par l’URL.  
  
## <a name="applies-to"></a>S'applique à  
 [DataControl, objet (RDS)](../../../ado/reference/rds-api/datacontrol-object-rds.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple de propriété d’URL (VBScript)](../../../ado/reference/rds-api/url-property-example-vbscript.md)



