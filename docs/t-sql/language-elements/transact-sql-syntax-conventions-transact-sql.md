---
title: Conventions de syntaxe Transact-SQL (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: t-sql|language-elements
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: sql13.TSQLExpandPortal.f1
dev_langs: TSQL
helpviewer_keywords:
- conventions [SQL Server]
- Applies to section in Transact-SQL topics
- code example conventions [SQL Server]
- objects [SQL Server], names
- code [SQL Server], conventions
- multipart names [SQL Server]
- Transact-SQL syntax conventions
- syntax conventions [SQL Server]
- code [SQL Server]
- Transact-SQL
- naming conventions [SQL Server]
- syntax [SQL Server], Transact-SQL
ms.assetid: 35fbcf7f-8b55-46cd-a957-9b8c7b311241
caps.latest.revision: "55"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Active
ms.openlocfilehash: 7c4eb67190b5123296fbcffb3fac3f09e9ec2000
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="transact-sql-syntax-conventions-transact-sql"></a>Conventions de la syntaxe Transact-SQL (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Le tableau suivant répertorie et décrit les conventions utilisées dans les diagrammes de syntaxe du Guide de référence [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
|Convention|Utilisé pour|  
|----------------|--------------|  
|MAJUSCULES|Mots clés [!INCLUDE[tsql](../../includes/tsql-md.md)].|  
|*italique*|Paramètres de syntaxe [!INCLUDE[tsql](../../includes/tsql-md.md)] fournis par l'utilisateur.|  
|**gras**|Noms de bases de données, de tables, de colonnes, d'index, de procédures stockées, d'utilitaires, de types de données et de textes à taper tel qu'indiqués.|  
|**underline**|Indique que l'instruction est omise par la valeur par défaut appliquée lorsque la clause contient la valeur soulignée.|  
|&#124; (barre verticale)|Sépare les éléments de syntaxe placés entre crochets ou entre accolades. Vous ne pouvez utiliser qu'un seul de ces éléments.|  
|`[ ]` (crochets)|Éléments de syntaxe facultatifs. Ne tapez pas les crochets.|  
|{} (accolades)|Éléments de syntaxe obligatoires. Ne tapez pas les accolades.|  
|[**,**...*n*]|Indique l’élément précédent peut se répéter  *n*  nombre de fois. Les occurrences sont séparées par des virgules.|  
|[...*n*]|Indique l’élément précédent peut se répéter  *n*  nombre de fois. Les occurrences sont séparées par des espaces.|  
|;|Terminateur d'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)]. Bien que le point-virgule ne soit pas requis pour la plupart des instructions dans cette version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], il sera requis dans une version à venir.|  
|\<label> ::=|Nom d'un bloc de syntaxe. Cette convention est utilisée pour regrouper et étiqueter des sections de syntaxe longue ou une unité de syntaxe pouvant apparaître à plusieurs emplacements au sein d'une instruction. Chaque emplacement dans lequel le bloc de syntaxe peut être utilisé est signalé par une étiquette encadrée de chevrons : \<étiquette >.<br /><br /> Un jeu est une collection d’expressions, par exemple \<jeu de regroupement > ; une liste est une collection de jeux, par exemple \<liste d’éléments composites >.|  
  
## <a name="multipart-names"></a>Noms à plusieurs composantes  
 Sauf indication contraire, toutes les références [!INCLUDE[tsql](../../includes/tsql-md.md)] au nom d'un objet de base de données peuvent prendre la forme d'un nom à quatre composantes, comme suit :  
  
 *server_name* **.**[*database_name*]**.**[*schema_name*]**.***object_name*  
  
 | *database_name***.**[*schema_name*]**.***object_name*  
  
 | *schema_name***.***object_name*  
  
 *| object_name*  
  
 *server_name*  
 Spécifie un nom de serveur lié ou un nom de serveur distant.  
  
 *database_name*  
 Spécifie le nom d'une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lorsque l'objet réside dans une instance locale de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Lorsque l’objet est dans un serveur lié, *nom_base_de_données* désigne un catalogue OLE DB.  
  
 *schema_name*  
 Spécifie le nom du schéma contenant l'objet si celui-ci réside dans une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Lorsque l’objet est dans un serveur lié, *schema_name* spécifie un nom de schéma OLE DB.  
  
 *object_name*  
 Fait référence au nom de l'objet.  
  
 Lorsque vous faites référence à un objet en particulier, il n'est pas toujours nécessaire de spécifier le serveur, la base de données et le schéma pour que le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] l'identifie. Toutefois, si l’objet ne peut pas être trouvé, une erreur est retournée.  
  
> [!NOTE]  
>  Pour éviter des erreurs relatives à la résolution du nom, nous vous recommandons de spécifier le nom du schéma chaque fois que vous indiquez un objet correspondant.  
  
 Pour omettre des nœuds intermédiaires, utilisez des points pour indiquer ces emplacements. Le tableau suivant répertorie les formats valides des noms d'objets.  
  
|Format de la référence d'objet| Description|  
|-----------------------------|-----------------|  
|*server* **.** *database* **.** *schema* **.** *objet*|Nom à quatre composantes.|  
|*server* **.** *base de données* **...** *objet*|Le nom du schéma est omis.|  
|*server* **..** *schema* **.** *objet*|Le nom de la base de données est omis.|  
|*server* **...** *object*|Les noms de la base de données et du schéma sont omis.|  
|*database* **.** *schema* **.** *objet*|Le nom du serveur est omis.|  
|*base de données* **...** *objet*|Les noms du serveur et du schéma sont omis.|  
|*schema* **.** *objet*|Les noms du serveur et de la base de données sont omis.|  
|*objet*|Les noms du serveur, de la base de données et du schéma sont omis.|  
  
## <a name="code-example-conventions"></a>Conventions des exemples de code  
 Sauf indication contraire, les exemples fournis dans le Guide de référence [!INCLUDE[tsql](../../includes/tsql-md.md)] ont été testés à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] et de ses paramètres par défaut pour les options suivantes :  
  
-   ANSI_NULLS  
  
-   ANSI_NULL_DFLT_ON  
  
-   ANSI_PADDING  
  
-   ANSI_WARNINGS  
  
-   CONCAT_NULL_YIELDS_NULL  
  
-   QUOTED_IDENTIFIER  
  
 La plupart des exemples de code figurant dans le Guide de référence [!INCLUDE[tsql](../../includes/tsql-md.md)] ont été testés sur des serveurs prenant en charge un ordre de tri respectant la casse. Généralement, les serveurs de test ont exécuté la page de codes ANSI/ISO 1252.  
  
 Les constantes de chaîne de caractères Unicode avec la lettre du préfixe de nombreux exemples de code **N**. Sans le **N** préfixe, la chaîne est convertie en page de codes par défaut de la base de données. Cette page risque de ne pas reconnaître certains caractères.  
  
## <a name="applies-to-references"></a>Informations de référence de type « S'applique à »  
 Le [!INCLUDE[tsql](../../includes/tsql-md.md)] référence inclut des articles relatifs aux [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)], et [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)]. Au début de chaque article est une section indiquant les produits qui prennent en charge le sujet de l’article. Si un produit est omis, la fonctionnalité décrite par l’article n’est pas disponible dans ce produit. Par exemple, les groupes de disponibilité ont été introduits dans [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]. Le **créer un groupe de disponibilité** article indique qu’il s’applique à **SQL Server (SQL Server 2012 jusqu'à la version actuelle)** , car il ne s’applique pas aux [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], ou [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].  
  
 Dans certains cas, le sujet général de l’article peut être utilisé dans un produit, mais tous les arguments ne sont pas pris en charge. Par exemple, les utilisateurs de base de données à relation contenant-contenu ont été introduits dans [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]. Le **CREATE USER** instruction peut être utilisée dans les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] produit, mais la **avec mot de passe** syntaxe ne peut pas être utilisée avec les versions antérieures. Dans ce cas, supplémentaire **s’applique à** sections sont insérées dans les descriptions des arguments appropriés dans le corps de l’article.  
  
## <a name="see-also"></a>Voir aussi  
 [Référence Transact-SQL &#40;moteur de base de données&#41;](../../t-sql/transact-sql-reference-database-engine.md)  
  
  


