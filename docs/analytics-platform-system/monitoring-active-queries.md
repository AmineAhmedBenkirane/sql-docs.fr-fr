---
title: "Analyse des requêtes actives (SQL Server PDW)"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.prod: analytics-platform-system
ms.prod_service: mpp-data-warehouse
ms.service: 
ms.component: 
ms.technology: mpp-data-warehouse
ms.custom: 
ms.date: 01/13/2017
ms.reviewer: na
ms.suite: sql
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: bb73f790-0537-414b-8dc2-f1eb69b92362
caps.latest.revision: "7"
ms.openlocfilehash: 44f128124c8027bf4c37e34309d6c711006ac113
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="monitoring-active-queries"></a>Analyse des requêtes actives
Cette rubrique montre comment utiliser la Console d’administration et les vues système SQL Server PDW pour surveiller les requêtes actives. Consultez [contrôler le matériel à l’aide de la Console d’administration](monitor-the-appliance-by-using-the-admin-console.md) et [vues système](tsql-system-views.md) pour plus d’informations sur ces outils.  
  
## <a name="prerequisites"></a>Prerequisites  
Quelle que soit la méthode utilisée pour surveiller les requêtes actives, la connexion doit avoir les autorisations décrites dans « Utiliser tous les de la Console d’administration » dans [accorder des autorisations pour utiliser la Console d’administration](grant-permissions.md#grant-permissions-to-use-the-admin-console).  
  
## <a name="PermsAdminConsole"></a>Analyse des requêtes actives  
La Console d’administration et les vues système SQL Server PDW peuvent être utilisés pour surveiller les requêtes actives. Suivez les instructions ci-dessous.  
  
### <a name="to-monitor-active-queries-by-using-the-admin-console"></a>Pour surveiller les requêtes actives à l’aide de la Console d’administration  
  
1.  Ouvrez une session sur la Console d’administration. Consultez [contrôler le matériel à l’aide de la Console d’administration](monitor-the-appliance-by-using-the-admin-console.md) pour obtenir des instructions.  
  
2.  Dans le menu supérieur, cliquez sur **requêtes**. Vous verrez une table avec les informations de base sur les requêtes les plus récentes sur le matériel, y compris la connexion qui a envoyé la requête, les heures de début et de fin pour la requête et l’état actuel de la requête.  
  
3.  Pour afficher la commande de requête, placez le pointeur de la souris sur l’ID de requête dans la colonne de gauche pour cette ligne.  
  
    Pour plus d’informations pour une requête particulière, cliquez sur l’ID de requête. Vous verrez des informations, notamment la requête complète et le plan de requête avec les informations d’état pour chaque étape de l’exécution de la requête. Si des erreurs ont été retournés, vous pouvez également voir des informations détaillées sur les erreurs. <!-- MISSING LINKS See [Understanding Query Plans &#40;SQL Server PDW&#41;](../sqlpdw/understanding-query-plans-sql-server-pdw.md) for information on how to interpret the query plan information available in the Admin Console.  -->
  
### <a name="to-monitor-active-queries-by-using-the-system-views"></a>Pour analyser des requêtes actives en utilisant les vues système  
La vue système principal utilisée pour surveiller les requêtes est [sys.dm_pdw_exec_requests](../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-requests-transact-sql.md). Utilisez cette vue système pour rechercher le `request_id` pour une requête active ou récente, basée sur le texte de requête.  
  
Par exemple, la requête suivante recherche le `request_id` et actuel `status` pour toute requête qui sélectionne toutes les colonnes à partir de la `memberAddresses` table.  
  
```sql  
SELECT request_id, command, status   
FROM sys.dm_pdw_exec_requests   
WHERE command   
LIKE ‘%SELECT * FROM db1..memberAddresses%’;  
```  
  
Après le `request_id` a été identifiée pour une requête, utilisez les autres informations contenues dans le `dm_pdw_exec_requests` pour trouver des informations sur le traitement de la requête de table, ou utilisez [sys.dm_pdw_request_steps](../relational-databases/system-dynamic-management-views/sys-dm-pdw-request-steps-transact-sql.md) pour afficher l’état de la requête individuelle étapes pour l’exécution de la requête.  
  
<!-- MISSING LINKS 
## See Also  
[Common Metadata Query Examples &#40;SQL Server PDW&#41;](../sqlpdw/common-metadata-query-examples-sql-server-pdw.md)  
-->
  
