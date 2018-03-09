---
title: "Read, méthode | Documents Microsoft"
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: reference
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
- Stream::raw_Read
- _Stream::Read
helpviewer_keywords:
- Read method [ADO]
ms.assetid: 838502de-80f1-4eeb-8838-dd3d9403e567
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a702625e2bc1fbb00a8f7d1519d574a30d8df270
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2018
---
# <a name="read-method"></a>Read, méthode
Lit un nombre spécifié d’octets à partir d’un fichier binaire [flux](../../../ado/reference/ado-api/stream-object-ado.md) objet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Variant = Stream.Read ( NumBytes)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *NumBytes*  
 Ce paramètre est facultatif. A **Long** valeur qui spécifie le nombre d’octets à lire à partir du fichier ou le [StreamReadEnum](../../../ado/reference/ado-api/streamreadenum.md) valeur **adReadAll**, qui est la valeur par défaut.  
  
## <a name="return-value"></a>Valeur retournée  
 Le **en lecture** méthode lit un nombre spécifié d’octets ou l’intégralité du flux à partir d’un **flux** de l’objet et retourne les données résultantes comme un **Variant**.  
  
## <a name="remarks"></a>Notes  
 Si *NumBytes* reste supérieur au nombre d’octets dans le **flux**, seuls les octets restants sont retournés. La lecture des données ne sont pas remplies pour correspondre à la longueur spécifiée par *NumBytes*. S’il n’y a aucun octet pour lire, une valeur variant avec une valeur null est retourné. **Lecture** ne peut pas être utilisé pour lire vers l’arrière.  
  
> [!NOTE]
>  *NbOctets* mesure toujours des octets. Pour le texte **flux** objets ([Type](../../../ado/reference/ado-api/type-property-ado-stream.md) est **adTypeText**), utilisez [ReadText](../../../ado/reference/ado-api/readtext-method.md).  
  
## <a name="applies-to"></a>S'applique à  
 [Stream, objet (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)  
  
## <a name="see-also"></a>Voir aussi  
 [ReadText, méthode](../../../ado/reference/ado-api/readtext-method.md)
