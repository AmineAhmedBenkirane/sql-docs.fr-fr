---
title: sp_add_category (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/06/2017
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
- sp_add_category
- sp_add_category_TSQL
dev_langs: TSQL
helpviewer_keywords: sp_add_category
ms.assetid: 6cca32cd-d941-4378-aed6-a7c90cb7520a
caps.latest.revision: "29"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: a180b1719f11b19097d2599847f1167f15ce7424
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="spaddcategory-transact-sql"></a>sp_add_category (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Ajoute la catégorie spécifiée de travaux, alertes ou opérateurs au serveur.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
sp_add_category   
     [ [ @class = ] 'class', ]   
     [ [ @type = ] 'type', ]   
     { [ @name = ] 'name' }  
```  
  
## <a name="arguments"></a>Arguments  
 [  **@class =** ] **'***classe***'**  
 Classe de la catégorie à ajouter. *classe* est **varchar(8)** avec une valeur par défaut du travail, et peut prendre l’une des valeurs suivantes.  
  
|Valeur| Description|  
|-----------|-----------------|  
|JOB|Ajoute une catégorie de travail.|  
|ALERT|Ajoute une catégorie d'alertes.|  
|OPERATOR|Ajoute une catégorie d'opérateurs.|  
  
 [  **@type =** ] **'***type***'**  
 Type de catégorie à ajouter. *type* est **varchar(12)**, avec la valeur par défaut **LOCAL**, et peut prendre l’une des valeurs suivantes.  
  
|Valeur| Description|  
|-----------|-----------------|  
|LOCAL|Catégorie de travaux locaux.|  
|PLUSIEURS SERVEURS|Une catégorie de travaux multiserveur.|  
|Aucune|Une catégorie d’une classe différente de JOB**.**|  
  
 [  **@name =** ] **'***nom***'**  
 Nom de la catégorie à ajouter. Le nom doit être unique dans la classe spécifiée. *nom* est **sysname**, sans valeur par défaut.  
  
## <a name="return-code-values"></a>Valeurs des codes de retour  
 **0** (réussite) ou **1** (échec)  
  
## <a name="result-sets"></a>Jeux de résultats  
 Aucune  
  
## <a name="remarks"></a>Notes  
 **sp_add_category** doit être exécuté à partir de la **msdb** base de données.  
  
## <a name="permissions"></a>Permissions  
 Seuls les membres de la **sysadmin** du rôle serveur fixe peuvent exécuter **sp_add_category**.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant crée une catégorie de travail local nommée `AdminJobs`.  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_add_category  
    @class=N'JOB',  
    @type=N'LOCAL',  
    @name=N'AdminJobs' ;  
GO  
```  
  
## <a name="see-also"></a>Voir aussi  
 [sp_delete_category &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-delete-category-transact-sql.md)   
 [sp_help_category &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-help-category-transact-sql.md)   
 [sp_update_category &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-update-category-transact-sql.md)   
 [dbo.sysjobs &#40; Transact-SQL &#41;](../../relational-databases/system-tables/dbo-sysjobs-transact-sql.md)   
 [dbo.sysjobservers &#40; Transact-SQL &#41;](../../relational-databases/system-tables/dbo-sysjobservers-transact-sql.md)   
 [Procédures stockées système &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
