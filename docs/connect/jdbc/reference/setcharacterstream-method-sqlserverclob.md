---
title: "Méthode setCharacterStream (SQLServerClob) | Documents Microsoft"
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
apiname: SQLServerClob.setCharacterStream
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: c02778f2-6681-4a84-a58b-2bcfac4233e4
caps.latest.revision: "9"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 0028cef27107027e99d3eaf5c5163ea20015209f
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2017
---
# <a name="setcharacterstream-method-sqlserverclob"></a>Méthode setCharacterStream (SQLServerClob)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Retourne un flux à utiliser pour écrire un flux de caractères Unicode dans le CLOB, en démarrant à la position donnée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public java.io.Writer setCharacterStream(long pos)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *bons de commande*  
  
 Position à laquelle démarrer l'écriture dans l'objet CLOB.  
  
## <a name="return-value"></a>Valeur retournée  
 Flux dans lequel les caractères chiffrés Unicode peuvent être écrits.  
  
## <a name="exceptions"></a>Exceptions  
 java.sql.SQLException  
  
## <a name="remarks"></a>Notes  
 Cette méthode setCharacterStream est spécifiée par la méthode setCharacterStream dans l’interface java.sql.Clob.  
  
 Les données de caractères dans le CLOB sont remplacées par l'enregistreur à partir de la position spécifiée et peuvent dépasser la longueur initiale du CLOB. La spécification d'une valeur position+1 permet d'ajouter des caractères. La spécification d'une valeur position+2 ou supérieure (ou de zéro ou d'une valeur inférieure) génère une erreur de position.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthodes SQLServerClob](../../../connect/jdbc/reference/sqlserverclob-methods.md)   
 [Membres de SQLServerClob](../../../connect/jdbc/reference/sqlserverclob-members.md)   
 [SQLServerClob, classe](../../../connect/jdbc/reference/sqlserverclob-class.md)  
  
  
