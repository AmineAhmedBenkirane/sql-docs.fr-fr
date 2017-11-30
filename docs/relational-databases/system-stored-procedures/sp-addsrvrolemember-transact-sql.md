---
title: sp_addsrvrolemember (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/20/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_addsrvrolemember
- sp_addsrvrolemember_TSQL
dev_langs: TSQL
helpviewer_keywords: sp_addsrvrolemember
ms.assetid: 777f0e09-8ee5-4cb2-a3ac-939d02c3cd22
caps.latest.revision: "32"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: c8159218d405cbd09861938393fd054ab8aea6e9
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/27/2017
---
# <a name="spaddsrvrolemember-transact-sql"></a>sp_addsrvrolemember (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Ajoute une connexion à un membre d'un rôle serveur fixe.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]Utilisez [ALTER SERVER ROLE](../../t-sql/statements/alter-server-role-transact-sql.md) à la place.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
sp_addsrvrolemember [ @loginame= ] 'login'   
    , [ @rolename = ] 'role'  
```  
  
## <a name="arguments"></a>Arguments  
 [ @loginame  **=**  ] **'***connexion***'**  
 Nom de la connexion ajoutée au rôle serveur fixe. *connexion* est **sysname**, sans valeur par défaut. *connexion* peut être un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connexion ou une connexion Windows. Si la connexion Windows n'a pas encore été autorisée à accéder à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], elle l'est automatiquement.  
  
 [ @rolename  **=**  ] **'***rôle***'**  
 Nom du rôle serveur fixe auquel est ajoutée la connexion. *rôle* est **sysname**, avec NULL comme valeur par défaut et doit être une des valeurs suivantes :  
  
-   sysadmin  
  
-   securityadmin  
  
-   serveradmin  
  
-   setupadmin  
  
-   processadmin  
  
-   diskadmin  
  
-   dbcreator  
  
-   bulkadmin  

## <a name="return-code-values"></a>Valeurs des codes de retour  
 0 (réussite) ou 1 (échec)  
  
## <a name="remarks"></a>Notes  
 Lorsque vous ajoutez une connexion à un rôle serveur fixe, la connexion obtient les autorisations associées à ce rôle.  
  
 Impossible de modifier l’appartenance au rôle de la connexion sa et publics.  
  
 Utilisez sp_addrolemember pour ajouter un membre à une base de données fixe ou d’un rôle défini par l’utilisateur.  
  
 sp_addsrvrolemember ne peut pas être exécutée dans une transaction définie par l’utilisateur.  
  
## <a name="permissions"></a>Permissions  
 Il faut appartenir au rôle auquel le nouveau membre est ajouté.  
  
## <a name="examples"></a>Exemples  
 L’exemple suivant ajoute la connexion Windows `Corporate\HelenS` à la `sysadmin` rôle serveur fixe.  
  
```  
EXEC sp_addsrvrolemember 'Corporate\HelenS', 'sysadmin';  
GO  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité stockée procédures &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)   
 [sp_addrolemember &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addrolemember-transact-sql.md)   
 [sp_dropsrvrolemember &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-dropsrvrolemember-transact-sql.md)   
 [Procédures stockées système &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [Fonctions de sécurité &#40;Transact-SQL&#41;](../../t-sql/functions/security-functions-transact-sql.md)   
 [CRÉER le rôle de serveur &#40; Transact-SQL &#41;](../../t-sql/statements/create-server-role-transact-sql.md)   
 [DROP SERVER ROLE &#40;Transact-SQL&#41;](../../t-sql/statements/drop-server-role-transact-sql.md)  
  
  
