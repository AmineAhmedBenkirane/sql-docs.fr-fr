---
title: OPENROWSET (DMX) | Documents Microsoft
ms.custom: ''
ms.date: 03/02/2016
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: data-mining
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- OPENROWSET
dev_langs:
- DMX
helpviewer_keywords:
- OPENROWSET statement
ms.assetid: 8c8b61b4-2bf6-46c7-8976-51484004dc22
caps.latest.revision: 34
author: Minewiskan
ms.author: owend
manager: erikre
ms.openlocfilehash: 362d3ec30f8ec8eb2d5b9f21994454421f8ce816
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="ltsource-data-querygt---openrowset"></a>&lt;requête de source de données&gt; -OPENROWSET
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Remplace la requête de données source par une requête vers un fournisseur externe. Les instructions INSERT, SELECT FROM PREDICTION JOIN et SELECT FROM NATURAL PREDICTION JOIN prennent en charge **OPENROWSET**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
OPENROWSET(provider_name,provider_string,query_syntax)  
```  
  
## <a name="arguments"></a>Arguments  
 *provider_name*  
 Nom d'un fournisseur OLE DB  
  
 *provider_string*  
 Chaîne de connexion OLE DB pour le fournisseur spécifié.  
  
 *query_syntax*  
 Syntaxe de requête qui retourne un ensemble de lignes.  
  
## <a name="remarks"></a>Notes  
 Le fournisseur d’exploration de données établit une connexion à l’objet de source de données à l’aide de *Nom_Fournisseur* et *provider_string,* et s’exécute la requête spécifiée dans *query_syntax* pour récupérer l’ensemble de lignes à partir de la source de données.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant peut être utilisé au sein d'une instruction PREDICTION JOIN pour récupérer des données provenant de la base de données [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] à l'aide d'une instruction [!INCLUDE[tsql](../includes/tsql-md.md)] SELECT.  
  
```  
OPENROWSET  
(  
'SQLOLEDB.1',  
'Provider=SQLOLEDB.1;Integrated Security=SSPI;Persist Security     Info=False;Initial Catalog=AdventureWorksDW2012;Data Source=localhost',  
'SELECT TOP 1000 * FROM vTargetMail'  
)  
```  
  
## <a name="see-also"></a>Voir aussi  
 [&#60;requête de source de données&#62;](../dmx/source-data-query.md)   
 [Data Mining Extensions &#40;DMX&#41; instructions de Manipulation de données](../dmx/dmx-statements-data-manipulation.md)   
 [Les Extensions d’exploration de données & #40 ; DMX & #41 ; Référence des instructions](../dmx/data-mining-extensions-dmx-statements.md)  
  
  
