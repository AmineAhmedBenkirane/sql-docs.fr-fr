---
title: Propriété PropertyIndex (classe SqlServiceAdvancedProperty) | Documents Microsoft
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: wmi
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- PropertyIndex Property (SqlServiceAdvancedProperty Class)
apilocation:
- sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords:
- PropertyIndex property
ms.assetid: b18b45a2-e187-44f5-a8c9-26fd9828b6c6
caps.latest.revision: 33
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: fc73b363383118e240d67ec775e4217875bc0722
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="propertyindex-property-sqlserviceadvancedproperty-class"></a>Propriété PropertyIndex (classe SqlServiceAdvancedProperty)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]
  Obtient ou définit l'index de propriété qui spécifie la position d'une propriété avancée dans un tableau de propriétés avancées qui appartiennent à un service référencé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
object.PropertyIndex [= value]  
```  
  
## <a name="parts"></a>Éléments  
 *objet*  
 Objet de [classe SqlServiceAdvancedProperty](../../../relational-databases/wmi-provider-configuration-classes/sqlserviceadvancedproperty-class/sqlserviceadvancedproperty-class.md) qui représente une propriété avancée.  
  
## <a name="property-valuereturn-value"></a>Valeur de propriété/valeur de retour  
 A **uint32** valeur qui spécifie la position de la propriété avancée dans le tableau de propriétés avancées qui appartient au service référencé.  
  
## <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [Démarrage et arrêt des Services](http://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
