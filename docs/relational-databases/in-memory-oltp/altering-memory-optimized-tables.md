---
title: "Modification des tables à mémoire optimisée | Microsoft Docs"
ms.custom:
- SQL2016_New_Updated
ms.date: 06/19/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine-imoltp
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 690b70b7-5be1-4014-af97-54e531997839
caps.latest.revision: 20
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 7d2dbe0bdc4cbd05f11eacf938b35a9c35ace2e7
ms.openlocfilehash: bd27f9755945abf7c09118a5997bb3745e66ab57
ms.contentlocale: fr-fr
ms.lasthandoff: 06/23/2017

---
# Modification des tables à mémoire optimisée
<a id="altering-memory-optimized-tables" class="xliff"></a>
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  Vous pouvez effectuer des modifications de schéma et d’index sur les tables à mémoire optimisée en utilisant l’instruction ALTER TABLE. Dans SQL Server 2016 et Azure SQL Database, les opérations ALTER TABLE sur des tables à mémoire optimisée sont HORS CONNEXION, ce qui signifie que la table n’est pas disponible pour les requêtes quand l’opération est en cours. Dans le cadre de cette modification, l’application de base de données peut continuer à s’exécuter, mais toute opération accédant à la table est bloquée jusqu’à la fin du processus de modification. Il est possible de combiner plusieurs opérations ADD, DROP ou ALTER dans une seule instruction ALTER TABLE.
  
## ALTER TABLE
<a id="alter-table" class="xliff"></a>  
 
La syntaxe ALTER TABLE permet d’apporter des modifications au schéma de la table, et d’ajouter, de supprimer et de régénérer des index. Les index sont considérés comme faisant partie intégrante de la définition de table :  
  
-   La syntaxe ALTER TABLE … ADD/DROP/ALTER INDEX est uniquement prise en charge pour les tables à mémoire optimisée.  
  
-   En l’absence d’instruction ALTER TABLE, les instructions CREATE INDEX, DROP INDEX et ALTER INDEX ne sont *pas* prises en charge pour les index sur les tables à mémoire optimisée.  
  
 Le code ci-après présente la syntaxe des clauses ADD, DROP et ALTER INDEX sur l’instruction ALTER TABLE.  
  
```
| ADD   
     {   
        <column_definition>  
      | <table_constraint>  
      | <table_index>    
     } [ ,...n ]  
  
| DROP   
     {  
         [ CONSTRAINT ]   
         {   
              constraint_name   
         } [ ,...n ]  
         | COLUMN   
         {  
              column_name   
         } [ ,...n ]  
         | INDEX   
         {  
              index_name   
         } [ ,...n ]  
     } [ ,...n ]  
  
| ALTER INDEX index_name  
     {   
         REBUILD WITH ( <rebuild_index_option> )     
     }  
}  
```  
  
 Les types de modifications pris en charge sont les suivants :  
  
-   modification du nombre de compartiments ;  
  
-   ajout et suppression d’un index ;  
  
-   modification, ajout et suppression d’une colonne ;  
  
-   ajout et suppression d’une contrainte.  
  
 Pour plus d’informations sur la fonctionnalité ALTER TABLE et sur la syntaxe complète, consultez [ALTER TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-table-transact-sql.md).  
  
## Dépendance liée au schéma
<a id="schema-bound-dependency" class="xliff"></a>  
 Les procédures stockées compilées en mode natif doivent être liées au schéma, ce qui signifie qu’elles ont une dépendance liée au schéma vis-à-vis des tables à mémoire optimisée auxquelles elles accèdent et des colonnes qu’elles référencent. Une dépendance liée au schéma est une relation entre deux entités qui empêche l’entité référencée d’être supprimée ou modifiée de façon incompatible tant que l’entité de référence existe.  
  
 Par exemple, si une procédure stockée compilée en mode natif et liée au schéma fait référence à une colonne *c1* de la table *mytable*, la colonne *c1* ne peut pas être supprimée. De même, s’il existe une telle procédure avec une instruction INSERT sans liste de colonnes (par exemple, `INSERT INTO dbo.mytable VALUES (...)`), alors aucune colonne de la table ne peut être supprimée.  
 
