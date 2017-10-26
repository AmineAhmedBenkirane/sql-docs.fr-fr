---
title: "setBytes (méthode) (long, byte) | Documents Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- SQLServerBlob.setBytes (long.byte[])
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: ffb8f107-0f9d-4410-957f-62b718e1e872
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 75886137dd2d8ac768dff35d3cf6bb9a7100efeb
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="setbytes-method-long-byte"></a>setBytes (long, byte) (méthode)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Enregistre le tableau d'octets spécifié dans le BLOB, en démarrant à la position spécifiée, puis retourne le nombre d'octets écrits.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
public int setBytes(long pos,  
                    byte[] bytes)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *bons de commande*  
  
 Position (base 1) dans le BLOB à laquelle démarrer l'écriture des données.  
  
 *octets*  
  
 Tableau d'octets à écrire dans le BLOB.  
  
## <a name="return-value"></a>Valeur retournée  
 A **long** valeur qui spécifie le nombre d’octets écrits.  
  
## <a name="exceptions"></a>Exceptions  
 java.sql.SQLException  
  
## <a name="remarks"></a>Notes  
 Cette méthode setBytes est spécifiée par la méthode setBytes dans l’interface java.sql.Blob.  
  
 Les données sont remplacées à partir de la position spécifiée et peuvent dépasser la longueur initiale du BLOB. La spécification d'une valeur position+1 permet d'ajouter des octets. Le passage d'une valeur position+2 ou supérieure (ou inférieure ou égale à zéro) génère une erreur de position. Passage d’une longueur nulle **octets** tableau retourne zéro car aucun octet n’a été écrit.  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode setBytes &#40; SQLServerBlob &#41;](../../../connect/jdbc/reference/setbytes-method-sqlserverblob.md)   
 [Méthodes SQLServerBlob](../../../connect/jdbc/reference/sqlserverblob-methods.md)   
 [Membres de SQLServerBlob](../../../connect/jdbc/reference/sqlserverblob-members.md)   
 [SQLServerBlob, classe](../../../connect/jdbc/reference/sqlserverblob-class.md)  
  
  

