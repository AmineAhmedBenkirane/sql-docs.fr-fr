---
title: "Catalog.create_environment (base de données SSISDB) | Documents Microsoft"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 66367092-9f6e-40e6-90bd-81efb078ab70
caps.latest.revision: 16
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 2d3ff080d50545b75a416e459b73ebd8bbb44666
ms.contentlocale: fr-fr
ms.lasthandoff: 09/26/2017

---
# <a name="catalogcreateenvironment-ssisdb-database"></a>catalog.create_environment (base de données SSISDB)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Crée un environnement dans le catalogue [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```tsql  
create_environment [ @folder_name = ] folder_name  
     , [ @environment_name = ] environment_name  
  [  , [ @environment_description = ] environment_description ]  
```  
  
## <a name="arguments"></a>Arguments  
 [ @folder_name =] *nom_dossier*  
 Nom du dossier qui contiendra l'environnement. Le *nom_dossier* est **nvarchar (128)**.  
  
 [ @environment_name =] *environment_name*  
 Nom de l'environnement. Le *environment_name* est **nvarchar (128)**.  
  
 [ @environment_description=] *environment_description*  
 Description facultative de l'environnement. Le *environment_description* est **nvarchar (1024)**.  
  
## <a name="return-code-value"></a>Valeur de Code de retour  
 0 (succès)  
  
## <a name="result-sets"></a>Jeux de résultats  
 Aucune  
  
## <a name="permissions"></a>Permissions  
 Cette procédure stockée requiert l'une des autorisations suivantes :  
  
-   Autorisations READ et MODIFY sur le dossier  
  
-   L’appartenance à la **ssis_admin** rôle de base de données  
  
-   d'un rôle de base de données ;  
  
-   L’appartenance à la **sysadmin** rôle de serveur  
  
## <a name="errors-and-warnings"></a>Erreurs et avertissements  
 La liste suivante décrit quelques conditions qui peuvent générer une erreur ou un avertissement :  
  
-   Le nom du dossier est introuvable  
  
-   Un environnement qui a le même nom existe déjà dans le dossier spécifié  
  
## <a name="remarks"></a>Notes  
 Le nom de l'environnement doit être unique dans le dossier.  
  
  
