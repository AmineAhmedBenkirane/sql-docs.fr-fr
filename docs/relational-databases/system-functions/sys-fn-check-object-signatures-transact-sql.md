---
title: Sys.fn_check_object_signatures (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine, pdw
ms.service: 
ms.component: system-functions
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.fn_check_object_signatures_TSQL
- fn_check_object_signatures_TSQL
- fn_check_object_signatures
- sys.fn_check_object_signatures
dev_langs: TSQL
helpviewer_keywords: sys.fn_check_object_signatures function
ms.assetid: 47509566-d3d7-46a9-89c1-91b4895d56b9
caps.latest.revision: "15"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: b4f237723380c7220086f4b6642609f6e9177315
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="sysfncheckobjectsignatures-transact-sql"></a>sys.fn_check_object_signatures (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-pdw-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-pdw-md.md)]

  Retourne une liste de tous les objets signables et indique si un objet est signé par un certificat spécifié ou une clé asymétrique. Retourne également une valeur indiquant si la signature d'un objet est valide si l'objet est signé par le certificat spécifié ou une clé asymétrique.  
  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
fn_ check_object_signatures (   
    { '@class' } , { @thumbprint }   
  )   
```  
  
## <a name="arguments"></a>Arguments  
 {' @*classe*'}  
 Identifie le type d'empreinte numérique fourni :  
  
-   'certificate'  
  
-   'asymmetric key'  
  
 @*classe* est **sysname**.  
  
 {@*l’empreinte numérique* }  
 Hachage SHA-1 du certificat avec lequel la clé est chiffrée ou GUID de la clé asymétrique avec laquelle la clé est chiffrée. @*l’empreinte numérique* est **varbinary(20)**.  
  
## <a name="tables-returned"></a>Tables retournées  
 Le tableau suivant répertorie les colonnes qui **fn_check_object_signatures** retourne.  
  
|Colonne|Type| Description|  
|------------|----------|-----------------|  
|Type|**nvarchar(120)**|Retourne une description de type ou un assembly.|  
|entity_id|**int**|Retourne l'ID de l'objet en cours d'évaluation.|  
|is_signed|**int**|Retourne la valeur 0 lorsque l'objet n'est pas signé par l'empreinte numérique fournie. Retourne la valeur 1 lorsque l'objet est signé par l'empreinte numérique fournie.|  
|is_signature_valid|**int**|Lorsque is_signed a la valeur 1, retourne la valeur 0 lorsque la signature n'est pas valide. Retourne la valeur 1 lorsque la signature est valide.<br /><br /> Lorsque is_signed a la valeur 0, retourne toujours la valeur 0.|  
  
## <a name="remarks"></a>Notes  
 Utilisez **fn_check_object_signatures** pour confirmer que les utilisateurs malveillants n’ont pas falsifiés objets.  
  
## <a name="permissions"></a>Permissions  
 Nécessite l'autorisation VIEW DEFINITION sur le certificat ou la clé asymétrique.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant recherche le certificat de signature de schéma pour la base de données `master` et retourne la valeur 1 pour `is_signed` et la valeur 1 pour `is_signature_valid` pour les objets signés par le certificat de signature de schéma et dont les signatures sont valides.  
  
```  
USE master;  
-- Declare a variable to hold the thumbprint.  
DECLARE @thumbprint varbinary(20) ;  
-- Populate the thumbprint variable with the master database schema signing certificate.  
SELECT @thumbprint = thumbprint   
FROM sys.certificates   
WHERE name LIKE '%SchemaSigningCertificate%' ;  
-- Evaluates the objects signed by the schema signing certificate  
SELECT type, entity_id, OBJECT_NAME(entity_id) AS [object name], is_signed, is_signature_valid  
FROM sys.fn_check_object_signatures ('certificate', @thumbprint) ;  
GO  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [IS_OBJECTSIGNED &#40; Transact-SQL &#41;](../../t-sql/functions/is-objectsigned-transact-sql.md)  
  
  
