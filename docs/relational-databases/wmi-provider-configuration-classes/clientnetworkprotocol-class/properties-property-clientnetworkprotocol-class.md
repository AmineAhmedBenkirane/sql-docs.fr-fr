---
title: Propriété Properties (classe ClientNetworkProtocol) | Documents Microsoft
ms.custom: ''
ms.date: 03/14/2017
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
- Properties Property (ClientNetworkProtocol Class)
apilocation:
- sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords:
- Properties property
ms.assetid: 7e0a4e38-4555-4750-8fd3-4425b29e6aa1
caps.latest.revision: 33
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: e2e930adba245ed48ba7c8f392e4bc6f59b704e2
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="properties-property-clientnetworkprotocol-class"></a>Propriété Properties (classe ClientNetworkProtocol)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]
  Obtient les propriétés associées au protocole réseau client actuel spécifié par [Configurer des protocoles clients](http://technet.microsoft.com/library/ms181035.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
object.Properties [= value]  
```  
  
## <a name="parts"></a>Éléments  
 *objet*  
 Objet de [classe ClientNetworkProtocol](../../../relational-databases/wmi-provider-configuration-classes/clientnetworkprotocol-class/clientnetworkprotocol-class.md) qui représente le protocole réseau utilisé par le client [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .  
  
## <a name="property-valuereturn-value"></a>Valeur de propriété/valeur de retour  
 Tableau d'objets de [classe ClientNetworkProtocolProperty](../../../relational-databases/wmi-provider-configuration-classes/clientnetworkprotocolproperty-class/clientnetworkprotocolproperty-class.md) qui représentent les propriétés prises en charge par le protocole réseau client actuel référencé par la propriété **OrderValue** .  
  
## <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [Configuration des bibliothèques réseau et des protocoles réseau clients](http://technet.microsoft.com/library/ms181035.aspx)  
  
  
