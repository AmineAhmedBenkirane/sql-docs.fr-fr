---
title: "Catalog.grant_permission (base de données SSISDB) | Documents Microsoft"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords:
- grant_permission stored procedure [Integration Services]
- catalog.grant_permission stored procedure [Integration Services]
ms.assetid: e72cfd52-de66-45e9-98b9-b8580ac7b956
caps.latest.revision: 25
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 71ca2fac0a6b9f087f9d434c5a701f5656889b9e
ms.openlocfilehash: 5f9bb38521631bcc60d39fba747f17b86183545d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/13/2017

---
# <a name="cataloggrantpermission-ssisdb-database"></a>catalog.grant_permission (base de données SSISDB)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Accorde une autorisation sur un objet sécurisable dans le catalogue [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```sql
catalog.grant_permission [ @object_type = ] object_type  
    , [ @object_id = ] object_id  
    , [ @principal_id = ] principal_id  
    , [ @permission_type = ] permission_type  
```  
  
## <a name="arguments"></a>Arguments  
 [ @object_type =] *object_type*  
 Type d'objet sécurisable. Types d’objets sécurisables incluent le dossier (`1`), projet (`2`), environnement (`3`) et l’opération (`4`). Le *object_type* est **smallint***.*  
  
 [ @object_id =] *object_id*  
 Identificateur unique (ID) de l'objet sécurisable. Le *object_id* est **bigint**.  
  
 [ @principal_id =] *principal_id*  
 ID du principal auquel accorder l'autorisation. Le *principal_id* est **int**.  
  
 [ @permission_type =] *permission_type*  
 Type d'autorisation à accorder. Le *permission_type* est **smallint**.  
  
## <a name="return-code-values"></a>Valeurs des codes de retour  
 0 (succès)  
  
 1 (object_class n’est pas valide)  
  
 2 (object_id n’existe pas)  
  
 3 (principal n’existe pas)  
  
 4 (autorisation n’est pas valide)  
  
 5 (autre erreur)  
  
## <a name="result-sets"></a>Jeux de résultats  
 Aucune  
  
## <a name="permissions"></a>Permissions  
 Cette procédure stockée requiert l'une des autorisations suivantes :  
  
-   Autorisations ASSIGN_PERMISSIONS sur l'objet  
  
-   L’appartenance à la **ssis_admin** rôle de base de données  
  
-   L’appartenance à la **sysadmin** rôle de serveur  

Cette procédure ne peut pas être appelée par les connexions qui ont été authentifiées par SQL Server. Il ne peut pas être appelé par la connexion sa.
  
## <a name="remarks"></a>Notes  
 Cette procédure stockée vous permet d'accorder les types d'autorisation décrits dans le tableau suivant :  
  
|Valeur permission_type|Nom de l'autorisation|Description de l'autorisation|Types d'objet applicables|  
|----------------------------|---------------------|----------------------------|-----------------------------|  
|`1`|READ|Permet au principal de lire des informations considérées comme faisant partie de l'objet, telles que les propriétés. Il n'autorise pas le principal à énumérer ou à lire le contenu d'autres objets contenus dans l'objet.|Dossier, projet, environnement, opération|  
|`2`|MODIFY|Permet au principal de modifier des informations considérées comme faisant partie de l'objet, telles que les propriétés. Il ne permet pas au principal de modifier d'autres objets contenus dans l'objet.|Dossier, projet, environnement, opération|  
|`3`|Exécutez|Permet au principal d'exécuter tous les packages dans le projet.|Projet|  
|`4`|MANAGE_PERMISSIONS|Permet au principal d'affecter des autorisations aux objets.|Dossier, projet, environnement, opération|  
|`100`|CREATE_OBJECTS|Permet au principal de créer des objets dans le dossier.|Dossier|  
|`101`|READ_OBJECTS|Permet au principal de lire tous les objets dans le dossier.|Dossier|  
|`102`|MODIFY_OBJECTS|Permet au principal de modifier tous les objets dans le dossier.|Dossier|  
|`103`|EXECUTE_OBJECTS|Permet au principal d'exécuter tous les packages de tous les projets dans le dossier.|Dossier|  
|`104`|MANAGE_OBJECT_PERMISSIONS|Permet au principal de gérer des autorisations sur tous les objets dans le dossier.|Dossier|  
  
## <a name="errors-and-warnings"></a>Erreurs et avertissements  
 Consultez la section qui traite des valeurs de code de retour pour les erreurs et les messages pertinents.  
  
  

