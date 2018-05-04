---
title: FilterAxis, propriété (ADO MD) | Documents Microsoft
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
- Cellset::FilterAxis
- FilterAxis
helpviewer_keywords:
- FilterAxis property [ADO MD]
ms.assetid: 9c656963-531e-4cd1-b698-d5f42a9b7ba3
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 671a56b9117ea77b479d1a0fff78729ca9c3f5ab
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
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
