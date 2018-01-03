---
title: "Contrôler le matériel à l’aide de la Console d’administration (système de plateforme Analytique)"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.prod: analytics-platform-system
ms.prod_service: mpp-data-warehouse
ms.service: 
ms.component: 
ms.technology: mpp-data-warehouse
ms.custom: 
ms.date: 01/05/2017
ms.reviewer: na
ms.suite: sql
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 294ba6ac-b1ff-46ea-ba32-d8b32cb4cdc2
caps.latest.revision: "26"
ms.openlocfilehash: db27003d4e1efd54a179551f585fb23ce9c0ed82
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="monitor-the-appliance-by-using-the-admin-console"></a>Contrôler le matériel à l’aide de la Console d’administration
La Console d’administration est une application web SQL Server PDW qui expose les informations d’état, l’intégrité et les performances de matériel. Les utilisateurs se connecter à la Console d’administration via Internet Explorer.  
  
## <a name="About"></a>Sur la Console d’administration  
![Accueil Console des appliances](./media/monitor-the-appliance-by-using-the-admin-console/SQL_Server_PDW_AdminConsol_ApplHome.png "SQL_Server_PDW_AdminConsol_ApplHome")  
  
**Équipement**  
Dossier de base  
Fournit un résumé de l’état de l’application.  
  
Contrôle d’intégrité  
Affiche la topologie d’appliances avec des indicateurs signalent l’état de chaque composant analysé dans chaque nœud. Vous permet d’afficher l’état actuel de nœuds individuels et les propriétés des composants du nœud.  
  
Affiche les alertes matérielles et logicielles.  
  
Analyseur de performances  
Affiche les graphiques d’analyse de performances.  
  
**Parallel Data Warehouse**  
Dossier de base  
Fournit un résumé de l’état PDW.  
  
Sessions  
Affiche les sessions utilisateur actives PDW. Cela peut permettre de surveillance de contention des ressources.  
  
Requêtes  
Affiche une liste de requêtes en cours d’exécution et récemment terminé. Il affiche les erreurs associées, le cas échéant. Fournit également la possibilité d’afficher les détails de requête d’exécution plan et nœud d’exécution.  
  
Charges  
Affiche de charger les plans, l’état actuel de la charge PDW et les erreurs associées, le cas échéant.  
  
Sauvegardes/restaurations  
Affiche le journal de PDW sauvegarde et de restauration.  
  
Contrôle d’intégrité  
Affiche la topologie PDW avec des indicateurs signalent l’état de chaque composant analysé dans chaque nœud. Vous permet d’afficher l’état actuel de nœuds individuels et les propriétés des composants du nœud.  
  
Affiche les alertes matérielles et logicielles.  
  
Ressources  
Affiche la liste des verrous de ressources PDW et leur état actuel.  
  
Stockage  
Résume l’utilisation du stockage PDW.  
  
Analyseur de performances  
Affiche les graphiques de moniteur de performances PDW.  
  
**HDInsight**  
Dossier de base  
Fournit un résumé de l’état de HDInsight.  
  
HDFS  
Récapitule l’utilisation de l’espace HDInsight et répertorie les principaux consommateurs de 10 espace.  
  
MapReduce  
Résume l’état des tâches MapReduce.  
  
Contrôle d’intégrité  
Affiche la topologie de HDInsight avec des indicateurs signalent l’état de chaque composant analysé dans chaque nœud. Vous permet d’afficher l’état actuel de nœuds individuels et les propriétés des composants du nœud.  
  
Affiche les alertes matérielles et logicielles.  
  
Stockage  
Résume l’utilisation du stockage de HDInsight.  
  
Analyseur de performances  
Affiche les graphiques d’analyse de performances.  
  
> [!NOTE]  
> La console d’administration a une résolution d’écran de 1024 x 768. La console d’administration affiche mieux avec une résolution d’écran de 1280 X 1024 ou plus.  
  
## <a name="Connect"></a>Se connecter à la Console d’administration  
Pour vous connecter à la Console d’administration requiert :  
  
-   Au moins Internet Explorer version 10.  
  
-   Autorisations d’accès de la Console d’administration. <!-- MISSING LINKS See [Grant Permissions to Use the Admin Console &#40;SQL Server PDW&#41;](../sqlpdw/grant-permissions-to-use-the-admin-console-sql-server-pdw.md).  -->  
  
-   L’adresse IP du cluster de nœud de contrôle.  Obtenir auprès de votre administrateur SQL Server PDW.  
  
Pour vous connecter à la Console d’administration, utilisez Internet Explorer et https pour accéder à l’adresse IP du cluster de nœud de contrôle. Par exemple, si l’adresse IP du cluster de nœud de contrôle est `10.192.63.102`, entrez `https://10.192.63.102` dans la barre d’adresse de votre navigateur. Le premier écran demande votre **connexion** et **mot de passe**. Fournissez soit un compte de connexion de l’authentification SQL Server et mot de passe, ou une connexion d’authentification Windows et mot de passe Windows. Si vous utilisez une connexion d’authentification Windows, la Console d’administration utilisera l’emprunt d’identité.  
  
## <a name="RelatedTasks"></a>Tâches de la Console d’administration  
La Console d’administration fournit la possibilité de contrôler les éléments suivants :  
  
|||  
|-|-|  
|**Type d’information**|**Accès dans la Console d’administration**|  
|État global de l’application|Cliquez sur **état des appliances** dans le menu supérieur, ou **accueil**.|  
|Alertes|Cliquez sur **alertes**. Pour plus d’informations, consultez [présentation des alertes de la Console Administration &#40; Système de plateforme Analytique &#41; ](understanding-admin-console-alerts.md).|  
|Composants d’application et leur état|Cliquez sur **état des appliances** dans le menu supérieur, ou **accueil**.|  
|Demandes d’analyse (y compris les requêtes, les charges, les sauvegardes et restaurations)|Cliquez sur **Sessions** pour afficher les sessions actuellement actives ou plus récentes.<br /><br />Cliquez sur **requêtes** pour afficher les requêtes actuellement actives ou plus récentes. Les informations affichées pour les requêtes incluent des charges, des sauvegardes et restaurations.<br /><br />Cliquez sur **verrous** pour afficher les verrous actifs.|  
|Analyser des informations supplémentaires pour les charges, les sauvegardes et restaurations.|Cliquez sur **charges** ou **sauvegardes/restaurations**.|  
|Informations sur les performances|Cliquez sur **l’Analyseur de performances**.|  
  
## <a name="see-also"></a>Voir aussi  
[Surveillance de l’appliance &#40; Système de plateforme Analytique &#41;](appliance-monitoring.md)  
  