## Journalisation de l’instruction ALTER TABLE sur des tables à mémoire optimisée
<a id="logging-of-alter-table-on-memory-optimized-tables" class="xliff"></a>
Sur une table à mémoire optimisée, la plupart des scénarios ALTER TABLE s’exécutent désormais en parallèle, d’où une optimisation des écritures dans le journal des transactions. L’optimisation est obtenue par la journalisation des seules modifications de métadonnées dans le journal des transactions. Cependant, les opérations ALTER TABLE suivantes sont effectuées en mode à thread unique et ne sont pas optimisées pour la journalisation.

L’opération monothread dans ce cas consigne dans le journal des transactions l’intégralité du contenu de la table modifiée. Voici la liste des opérations à thread unique :

- Modifier ou ajouter une colonne pour utiliser un type d’objet volumineux (LOB) : nvarchar(max), varchar(max) ou varbinary(max).

- Ajouter ou supprimer un index COLUMNSTORE.

- Presque tout ce qui affecte une [colonne hors ligne](../../relational-databases/in-memory-oltp/supported-data-types-for-in-memory-oltp.md).

    - Provoquer le déplacement d’une colonne sur une ligne en mode hors ligne.

    - Provoquer le déplacement d’une colonne en mode hors ligne sur une ligne.

    - Créer une colonne hors ligne.

    - *Exception :* l’allongement d’une colonne déjà hors ligne est journalisé de la manière optimisée. 
  
## Exemples
<a id="examples" class="xliff"></a>  
 L’exemple ci-après modifie le nombre de compartiments d’un index de hachage existant. Cette opération régénère l’index de hachage avec le nouveau nombre de compartiments, tandis que les autres propriétés de l’index de hachage restent identiques.  
  
```tsql
ALTER TABLE Sales.SalesOrderDetail_inmem   
       ALTER INDEX imPK_SalesOrderDetail_SalesOrderID_SalesOrderDetailID  
              REBUILD WITH (BUCKET_COUNT=67108864);  
GO
```
  
 L’exemple ci-après ajoute une colonne avec une contrainte NOT NULL et une définition DEFAULT, et utilise WITH VALUES afin de spécifier des valeurs pour chaque ligne existante de la table. Si l'option WITH VALUES n'est pas utilisée, chaque ligne a la valeur NULL dans la nouvelle colonne.  
  
```tsql  
ALTER TABLE Sales.SalesOrderDetail_inmem  
       ADD Comment NVARCHAR(100) NOT NULL DEFAULT N'' WITH VALUES;  
GO
```  
  
 L’exemple ci-après ajoute une contrainte de clé primaire à une colonne existante.  
  
```tsql
CREATE TABLE dbo.UserSession (   
   SessionId int not null,   
   UserId int not null,   
   CreatedDate datetime2 not null,   
   ShoppingCartId int,   
   index ix_UserId nonclustered hash (UserId) with (bucket_count=400000)   
)   
WITH (MEMORY_OPTIMIZED=ON, DURABILITY=SCHEMA_ONLY) ;  
GO  
  
ALTER TABLE dbo.UserSession  
       ADD CONSTRAINT PK_UserSession PRIMARY KEY NONCLUSTERED (SessionId);  
GO
```  
  
 L’exemple suivant supprime un index.  
  
```tsql
ALTER TABLE Sales.SalesOrderDetail_inmem  
       DROP INDEX ix_ModifiedDate;  
GO
```  
  
 L’exemple suivant ajoute un index.  
  
```tsql  
ALTER TABLE Sales.SalesOrderDetail_inmem  
       ADD INDEX ix_ModifiedDate (ModifiedDate);  
GO  
```  
  
 L’exemple suivant ajoute plusieurs colonnes, avec un index et des contraintes.  
  
```tsql
ALTER TABLE Sales.SalesOrderDetail_inmem  
       ADD    CustomerID int NOT NULL DEFAULT -1 WITH VALUES,  
              ShipMethodID int NOT NULL DEFAULT -1 WITH VALUES,  
              INDEX ix_Customer (CustomerID);  
GO  
```


<a name="logging-of-alter-table-on-memory-optimized-tables-124"></a>


## Voir aussi
<a id="see-also" class="xliff"></a>  

[Tables à mémoire optimisée](../../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  


