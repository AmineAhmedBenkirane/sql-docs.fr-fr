---
title: MoveRecordOptionsEnum | Documents Microsoft
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
- MoveRecordOptionsEnum
helpviewer_keywords:
- MoveRecordOptionsEnum enumeration [ADO]
ms.assetid: f53c2ce4-1021-4a45-92b8-775e8bebad99
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 5989991d5ca7001173790f9bfe00b6adee10e6da
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="moverecordoptionsenum"></a>MoveRecordOptionsEnum
Spécifie le comportement de la [enregistrement](../../../ado/reference/ado-api/record-object-ado.md) objet [MoveRecord](../../../ado/reference/ado-api/moverecord-method-ado.md) (méthode).  
  
|Constante|Valeur| Description|  
|--------------|-----------|-----------------|  
|**adMoveUnspecified**|-1|Valeur par défaut. Effectue l’opération de déplacement par défaut : l’opération échoue si le fichier de destination ou le répertoire existe déjà, et l’opération met à jour les liens hypertexte.|  
|**adMoveOverWrite**|1|Remplace le fichier de destination ou le répertoire, même si elle existe déjà.|  
|**adMoveDontUpdateLinks**|2|Modifie le comportement par défaut de **MoveRecord** méthode à mettre à jour les liens hypertexte de la source de **enregistrement**. Le comportement par défaut varie selon les capacités du fournisseur. Opération de déplacement met à jour les liens si le fournisseur est compatible. Si le fournisseur ne peut pas résoudre les liens ou si cette valeur n’est pas spécifiée, le déplacement réussit même lorsque des liens n'ont pas été résolus.|  
|**adMoveAllowEmulation**|4|Demande que le fournisseur de tenter de simuler le déplacement (à l’aide de téléchargement, de téléchargement et d’opérations de suppression). Si la tentative de déplacement le **enregistrement** échoue parce que l’URL de destination se trouve sur un autre serveur ou la prise en charge par un fournisseur autre que la source, cela peut entraîner accrue latence ou perte de données, en raison des fonctionnalités d’un fournisseur différent lorsque déplacement de ressources entre les fournisseurs.|  
  
## <a name="adowfc-equivalent"></a>ADO/WFC équivalent  
 Ces constantes n’ont pas d’équivalents ADO/WFC.  
  
## <a name="applies-to"></a>S'applique à  
 [MoveRecord, méthode (ADO)](../../../ado/reference/ado-api/moverecord-method-ado.md)
