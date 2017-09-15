---
title: "FilterAxis, propriété (ADO MD) | Documents Microsoft"
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
- Cellset::FilterAxis
- FilterAxis
helpviewer_keywords:
- FilterAxis property [ADO MD]
ms.assetid: 9c656963-531e-4cd1-b698-d5f42a9b7ba3
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 81424fbe54417a16df85f31dfec1f7322da9974e
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="filteraxis-property-ado-md"></a>FilterAxis, propriété (ADO MD)
Indique les informations de filtre actuel [ensemble de cellules](../../../ado/reference/ado-md-api/cellset-object-ado-md.md).  
  
## <a name="return-values"></a>Valeurs de retour  
 Retourne un [axe](../../../ado/reference/ado-md-api/axis-object-ado-md.md) de l’objet et est en lecture seule.  
  
## <a name="remarks"></a>Notes  
 Utilisez le **FilterAxis** propriété à retourner des informations sur les dimensions qui ont été utilisées pour découper les données. Le [DimensionCount](../../../ado/reference/ado-md-api/dimensioncount-property-ado-md.md) propriété de la **axe** retourne le nombre de dimensions de découpage. Cet axe comprend généralement une seule ligne.  
  
 Le **axe** retourné par **FilterAxis** n’est pas contenue dans le [Axes](../../../ado/reference/ado-md-api/axes-collection-ado-md.md) collection pour un [ensemble de cellules](../../../ado/reference/ado-md-api/cellset-object-ado-md.md) objet.  
  
## <a name="applies-to"></a>S'applique à  
 [Cellset, objet (ADO MD)](../../../ado/reference/ado-md-api/cellset-object-ado-md.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Objet de l’axe (ADO MD)](../../../ado/reference/ado-md-api/axis-object-ado-md.md)   
 [Objet de dimension (ADO MD)](../../../ado/reference/ado-md-api/dimension-object-ado-md.md)   
 [DimensionCount, propriété (ADO MD)](../../../ado/reference/ado-md-api/dimensioncount-property-ado-md.md)
