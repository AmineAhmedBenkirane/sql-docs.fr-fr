---
title: DBCC SHOWCONTIG (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 07/17/2017
ms.prod: sql-non-specified
ms.prod_service: sql-database
ms.service: 
ms.component: t-sql|database-console-commands
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DBCC_SHOWCONTIG_TSQL
- DBCC SHOWCONTIG
- SHOWCONTIG
- SHOWCONTIG_TSQL
dev_langs: TSQL
helpviewer_keywords:
- displaying defragmentation information
- DBCC SHOWCONTIG statement
- defragmenting indexes
- leaf level defragmenting
- fragmentation [SQL Server]
- index defragmenting [SQL Server]
ms.assetid: 1df2123a-1197-4fff-91a3-25e3d8848aaa
caps.latest.revision: "78"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 85822d9351e0f0ce5a8c5a7542fbd7df57d13d74
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="dbcc-showcontig-transact-sql"></a>DBCC SHOWCONTIG (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

Affiche les informations de fragmentation pour les données et les index de la table ou vue spécifiée.
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]Utilisez [sys.dm_db_index_physical_stats](../../relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql.md) à la place.  
  
**S’applique aux**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] via [version actuelle](http://go.microsoft.com/fwlink/p/?LinkId=299658))
  
![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntaxe  
  
```sql
DBCC SHOWCONTIG   
[ (   
    { table_name | table_id | view_name | view_id }   
    [ , index_name | index_id ]   
) ]   
    [ WITH   
        {   
         [ , [ ALL_INDEXES ] ]   
         [ , [ TABLERESULTS ] ]   
         [ , [ FAST ] ]  
         [ , [ ALL_LEVELS ] ]   
         [ NO_INFOMSGS ]  
         }  
    ]  
```  
  
## <a name="arguments"></a>Arguments  
 *nom_table* | *table_id* | *view_name* | *view_id*  
 Table ou vue dont les informations de fragmentation doivent être vérifiées. Sans aucune précision, toutes les tables et les vues indexées de la base de données active sont contrôlées. Pour obtenir la table ou afficher les ID, utilisez la [OBJECT_ID](../../t-sql/functions/object-id-transact-sql.md) (fonction).  
  
 *index_name* | *index_id*  
 Index dont les informations de fragmentation doivent être vérifiées. Si aucune option n'est spécifiée, l'instruction traite l'index de base de la table ou de la vue indiquée. Pour obtenir l’ID d’index, utilisez la [sys.indexes](../../relational-databases/system-catalog-views/sys-indexes-transact-sql.md) vue de catalogue.  
  
 par  
 Spécifie les options relatives au type d'informations renvoyées par l'instruction DBCC.  
  
 FAST  
 Indique si une analyse rapide de l'index doit être effectuée et un minimum d'informations renvoyées. Une analyse rapide ne lit pas les pages des niveaux feuille ou données de l'index.  
  
 ALL_INDEXES  
 Affiche les résultats de tous les index des tables et vues spécifiées, même si un index particulier est spécifié.  
  
 TABLERESULTS  
 Affiche les résultats sous la forme d'un ensemble de lignes, avec des informations complémentaires.  
  
 ALL_LEVELS  
 Conservé pour compatibilité descendante uniquement. Même si ALL_LEVELS est spécifié, seul le niveau feuille de l'index ou le niveau données de la table est traité.  
  
 NO_INFOMSGS  
 Supprime tous les messages d'information dont les niveaux de gravité sont compris entre 0 et 10.  
  
## <a name="result-sets"></a>Jeux de résultats  
Le tableau suivant décrit les informations du jeu de résultats.
  
|statistiques| Description|  
|---|---|
|**Pages analysées**|Nombre de pages dans la table ou l'index.|  
|**Extensions analysées**|Nombre d'extensions dans la table ou l'index|  
|**Commutateurs d’extension**|Nombre de fois où l'instruction DBCC est passée d'une extension à l'autre en parcourant les pages de l'index ou de la table.|  
|**Durée Pages par extension**|Nombre de pages par extension dans la chaîne de pages.|  
|**Densité d’analyse [meilleur nombre : nombre réel]**|Il s'agit d'un pourcentage. Il représente le ratio **meilleur nombre** à **nombre réel**. Cette valeur est de 100 si tout est contigu et elle est inférieure à 100 si certaines fragmentations existent.<br /><br /> **Meilleur nombre** est le nombre idéal de modifications d’extension si tout est lié en contigu. **Nombre réel** est le nombre effectif de modifications d’extension.|  
|**Fragmentation d’analyse logique**|Pourcentage de pages hors service renvoyées après l'analyse des pages de feuilles d'un index. Cette valeur n'est pas pertinente pour les segments. Une page non ordonnés est une page pour laquelle la page physique suivante allouée à l’index n’est pas la page vers laquelle pointée la pag suivant*e* pointeur dans la page feuille actuelle.|  
|**Fragmentation d’analyse d’extension**|Pourcentage d'extensions déclassées lors de l'analyse des pages feuilles d'un index. Cette valeur n'est pas pertinente pour les segments. Une extension hors service est une extension qui contient la page active pour un index, mais n'est pas physiquement l'extension qui suit celle contenant la page précédente pour un index.<br /><br /> Remarque : Ce nombre est sans signification lorsque l’index s’étend sur plusieurs fichiers.|  
|**Durée Octets libres par Page**|Nombre moyen d'octets libres sur les pages analysées. Plus le nombre est élevé et moins les pages sont remplies. Les faibles valeurs sont préférables si l'index ne doit pas recevoir beaucoup d'insertions aléatoires. Ce nombre est également affecté par la taille des lignes : plus elle sera élevée, plus le nombre le sera également.|  
|**Durée Densité de page (complète)**|Densité de page moyenne (pourcentage). Cette valeur prend en compte la taille des lignes. C'est donc une indication plus précise sur le remplissage de vos pages. Plus le pourcentage est élevé et mieux c'est.|  
  
Lorsque *table_id* et FAST sont spécifiés, DBCC SHOWCONTIG renvoie un jeu de résultats avec uniquement les colonnes suivantes.
-   **Pages analysées**  
-   **Commutateurs d’extension**  
-   **Densité d’analyse [meilleur nombre : nombre réel]**  
-   **Fragmentation d’analyse d’extension**  
-   **Fragmentation d’analyse logique**  
  
Lorsque TABLERESULTS est spécifié, DBCC SHOWCONTIG renvoie les colonnes suivantes et également les neuf colonnes décrites dans la table précédente.
  
|statistiques| Description|  
|---|---|
|**Nom de l’objet**|Nom de la table ou de la vue traitée.|  
|**ObjectId**|ID du nom d'objet.|  
|**IndexName**|Nom de l'index traité. A la valeur NULL pour un segment.|  
|**IndexId**|Identificateur de l'index. A la valeur 0 pour un segment.|  
|**Level**|Niveau de l'index. Le niveau 0 correspond au niveau feuille ou données de l'index.<br /><br /> Un segment a le niveau 0.|  
|**Pages**|Nombre de pages constituant ce niveau d'index ou segment entier.|  
|**Lignes**|Nombre d'enregistrements de données ou d'index situés à ce niveau de l'index. Pour un segment, cette valeur représente le nombre d'enregistrements de données dans le segment entier.<br /><br /> Pour un segment de mémoire, le nombre d'enregistrements retournés par cette fonction peut ne pas correspondre au nombre des lignes retournées en exécutant une requête SELECT COUNT(*) sur le segment. Cela est dû au fait qu'une ligne peut contenir plusieurs enregistrements. Par exemple, lors de certaines mises à jour, une ligne de segment unique peut comporter un enregistrement de transfert et un enregistrement transféré suite à l'opération de mise à jour. Par ailleurs, la plupart des lignes LOB de grande taille sont fractionnées en plusieurs enregistrements dans le stockage LOB_DATA.|  
|**MinimumRecordSize**|Taille minimum des enregistrements dans ce niveau d'index ou le segment entier.|  
|**MaximumRecordSize**|Taille maximum des enregistrements dans ce niveau d'index ou le segment entier.|  
|**AverageRecordSize**|Taille moyenne des enregistrements dans ce niveau d'index ou le segment entier.|  
|**ForwardedRecords**|Nombre d'enregistrements transférés dans ce niveau d'index ou le segment entier.|  
|**Étendues**|Nombre d'extensions dans ce niveau d'index ou le segment entier.|  
|**ExtentSwitches**|Nombre de fois où l'instruction DBCC est passée d'une extension à l'autre en parcourant les pages de l'index ou de la table.|  
|**AverageFreeBytes**|Nombre moyen d'octets libres sur les pages analysées. Plus le nombre est élevé et moins les pages sont remplies. Les faibles valeurs sont préférables si l'index ne doit pas recevoir beaucoup d'insertions aléatoires. Ce nombre est également affecté par la taille des lignes : plus elle sera élevée, plus le nombre le sera également.|  
|**AveragePageDensity**|Densité de page moyenne (pourcentage). Cette valeur prend en compte la taille des lignes. C'est donc une indication plus précise sur le remplissage de vos pages. Plus le pourcentage est élevé et mieux c'est.|  
|**ScanDensity**|Il s'agit d'un pourcentage. Il représente le ratio **BestCount** à **ActualCount**. Cette valeur est de 100 si tout est contigu et elle est inférieure à 100 si certaines fragmentations existent.|  
|**BestCount**|Il s'agit du nombre idéal de modifications d'extension si tout est lié en contigu.|  
|**ActualCount**|C'est le nombre effectif de modifications d'extension.|  
|**LogicalFragmentation**|Pourcentage de pages hors service renvoyées après l'analyse des pages de feuilles d'un index. Cette valeur n'est pas pertinente pour les segments. Une page non ordonnés est une page pour laquelle la page physique suivante allouée à l’index n’est pas la page vers laquelle pointée la pag suivant*e* pointeur dans la page feuille actuelle.|  
|**ExtentFragmentation**|Pourcentage d'extensions déclassées lors de l'analyse des pages feuilles d'un index. Cette valeur n'est pas pertinente pour les segments. Une extension hors service est une extension qui contient la page active pour un index, mais n'est pas physiquement l'extension qui suit celle contenant la page précédente pour un index.<br /><br /> Remarque : Ce nombre est sans signification lorsque l’index s’étend sur plusieurs fichiers.|  
  
Lorsque WITH TABLERESULTS et FAST sont spécifiés, l'ensemble de résultats est le même que lorsque WITH TABLERESULTS est spécifié, excepté que les colonnes suivantes auront des valeurs NULL :

| Lignes| Étendues |
|---|---|
|**MinimumRecordSize**|**AverageFreeBytes**|  
|**MaximumRecordSize**|**AveragePageDensity**|  
|**AverageRecordSize**|**ExtentFragmentation**|  
|**ForwardedRecords**||  
  
## <a name="remarks"></a>Notes  
L’instruction DBCC SHOWCONTIG parcourt la chaîne de pages au niveau feuille de l’index dans les cas *index_id* est spécifié. Si une seule *table_id* est spécifié ou si *index_id* est 0, les pages de données de la table spécifiée sont analysés. L'opération ne nécessite qu'un verrou de table intent-partagé. De cette manière, toutes les mises à jour et insertions peuvent être effectuées, sauf celles nécessitant un verrou de table exclusif (X). Cela permet un compromis entre la vitesse d'exécution et aucune réduction de la concurrence avec le nombre de statistiques renvoyées. Cependant, si la commande n'est utilisée que pour évaluer la fragmentation, nous vous recommandons d'appliquer l'option WITH FAST pour des performances optimales. Une analyse rapide ne lit pas les pages des niveaux feuille ou données de l'index. L'option WITH FAST ne s'applique pas à un segment.
  
## <a name="restrictions"></a>Restrictions  
DBCC SHOWCONTIG n’affiche pas les données **ntext**, **texte**, et **image** des types de données. Cela est dû au fait que les index de texte qui stockent des données de texte et d'image n'existent plus.
  
En outre, DBCC SHOWCONTIG ne prend pas en charge certaines fonctionnalités nouvelles. Exemple :
-   Si la table ou l'index spécifié est partitionné, DBCC SHOWCONTIG n'affiche que la première partition de la table ou de l'index spécifié.  
-   DBCC SHOWCONTIG n’affiche pas les informations de stockage de dépassement de ligne et d’autres nouveaux types de données hors ligne, tel que **nvarchar (max)**, **varchar (max)**, **varbinary (max)**, et **xml**.  
-   Les index spatiaux ne sont pas pris en charge par DBCC SHOWCONTIG.  
  
Toutes les nouvelles fonctionnalités sont entièrement pris en charge par le [sys.dm_db_index_physical_stats &#40; Transact-SQL &#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql.md) vue de gestion dynamique.
  
## <a name="table-fragmentation"></a>Fragmentation de la table  
DBCC SHOWCONTIG détermine si la table est fragmentée de manière importante ou non. La fragmentation de la table a lieu lors du processus de modification de données (instructions INSERT, UPDATE et DELETE) effectuées sur la table. Comme ces modifications ne sont pas généralement distribuées équitablement entre les lignes de la table, le remplissage de chaque page peut varier dans le temps. Pour les requêtes qui balaient une partie ou la totalité d'une table, une telle fragmentation de table peut provoquer des lectures de page supplémentaires. Cela perturbe l'analyse parallèle des données.
  
Lorsqu'un index est très fragmenté, vous disposez des méthodes alternatives suivantes pour réduire la fragmentation :
-   Supprimez puis créez de nouveau un index cluster.  
     La nouvelle création d'un index cluster permet de réorganiser les données, ce qui entraîne des pages de données remplies entièrement. Vous pouvez configurer le niveau de remplissage à l'aide de l'option FILLFACTOR de l'instruction CREATE INDEX. Cette méthode présente deux inconvénients : l'index est en mode hors connexion pendant la phase de suppression et de recréation, et l'opération est atomique. Si la création de l'index est interrompue, l'index n'est pas recréé.  
-   Réorganisez les pages de niveau feuille de l'index selon un ordre logique.  
     Utilisez l'instruction ALTER INDEX…REORGANIZE pour réorganiser les pages de niveau feuille de l'index selon un ordre logique. Comme il s'agit d'une opération en ligne, l'index est disponible lorsque l'instruction est exécutée. L'interruption de cette opération entraîne la perte du travail effectué. L'inconvénient de cette méthode est que la réorganisation des données est moins efficace que celle obtenue par l'opération de suppression et de recréation d'un index cluster.  
-   Reconstruisez l'index.  
     Utilisez ALTER INDEX avec REBUILD pour reconstruire l'index. Pour plus d’informations, consultez [ALTER INDEX &#40;Transact-SQL&#41;](../../t-sql/statements/alter-index-transact-sql.md).  
  
La valeur de **Moyenne Octets libres par page** et **moy. Page densité (complète)** statistique dans le jeu de résultats indiquent le remplissage des pages d’index. La valeur de **Moyenne Octets libres par page** nombre doit être faible et le **moy. Page densité (complète)** doit être élevée pour un index qui n’aura pas beaucoup d’insertions aléatoires. La suppression et la recréation d'un index avec l'option FILLFACTOR spécifiée peut améliorer ces statistiques. Par ailleurs, la commande ALTER INDEX avec REORGANIZE comprimera un index en tenant compte de son option FILLFACTOR, ce qui améliore les statistiques.
  
> [!NOTE]  
>  Un index possédant de nombreuses insertions aléatoires et des pages très remplies aura un nombre accru de fractionnements de page. Cela implique une fragmentation plus importante.  
  
Le niveau de fragmentation d'un index peut être déterminé des manières suivantes :
-   En comparant les valeurs de **commutées** et **extensions analysées**.  
     La valeur de **commutées** doit être aussi proche que possible de **extensions analysées**. Ce rapport est calculé comme le **densité d’analyse** valeur. Cette valeur doit être aussi élevée que possible et peut être améliorée en réduisant la fragmentation de l'index.  
  
    > [!NOTE]  
    >  Cette méthode ne fonctionne pas si l'index concerne un grand nombre de fichiers.  
  
-   En comprenant **Fragmentation d’analyse logique** et **Fragmentation d’analyse d’étendue** valeurs.  
     **Fragmentation d’analyse logique** et, dans une moindre mesure, **Fragmentation d’analyse d’étendue** valeurs fournissent la meilleure indication du niveau de fragmentation d’une table. Ces deux valeurs doivent être le plus proche possible de zéro. Toutefois, une valeur de 0 à 10 % est tolérée.  
  
    > [!NOTE]  
    >  Le **Fragmentation d’analyse d’étendue** valeur sera élevée si l’index s’étend sur plusieurs fichiers. Pour réduire ces valeurs, vous devez réduire la fragmentation de l'index.  
  
## <a name="permissions"></a>Permissions  
Utilisateur propriétaire de la table ou être membre du **sysadmin** rôle serveur fixe le **db_owner** rôle de base de données fixe ou **db_ddladmin** rôle de base de données fixe.
  
## <a name="examples"></a>Exemples  
### <a name="a-displaying-fragmentation-information-for-a-table"></a>A. Affichage des informations de fragmentation d'une table  
L'exemple suivant affiche les informations de fragmentation de la table `Employee`.
  
```sql  
USE AdventureWorks2012;  
GO  
DBCC SHOWCONTIG ('HumanResources.Employee');  
GO  
```  
  
### <a name="b-using-objectid-to-obtain-the-table-id-and-sysindexes-to-obtain-the-index-id"></a>B. Utilisation de OBJECT_ID pour obtenir l'ID de table et sys.indexes pour obtenir l'ID d'index  
L’exemple suivant utilise `OBJECT_ID` et `sys.indexes` affichage pour obtenir l’ID de table et l’ID d’index de catalogue le `AK_Product_Name` index de la `Production.Product` table le [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] base de données.
  
```sql  
USE AdventureWorks2012;  
GO  
DECLARE @id int, @indid int  
SET @id = OBJECT_ID('Production.Product')  
SELECT @indid = index_id   
FROM sys.indexes  
WHERE object_id = @id   
   AND name = 'AK_Product_Name'  
DBCC SHOWCONTIG (@id, @indid);  
GO  
```  
  
### <a name="c-displaying-an-abbreviated-result-set-for-a-table"></a>C. Affichage d'un jeu de résultats abrégés pour une table  
L’exemple suivant retourne un résultat abrégé défini pour le `Product` de table dans le [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] base de données.
  
```sql  
USE AdventureWorks2012;  
GO  
DBCC SHOWCONTIG ('Production.Product', 1) WITH FAST;  
GO  
```  
  
### <a name="d-displaying-the-full-result-set-for-every-index-on-every-table-in-a-database"></a>D. Affichage du jeu de résultats complet pour chaque index de chaque table dans une base de données  
L'exemple suivant retourne un jeu de résultats de table entière pour chaque index de chaque table de la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].
  
```sql  
USE AdventureWorks2012;  
GO  
DBCC SHOWCONTIG WITH TABLERESULTS, ALL_INDEXES;  
GO  
```  
  
### <a name="e-using-dbcc-showcontig-and-dbcc-indexdefrag-to-defragment-the-indexes-in-a-database"></a>E. Utilisation de DBCC SHOWCONTIG et de DBCC INDEXDEFRAG pour défragmenter les index d'une base de données  
L'exemple suivant illustre une méthode simple de défragmentation de tous les index d'une base de données fragmentée au-delà d'un seuil déclaré.
  
```sql
/*Perform a 'USE <database name>' to select the database in which to run the script.*/  
-- Declare variables  
SET NOCOUNT ON;  
DECLARE @tablename varchar(255);  
DECLARE @execstr   varchar(400);  
DECLARE @objectid  int;  
DECLARE @indexid   int;  
DECLARE @frag      decimal;  
DECLARE @maxfrag   decimal;  
  
-- Decide on the maximum fragmentation to allow for.  
SELECT @maxfrag = 30.0;  
  
-- Declare a cursor.  
DECLARE tables CURSOR FOR  
   SELECT TABLE_SCHEMA + '.' + TABLE_NAME  
   FROM INFORMATION_SCHEMA.TABLES  
   WHERE TABLE_TYPE = 'BASE TABLE';  
  
-- Create the table.  
CREATE TABLE #fraglist (  
   ObjectName char(255),  
   ObjectId int,  
   IndexName char(255),  
   IndexId int,  
   Lvl int,  
   CountPages int,  
   CountRows int,  
   MinRecSize int,  
   MaxRecSize int,  
   AvgRecSize int,  
   ForRecCount int,  
   Extents int,  
   ExtentSwitches int,  
   AvgFreeBytes int,  
   AvgPageDensity int,  
   ScanDensity decimal,  
   BestCount int,  
   ActualCount int,  
   LogicalFrag decimal,  
   ExtentFrag decimal);  
  
-- Open the cursor.  
OPEN tables;  
  
-- Loop through all the tables in the database.  
FETCH NEXT  
   FROM tables  
   INTO @tablename;  
  
WHILE @@FETCH_STATUS = 0  
BEGIN  
-- Do the showcontig of all indexes of the table  
   INSERT INTO #fraglist   
   EXEC ('DBCC SHOWCONTIG (''' + @tablename + ''')   
      WITH FAST, TABLERESULTS, ALL_INDEXES, NO_INFOMSGS');  
   FETCH NEXT  
      FROM tables  
      INTO @tablename;  
END;  
  
-- Close and deallocate the cursor.  
CLOSE tables;  
DEALLOCATE tables;  
  
-- Declare the cursor for the list of indexes to be defragged.  
DECLARE indexes CURSOR FOR  
   SELECT ObjectName, ObjectId, IndexId, LogicalFrag  
   FROM #fraglist  
   WHERE LogicalFrag >= @maxfrag  
      AND INDEXPROPERTY (ObjectId, IndexName, 'IndexDepth') > 0;  
  
-- Open the cursor.  
OPEN indexes;  
  
-- Loop through the indexes.  
FETCH NEXT  
   FROM indexes  
   INTO @tablename, @objectid, @indexid, @frag;  
  
WHILE @@FETCH_STATUS = 0  
BEGIN  
   PRINT 'Executing DBCC INDEXDEFRAG (0, ' + RTRIM(@tablename) + ',  
      ' + RTRIM(@indexid) + ') - fragmentation currently '  
       + RTRIM(CONVERT(varchar(15),@frag)) + '%';  
   SELECT @execstr = 'DBCC INDEXDEFRAG (0, ' + RTRIM(@objectid) + ',  
       ' + RTRIM(@indexid) + ')';  
   EXEC (@execstr);  
  
   FETCH NEXT  
      FROM indexes  
      INTO @tablename, @objectid, @indexid, @frag;  
END;  
  
-- Close and deallocate the cursor.  
CLOSE indexes;  
DEALLOCATE indexes;  
  
-- Delete the temporary table.  
DROP TABLE #fraglist;  
GO  
```  
  
## <a name="see-also"></a>Voir aussi  
[ALTER INDEX &#40;Transact-SQL&#41;](../../t-sql/statements/alter-index-transact-sql.md)  
[CREATE INDEX &#40;Transact-SQL&#41;](../../t-sql/statements/create-index-transact-sql.md)  
[DBCC &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-transact-sql.md)  
[DROP INDEX &#40;Transact-SQL&#41;](../../t-sql/statements/drop-index-transact-sql.md)  
[sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql.md)  
[OBJECT_ID &#40;Transact-SQL&#41;](../../t-sql/functions/object-id-transact-sql.md)  
[sys.indexes &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-indexes-transact-sql.md)
  
  

