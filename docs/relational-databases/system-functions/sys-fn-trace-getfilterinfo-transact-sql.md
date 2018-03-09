---
title: sys.fn_trace_getfilterinfo (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- fn_trace_getfilterinfo
- fn_trace_getfilterinfo_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- status information [SQL Server], filters
- sys.fn_trace_getfilterinfo function
- filters [SQL Server], traces
- fn_trace_getfilterinfo function
ms.assetid: 09fe4a28-ff8a-4655-9da1-4654d5bc514d
caps.latest.revision: 
author: rothja
ms.author: jroth
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 1af9d4794d952e1ecb82e28a225e782039aff901
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2018
---
# <a name="sysfntracegetfilterinfo-transact-sql"></a>sys.fn_trace_getfilterinfo (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retourne des informations relatives aux filtres appliqués à une trace spécifiée.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] Utilisez plutôt des événements étendus.  
  
 
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
fn_trace_getfilterinfo ( trace_id )  
```  
  
## <a name="arguments"></a>Arguments  
 *trace_id*  
 Est l’ID de la trace. *l’argument trace_id* est **int**, sans valeur par défaut.  
  
## <a name="tables-returned"></a>Tables retournées  
 Retourne les informations suivantes. Pour plus d’informations sur les colonnes, consultez [sp_trace_setfilter &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql.md).  
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**columnid**|**int**|L’ID de la colonne sur laquelle le filtre est appliqué.|  
|**logical_operator**|**int**|Indique si l'opérateur AND ou OR est appliqué.|  
|**comparison_operator**|**int**|Spécifie le type de comparaison effectué :<br /><br /> 0 = Égal<br /><br /> 1 = Différent de<br /><br /> 2 = Supérieur à<br /><br /> 3 = Inférieur à<br /><br /> 4 = Supérieur ou égal à<br /><br /> 5 = Inférieur ou égal à<br /><br /> 6 = Identique<br /><br /> 7 = Non identique|  
|**valeur**|**sql_variant**|Indique la valeur sur laquelle le filtre est appliqué.|  
  
## <a name="remarks"></a>Notes  
 L’utilisateur définit *trace_id* valeur pour identifier, modifier et contrôler la trace. Lorsqu’il est passé de l’ID d’une trace spécifique, **fn_trace_getfilterinfo** retourne des informations sur n’importe quel filtre cette trace. Si la trace spécifiée n'a pas de filtre, cette fonction retourne un ensemble de lignes vide. Lorsqu'un identificateur non valide lui est passé, cette fonction renvoie un ensemble de lignes vide. Pour plus d’informations sur les traces, consultez [sys.fn_trace_getinfo &#40; Transact-SQL &#41; ](../../relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql.md).  
  
## <a name="permissions"></a>Autorisations  
 Nécessite l'autorisation ALTER TRACE sur le serveur.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant retourne des informations sur tous les filtres de la trace numéro 2.  
  
```  
SELECT * FROM fn_trace_getfilterinfo(2) ;  
GO  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Créer une trace &#40;Transact-SQL&#41;](../../relational-databases/sql-trace/create-a-trace-transact-sql.md)   
 [sp_trace_setfilter &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql.md)   
 [sp_trace_create &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-trace-create-transact-sql.md)   
 [sp_trace_generateevent &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-trace-generateevent-transact-sql.md)   
 [sp_trace_setevent &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql.md)   
 [sp_trace_setstatus &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql.md)   
 [sys.fn_trace_geteventinfo &#40;Transact-SQL&#41;](../../relational-databases/system-functions/sys-fn-trace-geteventinfo-transact-sql.md)   
 [sys.fn_trace_getinfo &#40;Transact-SQL&#41;](../../relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql.md)   
 [sys.fn_trace_gettable &#40;Transact-SQL&#41;](../../relational-databases/system-functions/sys-fn-trace-gettable-transact-sql.md)  
  
  
