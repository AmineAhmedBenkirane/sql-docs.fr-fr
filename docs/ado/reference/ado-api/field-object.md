---
title: Field, objet | Documents Microsoft
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- Field
helpviewer_keywords:
- Field object [ADO]
ms.assetid: b10a72fc-3c4b-4186-a70b-993dc9f7a092
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: f876e76b29dbc2436d6d1dba317c5035ebbc9ca1
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="field-object"></a>Objet Field
Représente une colonne de données avec un type de données commun.  
  
## <a name="remarks"></a>Notes  
 Chaque **champ** objet correspond à une colonne dans la [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md). Vous utilisez la [valeur](../../../ado/reference/ado-api/value-property-ado.md) propriété du **champ** objets pour définir ou retourner les données de l’enregistrement actif. Selon les fonctionnalités le fournisseur expose des regroupements, des méthodes ou propriétés d’un **champ** objet n’est peut-être pas disponible.  
  
 Avec les collections, les méthodes et les propriétés d’un **champ** de l’objet, vous pouvez procédez comme suit :  
  
-   Retourner le nom d’un champ de la [nom](../../../ado/reference/ado-api/name-property-ado.md) propriété.  
  
-   Afficher ou modifier les données dans le champ avec le **valeur** propriété. **Valeur** est la propriété par défaut de la **champ** objet.  
  
-   Retourner les caractéristiques de base d’un champ de la [Type](../../../ado/reference/ado-api/type-property-ado.md), [précision](../../../ado/reference/ado-api/precision-property-ado.md), et [NumericScale](../../../ado/reference/ado-api/numericscale-property-ado.md) propriétés.  
  
-   Renvoyer la taille déclarée d’un champ de la [DefinedSize](../../../ado/reference/ado-api/definedsize-property.md) propriété.  
  
-   Retourner la taille réelle des données dans un champ donné avec la [ActualSize](../../../ado/reference/ado-api/actualsize-property-ado.md) propriété.  
  
-   Déterminer les types de fonctionnalités sont prises en charge pour un champ donné avec la [attributs](../../../ado/reference/ado-api/attributes-property-ado.md) propriété et [propriétés](../../../ado/reference/ado-api/properties-collection-ado.md) collection.  
  
-   Manipuler les valeurs des champs contenant des données binaires longues ou caractères longs avec les [AppendChunk](../../../ado/reference/ado-api/appendchunk-method-ado.md) et [GetChunk](../../../ado/reference/ado-api/getchunk-method-ado.md) méthodes.  
  
-   Si le fournisseur prend en charge les mises à jour par lots, résoudre les différences dans les valeurs de champ au cours de la mise à jour par lot avec le [OriginalValue](../../../ado/reference/ado-api/originalvalue-property-ado.md) et [UnderlyingValue](../../../ado/reference/ado-api/underlyingvalue-property.md) propriétés.  
  
 Toutes les propriétés de métadonnées (**nom**, **Type**, **DefinedSize**, **précision**, et **NumericScale**) sont disponibles avant d’ouvrir le **champ** l’objet **Recordset**. Leur définition à ce stade est utile pour la construction dynamique des formulaires.  
  
 Cette section contient les rubriques suivantes.  
  
-   [Champ objet propriétés, méthodes et événements](../../../ado/reference/ado-api/field-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Collection de champs (ADO)](../../../ado/reference/ado-api/fields-collection-ado.md)   
 [Collection de propriétés (ADO)](../../../ado/reference/ado-api/properties-collection-ado.md)   
 [Objet Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)
