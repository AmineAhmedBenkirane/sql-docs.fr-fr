---
title: sp_helpreplicationoption (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- sp_helpreplicationoption
- sp_helpreplicationoption_TSQL
helpviewer_keywords:
- sp_helpreplicationoption
ms.assetid: ef988dbc-dd0b-4132-80ab-81eebec1cffe
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 378a931a86932be4535906f34432d2a4ea2356e9
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="sphelpreplicationoption-transact-sql"></a>sp_helpreplicationoption (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Indique les types des options de réplication activées pour un serveur. Cette procédure stockée est exécutée sur n'importe quelle base de données de n'importe quel serveur.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
sp_helpreplicationoption [ [ @optname =] 'option_name' ]  
```  
  
## <a name="arguments"></a>Arguments  
 [  **@optname =**] **'***option_name***'**  
 Nom de l'option de réplication pour laquelle effectuer la requête. *option_name* est **sysname**, avec NULL comme valeur par défaut.  
  
|Valeur| Description|  
|-----------|-----------------|  
|**transactionnelle**|Un ensemble de résultats est renvoyé lorsque la réplication transactionnelle est activée.|  
|**fusion**|Un ensemble de résultats est renvoyé lorsque la réplication de fusion est activée.|  
|NULL (par défaut)|Aucun ensemble de résultats n'est renvoyé.|  
  
## <a name="result-sets"></a>Jeux de résultats  
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**nom_option**|**sysname**|Nom de l'option de réplication ; il peut s’agir de l'une des options suivantes :<br /><br /> **transactionnelle**<br /><br /> **fusion**|  
|**valeur**|**bit**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**version_principale**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**version_secondaire**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**révision**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**install_failures**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
  
## <a name="return-code-values"></a>Valeurs des codes de retour  
 **0** (réussite) ou **1** (échec)  
  
## <a name="remarks"></a>Notes  
 **sp_helpreplicationoption** est utilisée pour obtenir plus d’informations sur les options de réplication activées sur un serveur particulier. Pour obtenir plus d’informations sur une base de données, utilisez **sp_helpreplicationdboption**.  
  
## <a name="permissions"></a>Permissions  
 Les autorisations d'exécution reviennent par défaut au rôle **public** .  
  
## <a name="see-also"></a>Voir aussi  
 [Procédures stockées système &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
