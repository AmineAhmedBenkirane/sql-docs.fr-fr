---
title: ALTER PROCEDURE (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 05/01/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: t-sql|statements
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ALTER_PROCEDURE_TSQL
- ALTER_PROC_TSQL
- ALTER PROC
- ALTER PROCEDURE
dev_langs:
- TSQL
helpviewer_keywords:
- ALTER PROCEDURE statement
- stored procedure modifications [SQL Server]
- modifying stored procedures
- stored procedures [SQL Server], modifying
ms.assetid: ed9b2f76-11ec-498d-a95e-75b490a75733
caps.latest.revision: 69
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 3dc195d3f6ca908253ff5726c3f336435e7f2bd1
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="alter-procedure-transact-sql"></a>ALTER PROCEDURE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Modifie une procédure déjà créée en exécutant l'instruction CREATE PROCEDURE dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "icône lien de rubrique") [Conventions de syntaxe Transact-SQL (Transact-SQL)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
-- Syntax for SQL Server and Azure SQL Database
  
ALTER { PROC | PROCEDURE } [schema_name.] procedure_name [ ; number ]   
    [ { @parameter [ type_schema_name. ] data_type }   
        [ VARYING ] [ = default ] [ OUT | OUTPUT ] [READONLY]  
    ] [ ,...n ]   
[ WITH <procedure_option> [ ,...n ] ]  
[ FOR REPLICATION ]   
AS { [ BEGIN ] sql_statement [;] [ ...n ] [ END ] }  
[;]  
  
<procedure_option> ::=   
    [ ENCRYPTION ]  
    [ RECOMPILE ]  
    [ EXECUTE AS Clause ]  
```  
  
```  
-- Syntax for SQL Server CLR Stored Procedure  
  
ALTER { PROC | PROCEDURE } [schema_name.] procedure_name [ ; number ]   
    [ { @parameter [ type_schema_name. ] data_type }   
        [ = default ] [ OUT | OUTPUT ] [READONLY]  
    ] [ ,...n ]   
[ WITH EXECUTE AS Clause ]  
AS { EXTERNAL NAME assembly_name.class_name.method_name }  
[;]  
```  
  
```tsql  
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  
  
ALTER { PROC | PROCEDURE } [schema_name.] procedure_name  
    [ { @parameterdata_type } [= ] ] [ ,...n ]  
AS { [ BEGIN ] sql_statement [ ; ] [ ,...n ] [ END ] }  
[;]  
```  
  
## <a name="arguments"></a>Arguments  
 *schema_name*  
 Le nom du schéma auquel appartient la procédure.  
  
 *nom_procédure*  
 Le nom de la procédure de modification. Les noms des procédures doivent respecter les conventions concernant les [identificateurs](../../relational-databases/databases/database-identifiers.md).  
  
 **;**  *nombre*  
 Nombre entier facultatif qui est utilisé pour regrouper les procédures de même nom afin qu’ils puissent être supprimés ensemble à l’aide d’une instruction DROP PROCEDURE.  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
 **@***paramètre*  
 Un paramètre de la procédure. Il est possible de spécifier jusqu'à 2 100 paramètres.  
  
 [ *type_schema_name***.** ] *data_type*  
 Type de données du paramètre et du schéma auquel elle appartient.  
  
 Pour plus d’informations sur les restrictions de type de données, consultez [CREATE PROCEDURE &#40; Transact-SQL &#41; ](../../t-sql/statements/create-procedure-transact-sql.md).  
  
 VARYING  
 Spécifie le jeu de résultats pris en charge comme paramètre de sortie. La procédure stockée construit dynamiquement ce paramètre. Son contenu est variable. S'applique seulement aux paramètres de type cursor. Cette option n'est pas valide pour les procédures CLR.  
  
 *par défaut*  
 Valeur par défaut pour le paramètre.  
  
 OUT | OUTPUT  
 Indique que le paramètre est un paramètre renvoyé.  
  
 READONLY  
 Indique que le paramètre ne peut pas être mis à jour ou modifié dans le corps de la procédure. Si le type de paramètre est un type de table, READONLY doit être spécifié.  
  
 RECOMPILE  
 Indique que le [!INCLUDE[ssDE](../../includes/ssde-md.md)] n'utilise pas le cache pour le plan de cette procédure et que la procédure est recompilée à l'exécution.  
  
 ENCRYPTION  
 **S’applique aux**: SQL Server ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] via [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]) et [!INCLUDE[ssSDSFull](../../includes/sssdsfull-md.md)].  
  
 Indique que le [!INCLUDE[ssDE](../../includes/ssde-md.md)] se charge de convertir le texte d'origine provenant de l'instruction ALTER PROCEDURE dans un format d'obfuscation. La sortie générée par l'obfuscation n'est pas visible directement dans les affichages catalogue de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Les utilisateurs n'ayant pas accès aux tables système ou aux fichiers de base de données ne peuvent pas récupérer le texte d'obfuscation. Toutefois, le texte sera disponible pour les utilisateurs disposant de privilèges qui peuvent accéder soit les tables système via la [port DAC](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md) ou accéder directement aux fichiers de base de données. Les utilisateurs qui peuvent associer un débogueur au processus serveur peuvent également récupérer la procédure d'origine de la mémoire au moment de l'exécution. Pour plus d’informations sur l’accès aux métadonnées système, consultez [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
 Les procédures créées à l'aide de cette option ne peuvent pas être publiées dans le cadre d'une réplication [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 Cette option ne peut pas être spécifiée pour les procédures stockées CLR (Common Language Runtime).  
  
> [!NOTE]  
>  Pendant une mise à niveau, le [!INCLUDE[ssDE](../../includes/ssde-md.md)] utilise les commentaires d’obfuscation stockés dans **sys.sql_modules** pour recréer des procédures.  
  
 EXECUTE AS  
 Spécifie le contexte de sécurité dans lequel exécuter la procédure stockée après y avoir accédé.  
  
 Pour plus d’informations, consultez [Clause EXECUTE AS &#40;Transact-SQL&#41;](../../t-sql/statements/execute-as-clause-transact-sql.md).  
  
 FOR REPLICATION  

  
 Indique qu'il n'est pas possible d'exécuter sur l'Abonné les procédures stockées créées pour la réplication. Une procédure stockée créée avec l'option FOR REPLICATION est utilisée comme filtre de procédure stockée et n'est exécutée que lors de la réplication. Il n'est pas possible de déclarer des paramètres si FOR REPLICATION est spécifié. Cette option n'est pas valide pour les procédures CLR. L'option RECOMPILE est ignorée pour les procédures créées avec l'option FOR REPLICATION.  
  
> [!NOTE]  
>  Cette option n'est pas disponible dans une base de données à relation contenant-contenu.  
  
 {[BEGIN] *sql_statement* [ ;] [ ...  *n*  ] [END]}  
 Une ou plusieurs instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] comprenant le corps de la procédure. Vous pouvez utiliser les mots clés facultatifs BEGIN et END pour délimiter les instructions. Pour plus d’informations, consultez les sections de meilleures pratiques, remarques d’ordre général et Limitations et Restrictions dans [CREATE PROCEDURE &#40; Transact-SQL &#41; ](../../t-sql/statements/create-procedure-transact-sql.md).  
  
 NOM externe *assembly_name***.** *class_name***.** *nom_méthode*  
 **S'applique à**: [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] et [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 Spécifie la méthode d’un [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] assembly pour un type CLR une procédure stockée à référencer. *CLASS_NAME* doit être valide [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] identificateur et doit exister en tant que classe dans l’assembly. Si la classe a un nom qualifié d’espace de noms utilise une période (**.**) pour séparer les parties de l’espace de noms, le nom de classe doit être délimité par des crochets (**[]**) ou des guillemets (**» «**). La méthode spécifiée doit être une méthode statique de la classe.  
  
 Par défaut, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peut pas exécuter du code CLR. Vous pouvez créer, modifier et supprimer des objets de base de données qui référencent des modules de runtime de langage commun ; Toutefois, vous ne pouvez pas exécuter ces références dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] jusqu'à ce que vous activiez la [option clr enabled](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md). Pour activer l’option, utilisez [sp_configure](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md).  
  
> [!NOTE]  
>  Les procédures CLR ne sont pas prises en charge dans une base de données à relation contenant-contenu.  
  
## <a name="general-remarks"></a>Remarques d'ordre général  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] pour les transformer en procédures stockées CLR et inversement.  
  
 ALTER PROCEDURE ne modifie pas les autorisations et n'affecte aucune procédure stockée ni aucun déclencheur dépendants. Cependant, les paramètres QUOTED_IDENTIFIER et ANSI_NULLS de la session active sont inclus dans la procédure stockée lorsque celle-ci est modifiée. Si les paramètres sont différents des paramètres actifs lors de la création de la procédure stockée, le comportement de celle-ci peut changer.  
  
 Si une procédure à été créée avec les options WITH ENCRYPTION ou WITH RECOMPILE, ces options sont activées seulement si elles figurent dans l'instruction ALTER PROCEDURE.  
  
 Pour plus d’informations sur les procédures stockées, consultez [CREATE PROCEDURE &#40; Transact-SQL &#41; ](../../t-sql/statements/create-procedure-transact-sql.md).  
  
## <a name="security"></a>Sécurité  
  
### <a name="permissions"></a>Permissions  
 Requiert **ALTER** autorisation sur la procédure ou nécessite l’appartenance dans le **db_ddladmin** rôle de base de données fixe.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant crée la procédure stockée `uspVendorAllInfo`. Cette procédure retourne le nom de tous les fournisseurs de [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)], les produits qu'ils vendent, leurs conditions de crédit et leur disponibilité. Lorsque cette procédure est créée, elle est ensuite modifiée pour renvoyer un jeu de résultats différent.  
  
```  
  
IF OBJECT_ID ( 'Purchasing.uspVendorAllInfo', 'P' ) IS NOT NULL   
    DROP PROCEDURE Purchasing.uspVendorAllInfo;  
GO  
CREATE PROCEDURE Purchasing.uspVendorAllInfo  
WITH EXECUTE AS CALLER  
AS  
    SET NOCOUNT ON;  
    SELECT v.Name AS Vendor, p.Name AS 'Product name',   
      v.CreditRating AS 'Rating',   
      v.ActiveFlag AS Availability  
    FROM Purchasing.Vendor v   
    INNER JOIN Purchasing.ProductVendor pv  
      ON v.BusinessEntityID = pv.BusinessEntityID   
    INNER JOIN Production.Product p  
      ON pv.ProductID = p.ProductID   
    ORDER BY v.Name ASC;  
GO  
  
```  
  
 L'exemple suivant modifie la procédure stockée `uspVendorAllInfo`. Il supprime la clause EXECUTE AS CALLER et modifie le corps de la procédure pour qu'elle retourne uniquement les fournisseurs qui proposent le produit spécifié. Les fonctions `LEFT` et `CASE` personnalisent l'affichage du jeu de résultats.  
  
```  
USE AdventureWorks2012;  
GO  
ALTER PROCEDURE Purchasing.uspVendorAllInfo  
    @Product varchar(25)   
AS  
    SET NOCOUNT ON;  
    SELECT LEFT(v.Name, 25) AS Vendor, LEFT(p.Name, 25) AS 'Product name',   
    'Rating' = CASE v.CreditRating   
        WHEN 1 THEN 'Superior'  
        WHEN 2 THEN 'Excellent'  
        WHEN 3 THEN 'Above average'  
        WHEN 4 THEN 'Average'  
        WHEN 5 THEN 'Below average'  
        ELSE 'No rating'  
        END  
    , Availability = CASE v.ActiveFlag  
        WHEN 1 THEN 'Yes'  
        ELSE 'No'  
        END  
    FROM Purchasing.Vendor AS v   
    INNER JOIN Purchasing.ProductVendor AS pv  
      ON v.BusinessEntityID = pv.BusinessEntityID   
    INNER JOIN Production.Product AS p   
      ON pv.ProductID = p.ProductID   
    WHERE p.Name LIKE @Product  
    ORDER BY v.Name ASC;  
GO  
  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 ```   
 Vendor               Product name  Rating    Availability  
-------------------- ------------- -------   ------------  
Proseware, Inc.      LL Crankarm   Average   No  
Vision Cycles, Inc.  LL Crankarm   Superior  Yes  
(2 row(s) affected)`  
```  

## <a name="see-also"></a>Voir aussi  
 [CREATE PROCEDURE &#40;Transact-SQL&#41;](../../t-sql/statements/create-procedure-transact-sql.md)   
 [DROP PROCEDURE &#40; Transact-SQL &#41;](../../t-sql/statements/drop-procedure-transact-sql.md)   
 [EXECUTE &#40;Transact-SQL&#41;](../../t-sql/language-elements/execute-transact-sql.md)   
 [EXECUTE AS &#40; Transact-SQL &#41;](../../t-sql/statements/execute-as-transact-sql.md)   
 [EVENTDATA &#40;Transact-SQL&#41;](../../t-sql/functions/eventdata-transact-sql.md)   
 [Procédures stockées &#40;moteur de base de données&#41;](../../relational-databases/stored-procedures/stored-procedures-database-engine.md)   
 [Sys.Procedures &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-procedures-transact-sql.md)  
  
  

