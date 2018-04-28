---
title: sqlsrv_configure | Documents Microsoft
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: php
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
apiname:
- sqlsrv_configure
apitype: NA
helpviewer_keywords:
- sqlsrv_configure
- API Reference, sqlsrv_configure
ms.assetid: 9393f975-a4ef-4c50-b4dd-14892fc55cc9
caps.latest.revision: 20
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: d3481148dada17e1dcd5faa42cc52c47716cfe75
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="sqlsrvconfigure"></a>sqlsrv_configure
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Modifie les paramètres de gestion des erreurs et les options de journalisation.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
sqlsrv_configure( string $setting, mixed $value )  
```  
  
#### <a name="parameters"></a>Paramètres  
*$setting*: nom du paramètre à configurer. Consultez le tableau ci-dessous pour obtenir la liste de paramètres.  
  
*$value*: valeur à appliquer au paramètre spécifié dans le paramètre *$setting* . Les valeurs possibles pour ce paramètre dépendent du paramètre spécifié. Le tableau suivant répertorie les combinaisons possibles :  
  
|Paramètre|Valeurs possibles pour le paramètre $value (entier équivalent entre parenthèses)|Valeur par défaut|  
|-----------|------------------------------------------------------------------------------|-----------------|  
|ClientBufferMaxKBSize<sup>1</sup>|Nombre non négatif jusqu’à la limite de mémoire PHP.<br /><br />Zéro (0) signifie que la taille de la mémoire tampon est illimitée.|10240|  
|LogSeverity<sup>2</sup>|SQLSRV_LOG_SEVERITY_ALL (-1)<br /><br />SQLSRV_LOG_SEVERITY_ERROR (1)<br /><br />SQLSRV_LOG_SEVERITY_NOTICE (4)<br /><br />SQLSRV_LOG_SEVERITY_WARNING (2)|SQLSRV_LOG_SEVERITY_ERROR (1)|  
|LogSubsystems<sup>2</sup>|SQLSRV_LOG_SYSTEM_ALL (-1)<br /><br />SQLSRV_LOG_SYSTEM_CONN (2)<br /><br />SQLSRV_LOG_SYSTEM_INIT (1)<br /><br />SQLSRV_LOG_SYSTEM_OFF (0)<br /><br />SQLSRV_LOG_SYSTEM_STMT (4)<br /><br />SQLSRV_LOG_SYSTEM_UTIL (8)|SQLSRV_LOG_SYSTEM_OFF (0)|  
|WarningsReturnAsErrors<sup>3</sup>|**true** (1) ou **false** (0)|**true** (1)|  
  
## <a name="return-value"></a>Valeur retournée  
Si **sqlsrv_configure** est appelé avec un paramètre ou une valeur non pris en charge, la fonction retourne **false**. Sinon, elle retourne **true**.  
  
## <a name="remarks"></a>Notes  
(1) pour plus d’informations sur les requêtes côté client, consultez [Types de curseurs &#40;pilote SQLSRV&#41;](../../connect/php/cursor-types-sqlsrv-driver.md).  
  
(2) pour plus d’informations sur la journalisation de l’activité, consultez [enregistrement de l’activité](../../connect/php/logging-activity.md).  
  
(3) pour plus d’informations sur la configuration d’erreur et gestion d’avertissement, consultez [Comment : configurer l’avertissement gestion des erreurs et l’utilisation du pilote SQLSRV](../../connect/php/how-to-configure-error-and-warning-handling-using-the-sqlsrv-driver.md).  
  
## <a name="see-also"></a>Voir aussi  
[Informations de référence sur l’API du pilote SQLSRV](../../connect/php/sqlsrv-driver-api-reference.md)

[Guide de programmation pour les pilotes Microsoft pour PHP pour SQL Server](../../connect/php/programming-guide-for-php-sql-driver.md) 
  
