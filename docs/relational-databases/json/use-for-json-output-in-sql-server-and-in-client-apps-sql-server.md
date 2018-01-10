---
title: Utiliser la sortie de FOR JSON dans SQL Server et les applications clientes (SQL Server) | Microsoft Docs
ms.custom: 
ms.date: 06/02/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.component: json
ms.reviewer: 
ms.suite: sql
ms.technology: dbe-json
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FOR JSON, using in client apps
- FOR JSON, using in SQL Server
ms.assetid: 302e5397-b499-4ea3-9a7f-c24ccad698eb
caps.latest.revision: "12"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 3ab09b43e7980921ec09c3b8a04592cc20f61d1f
ms.sourcegitcommit: 4aeedbb88c60a4b035a49754eff48128714ad290
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/05/2018
---
# <a name="use-for-json-output-in-sql-server-and-in-client-apps-sql-server"></a>Utiliser la sortie de FOR JSON dans SQL Server et les applications clientes (SQL Server)
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]

Les exemples suivants montrent comment utiliser la clause **FOR JSON** et sa sortie JSON dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou les applications clientes.  
  
## <a name="use-for-json-output-in-sql-server-variables"></a>Utiliser la sortie de FOR JSON dans des variables SQL Server  
La sortie de la clause FOR JSON est de type NVARCHAR(MAX). Vous pouvez donc l’assigner à une variable, comme indiqué dans l’exemple suivant.  
  
```sql  
DECLARE @x NVARCHAR(MAX) = (SELECT TOP 10 * FROM Sales.SalesOrderHeader FOR JSON AUTO)  
```  
  
## <a name="use-for-json-output-in-sql-server-user-defined-functions"></a>Utiliser la sortie de FOR JSON dans des fonctions SQL Server définies par l’utilisateur  
 Vous pouvez créer des fonctions définies par l’utilisateur qui convertissent les jeux de résultats au format JSON et renvoient cette sortie JSON. l’exemple suivant crée une fonction définie par l’utilisateur, qui extrait certaines lignes de détails de commande et les organise en un tableau JSON.  
  
```sql  
CREATE FUNCTION GetSalesOrderDetails(@salesOrderId int)  
 RETURNS NVARCHAR(MAX)  
AS  
BEGIN  
   RETURN (SELECT UnitPrice, OrderQty  
           FROM Sales.SalesOrderDetail  
           WHERE SalesOrderID = @salesOrderId  
           FOR JSON AUTO)  
END
```  
  
 Vous pouvez utiliser cette fonction dans un lot ou une requête, comme indiqué dans l’exemple suivant.  
  
```sql  
DECLARE @x NVARCHAR(MAX) = dbo.GetSalesOrderDetails(43659)

PRINT dbo.GetSalesOrderDetails(43659)

SELECT TOP 10
  H.*, dbo.GetSalesOrderDetails(H.SalesOrderId) AS Details
FROM Sales.SalesOrderHeader H
```  
  
## <a name="merge-parent-and-child-data-into-a-single-table"></a>Fusionner les données parentes et enfants dans une seule table  
Dans l’exemple suivant, chaque ensemble de lignes enfants est mis en forme en tant que tableau JSON. Le tableau JSON devient la valeur de la colonne Détails dans la table parente.  
  
```sql  
SELECT TOP 10 SalesOrderId, OrderDate,  
      (SELECT TOP 3 UnitPrice, OrderQty  
         FROM Sales.SalesOrderDetail D  
         WHERE H.SalesOrderId = D.SalesOrderID  
         FOR JSON AUTO) AS Details  
INTO SalesOrder  
FROM Sales.SalesOrderHeader H  
```  
  
## <a name="update-the-data-in-json-columns"></a>Mettre à jour les données dans les colonnes JSON  
 L’exemple suivant montre comment mettre à jour la valeur d’une colonne qui contient du texte JSON.  
  
```sql  
UPDATE SalesOrder  
SET Details =  
     (SELECT TOP 1 UnitPrice, OrderQty  
       FROM Sales.SalesOrderDetail D  
       WHERE D.SalesOrderId = SalesOrder.SalesOrderId  
      FOR JSON AUTO 
```  
  
## <a name="use-for-json-output-in-a-c-client-app"></a>Utiliser la sortie de FOR JSON dans une application cliente C#  
 l’exemple suivant montre comment récupérer la sortie JSON d’une requête dans un objet StringBuilder d’une application cliente C#. Supposons que la variable `queryWithForJson` contienne le texte d’une instruction SELECT avec une clause FOR JSON.  
  
```csharp  
var queryWithForJson = "SELECT ... FOR JSON";
var conn = new SqlConnection("<connection string>");
var cmd = new SqlCommand(queryWithForJson, conn);
conn.Open();
var jsonResult = new StringBuilder();
var reader = cmd.ExecuteReader();
if (!reader.HasRows)
{
    jsonResult.Append("[]");
}
else
{
    while (reader.Read())
    {
        jsonResult.Append(reader.GetValue(0).ToString());
    }
}
```  

## <a name="learn-more-about-the-built-in-json-support-in-sql-server"></a>En savoir plus sur la prise en charge intégrée de JSON dans SQL Server  
Pour accéder à un grand nombre de solutions spécifiques, de cas d’usage et de recommandations, consultez les [billets de blog sur la prise en charge intégrée de JSON](http://blogs.msdn.com/b/sqlserverstorageengine/archive/tags/json/) dans SQL Server et Azure SQL Database, écrits par Jovan Popovic (Microsoft Program Manager).
 
## <a name="see-also"></a> Voir aussi  
 [Mettre les résultats de requête au format JSON avec FOR JSON &#40;SQL Server&#41;](../../relational-databases/json/format-query-results-as-json-with-for-json-sql-server.md)  
  
  
