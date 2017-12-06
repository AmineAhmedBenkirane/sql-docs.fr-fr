---
title: sp_polybase_join_group | Documents Microsoft
ms.custom: 
ms.date: 05/24/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: sp_polybase_join_group
helpviewer_keywords: PolyBase
ms.assetid: 48066431-fed2-4a8a-85af-ac704689e183
caps.latest.revision: "12"
author: CarlRabeler
ms.author: carlrab
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: d5c9529c61e5f89b5bf049b36279cb8b7611af60
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="polybase-stored-procedures---sppolybasejoingroup"></a>Procédures stockées PolyBase - sp_polybase_join_group
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  Ajoute une instance de SQL Server comme nœud de calcul à un groupe PolyBase pour le calcul de la montée en puissance parallèle.  
  
 L’instance de SQL Server doit posséder le [PolyBase](../../relational-databases/polybase/polybase-guide.md) fonctionnalité installée.  PolyBase permet l’intégration de sources de données non SQL Server, tels que le stockage blob Hadoop et Azure. Voir aussi [sp_polybase_leave_group &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/polybase-stored-procedures-sp-polybase-leave-group.md).  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
sp_polybase_join_group (@head_node_address = N'head_node_address',  
    @dms_control_channel_port = dms_control_channel_port,  
    @head_node_sql_server_instance_name = head_node_sql_server_instance_name)  
[ ; ]          
```  
  
## <a name="arguments"></a>Arguments  
 *@head_node_address*= N'*head_node_address*'  
 Le nom de l’ordinateur qui héberge le nœud principal de SQL Server du groupe de montée en puissance parallèle PolyBase. *@head_node_address*est nvarchar (255).  
  
 *@dms_control_channel_port*= dms_control_channel_port  
 Le port sur lequel le canal de contrôle pour le nœud principal PolyBase Data Movement Service s’exécute. *@dms_control_channel_port*est un __int16 non signé. La valeur par défaut est **16450**.  
  
 *@head_node_sql_server_instance_name*= head_node_sql_server_instance_name  
 Le nom de l’instance de SQL Server de nœud principal dans le groupe de scale-out PolyBase. *@head_node_sql_server_instance_name*est nvarchar(16).  
  
## <a name="return-code-values"></a>Valeurs des codes de retour  
 0 (réussite) ou 1 (échec)  
  
## <a name="permissions"></a>Permissions  
 Requiert l'autorisation CONTROL SERVER.  
  
## <a name="remarks"></a>Notes  
 Après avoir exécuté la procédure stockée, arrêter le moteur PolyBase et redémarrez le Service de déplacement de données PolyBase sur l’ordinateur. Pour vérifier s’exécutent de la DMV suivante sur le nœud principal : **sys.dm_exec_compute_nodes**.  
  
## <a name="example"></a>Exemple  
 L’exemple joint l’ordinateur actuel comme nœud de calcul à un groupe PolyBase.  Le nom du nœud principal est **HST01** et le nom de l’instance de SQL Server sur le nœud principal est **MSSQLSERVER**.  
  
```  
EXEC sp_polybase_join_group N'HST01', 16450, N'MSSQLSERVER'   
```  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en main de PolyBase](../../relational-databases/polybase/get-started-with-polybase.md)   
 [Procédures stockées système &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  