---
title: PDO::Rollback | Documents Microsoft
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: ''
ms.component: php
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d918c1e3-1be0-4001-b3b0-000db6d9e8b8
caps.latest.revision: ''
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: bdb5d1e59e1b2d29225568abf53d3f6bf90d03d0
ms.sourcegitcommit: 2e130e9f3ce8a7ffe373d7fba8b09e937c216386
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="pdorollback"></a>PDO::Rollback
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Supprime les commandes de base de données qui ont été émises après avoir appelé [PDO::beginTransaction](../../connect/php/pdo-begintransaction.md) et rétablit la connexion en mode de validation automatique.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
bool PDO::rollBack ();  
```  
  
## <a name="return-value"></a>Valeur retournée  
La valeur est true si l’appel de méthode a réussi, false dans le cas contraire.  
  
## <a name="remarks"></a>Notes  
PDO::ROLLBACK n’est pas affecté par (et n’affecte pas) la valeur de PDO::ATTR_AUTOCOMMIT.  
  
Consultez [PDO::beginTransaction](../../connect/php/pdo-begintransaction.md) pour obtenir un exemple qui utilise PDO::rollback.  
  
La prise en charge de PDO a été ajoutée dans la version 2.0 de [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
[Classe PDO](../../connect/php/pdo-class.md)

[PDO](http://php.net/manual/book.pdo.php)  
  
