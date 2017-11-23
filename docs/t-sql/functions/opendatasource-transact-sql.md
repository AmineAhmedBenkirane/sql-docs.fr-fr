---
title: OPENDATASOURCE (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- OPENDATASOURCE
- OPENDATASOURCE_TSQL
dev_langs: TSQL
helpviewer_keywords:
- data sources [SQL Server]
- OPENDATASOURCE function
- remote data access [SQL Server], OPENDATASOURCE
- ad hoc distributed queries
- OLE DB data sources [SQL Server]
- ad hoc connection information
ms.assetid: 5510b846-9cde-4687-8798-be9a273aad31
caps.latest.revision: "41"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: e2ddb99a84c910c89aedaa086eb10e3f9de7abb9
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="opendatasource-transact-sql"></a>OPENDATASOURCE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Fournit les informations de connexion appropriées pour un nom d'objet en quatre parties sans utiliser de nom de serveur lié.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
OPENDATASOURCE ( provider_name, init_string )  
```  
  
## <a name="arguments"></a>Arguments  
 *Nom_Fournisseur*  
 Nom enregistré comme PROGID du fournisseur OLE DB utilisé pour accéder à la source de données. *Nom_Fournisseur* est un **char** type de données, sans valeur par défaut.  
  
 *init_string*  
 La chaîne de connexion est passée à l’interface IDataInitialize du fournisseur de destination. La syntaxe de chaîne du fournisseur est basée sur des paires mot clé-valeur séparées par des points-virgules, par exemple : **'***mot_clé1*=*valeur***;** *mot Clé2*=*valeur***'**.  
  
 Pour plus d'informations sur les paires mot clé-valeur prises en charge par le fournisseur, consultez le kit de développement logiciel (SDK) de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Data Access. Cette documentation définit la syntaxe de base. Le tableau suivant mots-clés répertorie les plus fréquemment utilisées dans les *init_string* argument.  
  
|Mot clé|Propriété OLE DB|Valeurs admises et description|  
|-------------|---------------------|----------------------------------|  
|Source de données|DBPROP_INIT_DATASOURCE|Nom de la source de données à laquelle la connexion doit être établie. Ceci est interprété différemment selon les fournisseurs. Pour le fournisseur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB, cette propriété indique le nom du serveur. Pour le fournisseur Jet OLE DB, elle indique le chemin d'accès complet au fichier .mdb ou .xls.|  
|Emplacement|DBPROP_INIT_LOCATION|Emplacement de la base de données à laquelle la connexion doit être établie|  
|Extended Properties|DBPROP_INIT_PROVIDERSTRING|Chaîne de connexion spécifique au fournisseur|  
|Connect timeout|DBPROP_INIT_TIMEOUT|Délai d'expiration au bout duquel la tentative de connexion échoue|  
|ID d'utilisateur|DBPROP_AUTH_USERID|ID utilisateur à utiliser pour la connexion|  
|Mot de passe|DBPROP_AUTH_PASSWORD|Mot de passe à utiliser pour la connexion|  
|Catalogue|DBPROP_INIT_CATALOG|Nom du catalogue initial ou par défaut lors de la connexion à la source de données|  
|Sécurité intégrée|DBPROP_AUTH_INTEGRATED|SSPI pour spécifier l'authentification Windows|  
  
## <a name="remarks"></a>Notes  
 OPENDATASOURCE ne peut être utilisé pour accéder à des données distantes à partir de sources de données OLE DB que si l'option de Registre DisallowAdhocAccess est explicitement définie avec la valeur 0 pour le fournisseur spécifié et que l'option de configuration avancée Ad Hoc Distributed Queries est activée. Lorsque ces options ne sont pas définies, le comportement par défaut n'autorise pas l'accès d'égal à égal.  
  
 La fonction OPENDATASOURCE peut être utilisée dans les mêmes emplacements de syntaxe [!INCLUDE[tsql](../../includes/tsql-md.md)] qu'un nom de serveur lié. OPENDATASOURCE peut donc constituer la première des quatre parties d'un nom qui fait référence à un nom de table ou de vue (dans une instruction SELECT, INSERT, UPDATE ou DELETE) ou à une procédure stockée distante (dans une instruction EXECUTE). Lors de l'exécution de procédures stockées distantes, OPENDATASOURCE doit faire référence à une autre instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. OPENDATASOURCE n'accepte pas de variables pour ses arguments.  
  
 Comme la fonction OPENROWSET, OPENDATASOURCE doit uniquement faire référence à des sources de données OLE DB qui ne sont pas sollicitées fréquemment. Définissez un serveur lié pour toutes les sources de données qui font l'objet de nombreux accès. OPENDATASOURCE et OPENROWSET n'offrent pas toutes les fonctionnalités des définitions de serveur lié, en particulier en ce qui concerne la gestion de la sécurité et la consultation des informations du catalogue. Toutes les informations de connexion, y compris les mots de passe, doivent être fournies à chaque appel de OPENDATASOURCE.  
  
> [!IMPORTANT]  
>  L'authentification Windows est plus sûre que l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Veillez à utiliser l'authentification Windows chaque fois que c'est possible. OPENDATASOURCE ne doit pas être utilisé avec des mots de passe explicites dans la chaîne de connexion.  
  
 Les exigences de connexion pour chaque fournisseur sont semblables à celles de ces paramètres lors de la création de serveurs liés. Les détails de nombreux fournisseurs courants sont répertoriés dans la rubrique [sp_addlinkedserver &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql.md).  
  
 Tout appel à OPENDATASOURCE, OPENQUERY ou OPENROWSET dans la clause FROM est évalué séparément et indépendamment de tout appel à ces fonctions utilisé comme cible de la mise à jour, même si des arguments identiques sont fournis aux deux appels. En particulier, les conditions de filtre ou de jointure appliquées sur le résultat de l'un de ces appels n'ont aucun effet sur les résultats de l'autre.  
  
## <a name="permissions"></a>Permissions  
 Tous les utilisateurs peuvent exécuter OPENDATASOURCE. Les autorisations utilisées pour la connexion au serveur distant sont déterminées à partir de la chaîne de connexion.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant crée une connexion appropriée à l'instance `Payroll` de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur le serveur `London`, puis interroge la table `AdventureWorks2012.HumanResources.Employee`. (L'utilisation de SQLNCLI et [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vous redirigera vers la version la plus récente du fournisseur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB.)  
  
```  
SELECT *  
FROM OPENDATASOURCE('SQLNCLI',  
    'Data Source=London\Payroll;Integrated Security=SSPI')  
    .AdventureWorks2012.HumanResources.Employee  
```  
  
 L’exemple suivant crée une connexion ad hoc avec une feuille de calcul Excel au format de document Word 1997 - 2003.  
  
```  
SELECT * FROM OPENDATASOURCE('Microsoft.Jet.OLEDB.4.0',  
'Data Source=C:\DataFolder\Documents\TestExcel.xls;Extended Properties=EXCEL 5.0')...[Sheet1$] ;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [OPENROWSET &#40;Transact-SQL&#41;](../../t-sql/functions/openrowset-transact-sql.md)   
 [sp_addlinkedserver &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql.md)  
  
  
