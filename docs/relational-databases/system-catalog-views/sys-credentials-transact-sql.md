---
title: Sys.Credentials (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 02/27/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.credentials
- sys.credentials_TSQL
- credentials_TSQL
- credentials
dev_langs: TSQL
helpviewer_keywords: sys.credentials catalog view
ms.assetid: ea48cf80-904a-4273-a950-6d35b1b0a1b6
caps.latest.revision: "33"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: bf03ffcc4dffb40aa53aff24d67e12487f3d069b
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="syscredentials-transact-sql"></a>sys.credentials (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2008-xxxx-asdw-pdw-md.md)]

  Retourne une ligne pour chaque information d’identification au niveau du serveur.  
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|credential_id|**int**|ID de l'information d'identification. Unique dans le serveur.|  
|name|**sysname**|Nom de l'information d'identification. Unique dans le serveur.|  
|credential_identity|**nvarchar(4000)**|Nom de l'identité à utiliser. Il s'agit généralement d'un utilisateur Windows. Il n'est pas nécessaire qu'elle soit unique.|  
|create_date|**datetime**|Heure de création de l'information d'identification.|  
|modify_date|**datetime**|Heure de la dernière modification de l'information d'identification.|  
|target_type|**nvarchar (100)**|Type d'information d'identification. Retourne NULL pour des informations d'identification traditionnelles, CRYPTOGRAPHIC PROVIDER pour des informations d'identification mappées à un fournisseur de chiffrement. Pour plus d’informations sur les fournisseurs de gestion de clés externes, consultez [gestion de clés Extensible &#40; Gestion de clés extensible &#41; ](../../relational-databases/security/encryption/extensible-key-management-ekm.md).|  
|target_id|**int**|ID de l'objet auquel l'information d'identification est mappée. Retourne 0 pour des informations d'identification traditionnelles, et une valeur différente de 0 pour des informations d'identification mappées à un fournisseur de chiffrement. Pour plus d’informations sur les fournisseurs de gestion de clés externes, consultez [gestion de clés Extensible &#40; Gestion de clés extensible &#41; ](../../relational-databases/security/encryption/extensible-key-management-ekm.md).|  

## <a name="remarks"></a>Notes  
Pour plus d’informations d’identification de niveau base de données, consultez [sys.database_scoped_credentials](../../relational-databases/system-catalog-views/sys-database-scoped-credentials-transact-sql.md).
  
## <a name="permissions"></a>Permissions  
 Nécessite soit `VIEW ANY DEFINITION` autorisation ou `ALTER ANY CREDENTIAL` autorisation. En outre, l’entité de sécurité ne doit pas être refusée `VIEW ANY DEFINITION` autorisation.  
  
## <a name="see-also"></a>Voir aussi  
 [Sys.database_scoped_credentials](../../relational-databases/system-catalog-views/sys-database-scoped-credentials-transact-sql.md)   
 [Informations d’identification &#40; moteur de base de données &#41;](../../relational-databases/security/authentication-access/credentials-database-engine.md)   
 [Affichages catalogue de sécurité &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/security-catalog-views-transact-sql.md)   
 [Principaux &#40;moteur de base de données&#41;](../../relational-databases/security/authentication-access/principals-database-engine.md)   
 [CREATE CREDENTIAL &#40;Transact-SQL&#41;](../../t-sql/statements/create-credential-transact-sql.md)  
  
  
