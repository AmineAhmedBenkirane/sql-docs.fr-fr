---
title: "Name, propriété (ADO) | Documents Microsoft"
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
- _Parameter::Name
- Field20::Name
helpviewer_keywords:
- Name property [ADO]
ms.assetid: cfd0e29c-8310-44ab-85c3-5761184b865d
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 8c2bf66589dc841e7f543b166b432f39a0869b3f
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="name-property-ado"></a>Nom, propriété (ADO)
Indique le nom d’un objet.  
  
## <a name="settings-and-return-values"></a>Paramètres et valeurs de retour  
 Définit ou retourne un **chaîne** valeur qui indique le nom d’un objet.  
  
## <a name="remarks"></a>Notes  
 Utilisez le **nom** propriété à attribuer un nom à ou récupérer le nom d’un **commande**, **propriété**, **champ**, ou **paramètre ** objet.  
  
 La valeur est en lecture/écriture sur un **commande** objet et en lecture seule sur un **propriété** objet.  
  
 Pour un **champ** objet, **nom** est généralement en lecture seule. Toutefois, pour les nouveaux **champ** les objets qui ont été ajoutées à la [champs](../../../ado/reference/ado-api/fields-collection-ado.md) collection d’un [enregistrement](../../../ado/reference/ado-api/record-object-ado.md), **nom** est en lecture/écriture uniquement après avoir le [valeur](../../../ado/reference/ado-api/value-property-ado.md) propriété pour le **champ** a été spécifié et le fournisseur de données a ajouté le nouveau **champ** en appelant le [ Mise à jour](../../../ado/reference/ado-api/update-method.md) méthode de la **champs** collection.  
  
 Pour **paramètre** objets pas encore ajouté à la [paramètres](../../../ado/reference/ado-api/parameters-collection-ado.md) collection, le **nom** propriété est en lecture/écriture. Pour ajoutées **paramètre** objets et tous les autres objets, la **nom** propriété est en lecture seule. Noms n’ont pas à être uniques dans une collection.  
  
 Vous pouvez récupérer le **nom** propriété d’un objet par référence ordinale, après quoi vous pouvez faire référence à l’objet directement par nom. Par exemple, si `rstMain.Properties(20).Name` génère `Updatability`, vous pouvez ensuite référencer cette propriété en tant que `rstMain.Properties("Updatability")`.  
  
## <a name="applies-to"></a>S'applique à  
  
|||  
|-|-|  
|[Objet de commande (ADO)](../../../ado/reference/ado-api/command-object-ado.md)|[Objet Field](../../../ado/reference/ado-api/field-object.md)|  
|[Objet de paramètre](../../../ado/reference/ado-api/parameter-object.md)|[Objet de propriété (ADO)](../../../ado/reference/ado-api/property-object-ado.md)|  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs et propriétés nom-exemple (VB)](../../../ado/reference/ado-api/attributes-and-name-properties-example-vb.md)   
 [Attributs et propriétés nom-exemple (VC ++)](../../../ado/reference/ado-api/attributes-and-name-properties-example-vc.md)   

