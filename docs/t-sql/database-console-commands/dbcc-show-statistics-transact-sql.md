---
title: DBCC SHOW_STATISTICS (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 07/17/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SHOW_STATISTICS_TSQL
- DBCC SHOW_STATISTICS
- SHOW_STATISTICS
- DBCC_SHOW_STATISTICS_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- query optimization statistics [SQL Server], densities
- histograms [SQL Server]
- statistical information [SQL Server], viewing statistics objects
- current distribution statistics
- query optimization statistics [SQL Server], histograms
- DBCC SHOW_STATISTICS statement
- distribution statistics
- statistical information [SQL Server], densities
- statistics objects
- statistical information [SQL Server], histograms
- query optimization statistics [SQL Server], viewing statistics objects
- statistical information [SQL Server], distribution
- densities [SQL Server]
- displaying distribution statistics
ms.assetid: 12be2923-7289-4150-b497-f17e76a50b2e
caps.latest.revision: 75
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Active
ms.translationtype: MT
ms.sourcegitcommit: 77c7eb1fcde9b073b3c08f412ac0e46519763c74
ms.openlocfilehash: 38abfb552f1bb969c132d5086ca007d36541a76c
ms.contentlocale: fr-fr
ms.lasthandoff: 10/17/2017

---
# <a name="dbcc-showstatistics-transact-sql"></a>DBCC SHOW_STATISTICS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

DBCC SHOW_STATISTICS affiche les statistiques d'optimisation de la requête actuelle pour une table ou une vue indexée. L'optimiseur de requête utilise des statistiques pour estimer le nombre de lignes, également appelé cardinalité, dans le résultat de la requête, ce qui lui permet de créer un plan de requête de haute qualité. Par exemple, l'optimiseur de requête pourrait utiliser des estimations de cardinalité afin de choisir l'opérateur de recherche d'index plutôt que l'opérateur d'analyse d'index dans le plan de requête. Cela permettrait d'améliorer les performances des requêtes car le recours à une analyse d'index monopolisant de nombreuses ressources serait ainsi évité.
  
L'optimiseur de requête stocke des statistiques pour une table ou vue indexée dans un objet des statistiques. Pour une table, l'objet des statistiques est créé sur un index ou sur une liste de colonnes de table. L'objet des statistiques inclut un en-tête contenant des métadonnées sur les statistiques, un histogramme indiquant la distribution des valeurs dans la première colonne clé de l'objet des statistiques, et un vecteur de densité destiné à mesurer la corrélation entre les colonnes. Le [!INCLUDE[ssDE](../../includes/ssde-md.md)] peut calculer des estimations de cardinalité avec les données dans l’objet de statistiques.
  
DBCC SHOW_STATISTICS affiche l'en-tête, l'histogramme et le vecteur de densité en fonction des données stockées dans l'objet des statistiques. La syntaxe vous permet de spécifier une table ou une vue indexée ainsi qu’un nom d'index cible, un nom de statistique ou un nom de colonne. Cette rubrique explique comment afficher les statistiques et comment comprendre les résultats affichés.
  
Pour plus d'informations, consultez [Statistics](../../relational-databases/statistics/statistics.md).
  
![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntaxe  
  
```
-- Syntax for SQL Server and Azure SQL Database  
  
DBCC SHOW_STATISTICS ( table_or_indexed_view_name , target )   
[ WITH [ NO_INFOMSGS ] < option > [ , n ] ]  
< option > :: =  
    STAT_HEADER | DENSITY_VECTOR | HISTOGRAM | STATS_STREAM  
```  
  
```
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  

DBCC SHOW_STATISTICS ( table_name , target )   
    [ WITH {STAT_HEADER | DENSITY_VECTOR | HISTOGRAM } [ ,...n ] ]  
[;]  
```  
  
## <a name="arguments"></a>Arguments  
 *table_or_indexed_view_name*  
 Nom de la table ou de la vue indexée dont les informations statistiques doivent être affichées.  
  
 *table_name*  
 Nom de la table qui contient les statistiques à afficher. La table ne peut pas être une table externe.  
  
 *cible*  
 Nom de l'index, de la statistique ou de la colonne dont les informations statistiques doivent être affichées. *cible* est placé entre crochets, unique guillemets doubles, des guillemets ou des guillemets non. Si *cible* est un nom d’un index existant ou des statistiques sur une table ou une vue indexée, les informations statistiques concernant cette cible sont retournée. Si *cible* est le nom d’une colonne existante, et il existe un statistiques créées automatiquement sur cette colonne, plus d’informations sur cette statistique créée automatiquement sont retournés. S'il n'existe pas de statistique créée automatiquement pour une cible de colonne, le message d'erreur 2767 est retourné.  
 Dans [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] et [!INCLUDE[ssPDW](../../includes/sspdw-md.md)], *cible* ne peut pas être un nom de colonne.  
  
 NO_INFOMSGS  
 Supprime tous les messages d'information dont les niveaux de gravité sont compris entre 0 et 10.  
  
 STAT_HEADER | DENSITY_VECTOR | HISTOGRAMME | STATS_STREAM [ **,**  *n*  ]  
 La spécification d'une ou de plusieurs de ces options limite les jeux de résultats retournés par l'instruction aux options spécifiées. Si aucune option n'est spécifiée, toutes les informations statistiques sont retournées.  
  
 STATS_STREAM est [!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]  
  
## <a name="result-sets"></a>Jeux de résultats  
Le tableau suivant décrit les colonnes retournées dans le jeu de résultats lorsque STAT_HEADER est spécifié.
  
|Nom de colonne| Description|  
|-----------------|-----------------|  
|Nom|Nom de l'objet de statistiques.|  
|Mis à jour|Date et heure de la dernière mise à jour des statistiques. Le [STATS_DATE](../../t-sql/functions/stats-date-transact-sql.md) fonction est une autre manière de récupérer ces informations.|  
|Lignes|Nombre total de lignes dans la table ou la vue indexée au moment de la dernière mise à jour des statistiques. Si les statistiques sont filtrées ou correspondent à un index filtré, le nombre de lignes peut être inférieur à celui de la table. Pour plus d’informations, consultez[statistiques](../../relational-databases/statistics/statistics.md).|  
|Lignes échantillonnées|Nombre total de lignes échantillonnées pour le calcul des statistiques. Si Rows Sampled < Rows, l'histogramme et les résultats de densité affichés sont des estimations basées sur les lignes échantillonnées.|  
|Étapes|Nombre d'étapes dans l'histogramme. Chaque étape couvre une plage de valeurs de colonnes suivie d'une valeur de colonne de limite supérieure. Les étapes d'histogramme sont définies sur la première colonne clé des statistiques. Le nombre maximal d'étapes est 200.|  
|Densité|La formule 1 / *valeurs distinctes* est utilisée pour toutes les valeurs de la première colonne clé de l’objet de statistiques, à l’exception des valeurs limites de l’histogramme. Cette valeur Density n'est pas utilisée par l'optimiseur de requête ; elle est affichée pour la compatibilité descendante avec les versions antérieures à [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].|  
|Longueur moyenne d'une clé|Nombre moyen d'octets par valeur pour toutes les colonnes clés de l'objet de statistiques.|  
|String Index|La valeur Yes indique que l'objet de statistiques contient des statistiques de résumé de chaîne pour améliorer les estimations de cardinalité des prédicats de requête qui utilisent l'opérateur LIKE ; c'est le cas par exemple de `WHERE ProductName LIKE '%Bike'`. Chaîne des statistiques de synthèse sont stockés séparément à partir de l’histogramme et sont créées sur la première colonne de clé de l’objet de statistiques lorsqu’il est de type **char**, **varchar**, **nchar**, **nvarchar**, **varchar (max)**, **nvarchar (max)**, **texte**, ou **ntext.**.|  
|Expression de filtre|Prédicat pour le sous-ensemble des lignes de table incluses dans l'objet de statistiques. NULL = statistiques non filtrées. Pour plus d’informations sur les prédicats filtrés, consultez [Create Filtered Indexes](../../relational-databases/indexes/create-filtered-indexes.md). Pour plus d’informations sur les statistiques filtrées, consultez [statistiques](../../relational-databases/statistics/statistics.md).|  
|Lignes non filtrées|Nombre total de lignes dans la table avant l'application de l'expression de filtre. Si Expression de filtre a la valeur NULL, Lignes non filtrées est égal à Lignes.|  
|Rendu persistant pour cent d’exemple|Persistante pourcentage d’échantillonnage destinée mises à jour des statistiques qui ne spécifient pas explicitement un pourcentage d’échantillonnage. Si la valeur est zéro, aucun pourcentage exemple persistante n’est définie pour cette statistique.<br /><br /> **S’applique à :** [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] SP1 CU4| 
  
Le tableau suivant décrit les colonnes retournées dans le jeu de résultats lorsque DENSITY_VECTOR est spécifié.
  
|Nom de colonne| Description|  
|-----------------|-----------------|  
|Toutes les densités|La densité est calculée selon la formule 1 / *valeurs distinctes*. Les résultats affichent la densité pour chaque préfixe des colonnes de l'objet de statistiques, à raison d'une ligne par densité. Une valeur distincte est une liste distincte des valeurs de colonnes par ligne et par préfixe de colonne. Par exemple, si l'objet de statistiques contient des colonnes clés (A, B, C), les résultats affichent la densité des listes distinctes de valeurs dans chacun des préfixes de colonnes suivants : (A), (A,B) et (A, B, C). Avec le préfixe (A, B, C), chacune des listes suivantes est une liste de valeurs distincte : (3, 5, 6), (4, 4, 6), (4, 5, 6), (4, 5, 7). Avec le préfixe (A, B), les listes de valeurs distinctes suivantes sont associées aux mêmes valeurs de colonnes : (3, 5), (4, 4) et (4, 5)|  
|Longueur moyenne|Longueur moyenne, en octets, pour le stockage d'une liste des valeurs de colonnes pour le préfixe de colonne. Par exemple, si les valeurs dans la liste (3, 5, 6) nécessitent 4 octets chacune, la longueur est égale à 12 octets.|  
|Columns|Noms des colonnes dans le préfixe dont les valeurs Toutes les densités et Longueur moyenne sont affichées.|  
  
Le tableau suivant décrit les colonnes retournées dans le jeu de résultats lorsque l'option HISTOGRAM est spécifiée.
  
|Nom de colonne| Description|  
|---|---|
|RANGE_HI_KEY|Valeur de colonne de limite supérieure pour une étape d'histogramme. La valeur de colonne est également appelée « valeur de clé ».|  
|RANGE_ROWS|Nombre estimé de lignes dont la valeur de colonne est comprise dans une étape d'histogramme, à l'exception de la limite supérieure.|  
|EQ_ROWS|Nombre estimé de lignes dont la valeur de colonne est égale à la limite supérieure de l'étape d'histogramme.|  
|DISTINCT_RANGE_ROWS|Nombre estimé de lignes ayant une valeur de colonne distincte dans une étape d'histogramme, à l'exception de la limite supérieure.|  
|AVG_RANGE_ROWS|Nombre moyen de lignes ayant des valeurs de colonnes dupliquées dans une étape d'histogramme, à l'exception de la limite supérieure (RANGE_ROWS / DISTINCT_RANGE_ROWS pour DISTINCT_RANGE_ROWS > 0).| 
  
## <a name="remarks"></a>Notes  
  
## <a name="histogram"></a>Histogramme  
Un histogramme mesure la fréquence des occurrences de chaque valeur distincte dans un jeu de données. L'optimiseur de requête calcule un histogramme sur les valeurs de colonnes de la première colonne clé de l'objet de statistiques, en sélectionnant les valeurs de colonnes au moyen d'un échantillonnage statistique des lignes ou d'une analyse complète de toutes les lignes dans la table ou la vue. Si l'histogramme est créé à partir d'un jeu de lignes échantillonnées, les totaux stockés pour le nombre de lignes et le nombre de valeurs distinctes sont des estimations et ne doivent pas nécessairement être des nombres entiers.
  
Pour créer l'histogramme, l'optimiseur de requête trie les valeurs de colonnes, calcule le nombre de valeurs qui correspondent à chaque valeur de colonne distincte, puis regroupe les valeurs de colonnes dans 200 étapes d'histogramme contiguës au maximum. Chaque étape inclut une plage de valeurs de colonnes suivie d'une valeur de colonne de limite supérieure. La plage comprend toutes les valeurs de colonnes possibles entre des valeurs limites, à l'exception des valeurs limites elles-mêmes. La plus basse des valeurs de colonnes triées est la valeur de limite supérieure pour la première étape d'histogramme.
  
Le diagramme suivant illustre un histogramme avec six étapes : La zone située à gauche de la première valeur limite supérieure représente la première étape.
  
![](../../relational-databases/system-dynamic-management-views/media/a0ce6714-01f4-4943-a083-8cbd2d6f617a.gif "a0ce6714-01f4-4943-a083-8cbd2d6f617a")
  
Pour chaque étape d'histogramme :
-   La ligne en gras représente la valeur limite supérieure (RANGE_HI_KEY) et le nombre d'occurrences (EQ_ROWS) correspondant.  
-   La zone pleine située à gauche de RANGE_HI_KEY représente la plage de valeurs de colonnes et le nombre moyen d'occurrences de chacune des valeurs de colonnes (AVG_RANGE_ROWS). La valeur AVG_RANGE_ROWS pour la première étape d'histogramme est toujours 0.  
-   Les lignes pointillées représentent les valeurs échantillonnées utilisées pour estimer le nombre total de valeurs distinctes dans la plage (DISTINCT_RANGE_ROWS) et le nombre total de valeurs dans la plage (RANGE_ROWS). L'optimiseur de requête utilise les valeurs RANGE_ROWS et DISTINCT_RANGE_ROWS pour calculer la valeur AVG_RANGE_ROWS ; il ne stocke pas les valeurs échantillonnées.  
  
L'optimiseur de requête définit les étapes d'histogramme en fonction de leur importance statistique. Il utilise un algorithme de nombre maximal de différences pour réduire le nombre d'étapes dans l'histogramme tout en augmentant la différence entre les valeurs limites. Le nombre maximal d'étapes est 200. Le nombre d'étapes d'histogramme peut être inférieur au nombre de valeurs distinctes, même pour les colonnes comportant moins de 200 points de limite. Par exemple, une colonne avec 100 valeurs distinctes peut avoir un histogramme comportant moins de 100 points de limite.
  
## <a name="density-vector"></a>Vecteur de densité  
L'optimiseur de requête utilise des densités afin d'améliorer les estimations de cardinalité pour les requêtes qui retournent plusieurs colonnes à partir de la même table ou vue indexée. Le vecteur de densité contient une densité pour chaque préfixe des colonnes dans l'objet de statistiques. Par exemple, si un objet de statistiques contient les colonnes clés CustomerID, ItemId, Price, la densité est calculée sur chacun des préfixes de colonnes suivants :
  
|Préfixe de colonne|Densité calculée sur|  
|---|---|
|(CustomerId)|Lignes avec des valeurs correspondantes pour CustomerID|  
|(CustomerId, ItemId)|Lignes avec des valeurs correspondantes pour CustomerId et ItemId|  
|(CustomerId, ItemId, Price)|Lignes avec des valeurs correspondantes pour CustomerId, ItemId et Price|  
  
## <a name="restrictions"></a>Restrictions  
 DBCC SHOW_STATISTICS ne fournit pas de statistiques pour les index spatiaux ou columnstore optimisés en mémoire xVelocity.  
  
## <a name="permissions-for-includessnoversionincludesssnoversion-mdmd-and-includesssdsincludessssds-mdmd"></a>Autorisations pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et[!INCLUDE[ssSDS](../../includes/sssds-md.md)]  
Afin d’afficher l’objet de statistiques, l’utilisateur doit posséder la table ou de l’utilisateur doit être un membre de la `sysadmin` rôle serveur fixe le `db_owner` rôle de base de données fixe ou la `db_ddladmin` rôle de base de données fixe.
  
SQL Server 2012 SP1 modifie les limites liées aux autorisations et permet aux utilisateurs avec l'autorisation SELECT d'utiliser cette commande. Remarquez que les conditions suivantes doivent être remplies pour que les autorisations SELECT permettent d'exécuter la commande :
-   Les utilisateurs doivent posséder des autorisations sur toutes les colonnes dans l'objet de statistiques.  
-   Les utilisateurs doivent posséder une autorisation sur toutes les colonnes dans une condition de filtre (le cas échéant).  
-   La table ne peut pas avoir une stratégie de sécurité de niveau ligne.  
  
Pour désactiver ce comportement, utilisez traceflag 9485.
  
## <a name="permissions-for-includesssdwincludessssdw-mdmd-and-includesspdwincludessspdw-mdmd"></a>Autorisations pour [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] et[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
DBCC SHOW_STATISTICS requiert l’autorisation SELECT sur la table ou l’appartenance de l’une des opérations suivantes :
-   rôle serveur fixe sysadmin  
-   rôle de base de données fixe db_owner  
-   rôle de base de données fixe db_ddladmin  
  
## <a name="limitations-and-restrictions-for-includesssdwincludessssdw-mdmd-and-includesspdwincludessspdw-mdmd"></a>Limitations et Restrictions pour [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] et[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
DBCC SHOW_STATISTICS affiche les statistiques stockées dans la base de données de l’interpréteur de commandes au niveau du nœud de contrôle. Il n’affiche pas les statistiques sont créées automatiquement par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur les nœuds de calcul.
  
DBCC SHOW_STATISTICS n’est pas pris en charge sur les tables externes.
  
## <a name="examples-includessnoversionincludesssnoversion-mdmd-and-includesssdsincludessssds-mdmd"></a>Exemples : [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et[!INCLUDE[ssSDS](../../includes/sssds-md.md)]  
### <a name="a-returning-all-statistics-information"></a>A. Retour de toutes les informations statistiques  
L’exemple suivant affiche toutes les informations statistiques relatives à la `AK_Address_rowguid` index de la `Person.Address` de table dans le [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] base de données.
  
```t-sql
DBCC SHOW_STATISTICS ("Person.Address", AK_Address_rowguid);  
GO  
```  
  
### <a name="b-specifying-the-histogram-option"></a>B. Utilisation de l'option HISTOGRAM  
Cela limite les informations statistiques affichées pour Customer_LastName pour les données d’histogramme.
  
```t-sql
DBCC SHOW_STATISTICS ("dbo.DimCustomer",Customer_LastName) WITH HISTOGRAM;  
GO  
```  
  
## <a name="examples-includesssdwincludessssdw-mdmd-and-includesspdwincludessspdw-mdmd"></a>Exemples : [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] et[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
### <a name="c-display-the-contents-of-one-statistics-object"></a>C. Afficher le contenu de l’objet de statistiques d’un  
 L’exemple suivant affiche le contenu des statistiques Customer_LastName sur la table DimCustomer.  
  
```t-sql
-- Uses AdventureWorks  
--First, create a statistics object  
CREATE STATISTICS Customer_LastName   
ON AdventureWorksPDW2012.dbo.DimCustomer (LastName);  
GO  
DBCC SHOW_STATISTICS ("dbo.DimCustomer",Customer_LastName);  
GO  
```  
  
Les résultats indiquent l’en-tête, le vecteur de densité et la partie de l’histogramme.
  
![DBCC SHOW_STATISTICS (résultats)](../../t-sql/database-console-commands/media/aps-sql-dbccshow-statistics.JPG "DBCC SHOW_STATISTICS (résultats)")
  
## <a name="see-also"></a>Voir aussi  
[Statistiques](../../relational-databases/statistics/statistics.md)  
[CREATE INDEX &#40;Transact-SQL&#41;](../../t-sql/statements/create-index-transact-sql.md)  
[CREATE STATISTICS &#40;Transact-SQL&#41;](../../t-sql/statements/create-statistics-transact-sql.md)  
[DROP STATISTICS &#40; Transact-SQL &#41;](../../t-sql/statements/drop-statistics-transact-sql.md)  
[sp_autostats &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-autostats-transact-sql.md)  
[sp_createstats &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-createstats-transact-sql.md)  
[STATS_DATE &#40; Transact-SQL &#41;](../../t-sql/functions/stats-date-transact-sql.md)  
[UPDATE STATISTICS &#40;Transact-SQL&#41;](../../t-sql/statements/update-statistics-transact-sql.md)  
[Sys.dm_db_stats_properties (Transact-SQL)](../../relational-databases/system-dynamic-management-views/sys-dm-db-stats-properties-transact-sql.md)  
[Sys.dm_db_stats_histogram (Transact-SQL)](../../relational-databases/system-dynamic-management-views/sys-dm-db-stats-histogram-transact-sql.md)   

