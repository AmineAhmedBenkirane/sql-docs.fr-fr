---
title: AllowNullsEnum | Documents Microsoft
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: reference
ms.technology: drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords: AllowNullsEnum
helpviewer_keywords: AllowNullsEnum enumeration [ADOX]
ms.assetid: 6acf3689-1a7f-4379-9d7f-df452ccbac27
caps.latest.revision: "12"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: c9bbf4b48843d897003774e75e5148881b020f47
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="allownullsenum"></a>AllowNullsEnum
Spécifie si les enregistrements avec des valeurs null sont indexés.  
  
|Constante|Valeur| Description|  
|--------------|-----------|-----------------|  
|**adIndexNullsAllow**|0|L’index autorise les entrées dans lesquelles les colonnes clés sont null. Si une valeur null est entrée dans une colonne clé, l’entrée est insérée dans l’index.|  
|**adIndexNullsDisallow**|1|Valeur par défaut. L’index n’autorise pas les entrées dans lesquelles les colonnes clés sont null. Si une valeur null est entrée dans une colonne clé, une erreur se produit.|  
|**adIndexNullsIgnore**|2|L’index n’insère pas les entrées contenant des clés null. Si une valeur null est entrée dans une colonne clé, l’entrée est ignorée et aucune erreur ne se produit.|  
|**adIndexNullsIgnoreAny**|4|L’index n’insère pas d’entrée où une colonne clé a la valeur null. Un index possédant un plusieurs colonnes clés, si une valeur null est entrée dans une colonne, l’entrée est ignorée et aucune erreur ne se produit.|  
  
## <a name="applies-to"></a>S'applique à  
 [IndexNulls, propriété (ADOX)](../../../ado/reference/adox-api/indexnulls-property-adox.md)
