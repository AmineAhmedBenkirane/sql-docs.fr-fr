---
title: "Méthode getPacketSize (SQLServerDataSource) | Documents Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: jdbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname: SQLServerDataSource.getPacketSize
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: b2e9f01a-2e51-47e5-90bf-43c62d1be74d
caps.latest.revision: "14"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: ed2658e2a4847af07a773bb32a229a24d77d6a09
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2017
---
# <a name="getpacketsize-method-sqlserverdatasource"></a>Méthode getPacketSize (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Retourne la taille du paquet réseau actuelle utilisée pour communiquer avec [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)], spécifié en octets.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public int getPacketSize()  
```  
  
## <a name="return-value"></a>Valeur retournée  
 Un **int** valeur contenant la taille du paquet réseau actuelle.  
  
## <a name="remarks"></a>Notes  
 Si la propriété packetSize n’est pas définie, la méthode getPacketSize retourne la valeur par défaut de 8 000.  
  
## <a name="see-also"></a>Voir aussi  
 [Membres de SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource, classe](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
