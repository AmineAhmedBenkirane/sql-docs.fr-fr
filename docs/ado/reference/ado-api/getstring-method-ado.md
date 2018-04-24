---
title: GetString, méthode (ADO) | Documents Microsoft
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
- Recordset20::raw_GetString
- Recordset20::GetString
helpviewer_keywords:
- GetString method [ADO]
ms.assetid: 92452940-b2a7-456e-94fc-3780c71da33c
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 9b877ee51cb85b10f1a59a56bce68529b41df029
ms.sourcegitcommit: bb044a48a6af9b9d8edb178dc8c8bd5658b9ff68
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="getstring-method-ado"></a>GetString, méthode (ADO)
Retourne le [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) sous forme de chaîne.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Variant = recordset.GetString(StringFormat, NumRows, ColumnDelimiter, RowDelimiter, NullExpr)  
```  
  
## <a name="return-value"></a>Valeur retournée  
 Retourne le **Recordset** comme une valeur de chaîne **Variant** (BSTR).  
  
#### <a name="parameters"></a>Paramètres  
 *StringFormat*  
 A [StringFormatEnum](../../../ado/reference/ado-api/stringformatenum.md) valeur qui spécifie comment la **Recordset** doit être convertie en une chaîne. Le *RowDelimiter*, *ColumnDelimiter*, et *NullExpr* paramètres sont utilisés uniquement avec un *StringFormat* de  **adClipString**.  
  
 *NumRows*  
 Ce paramètre est facultatif. Le nombre de lignes à convertir dans le **Recordset**. Si *NumRows* n’est pas spécifié, ou si elle est supérieure au nombre total de lignes dans le **Recordset**, puis toutes les lignes de la **Recordset** sont convertis.  
  
 *ColumnDelimiter*  
 Ce paramètre est facultatif. Un délimiteur utilisé entre les colonnes, si spécifié, sinon le caractère de tabulation.  
  
 *RowDelimiter*  
 Ce paramètre est facultatif. Délimiteur utilisé entre les lignes, dans le cas contraire, le caractère de retour chariot.  
  
 *NullExpr*  
 Ce paramètre est facultatif. Une expression utilisée à la place d’une valeur null, si spécifié, sinon retourne la chaîne vide.  
  
## <a name="remarks"></a>Notes  
 Données de ligne, mais aucune donnée de schéma, est enregistré dans la chaîne. Par conséquent, un **Recordset** ne peut pas être rouverte à l’aide de cette chaîne.  
  
 Cette méthode est équivalente à la RDO **GetClipString** (méthode).  
  
## <a name="applies-to"></a>S'applique à  
 [Recordset, objet (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>Voir aussi  
 [GetString, exemple de méthode (VB)](../../../ado/reference/ado-api/getstring-method-example-vb.md)
