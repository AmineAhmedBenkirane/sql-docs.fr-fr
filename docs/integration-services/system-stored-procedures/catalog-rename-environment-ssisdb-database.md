---
title: "catalog.rename_environment (base de données SSISDB) | Microsoft Docs"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: c73d7452-31c5-4f4e-afcc-e9eca760c826
caps.latest.revision: "13"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: fab134694401fa13f2798fcd5a5ef0787dc14f52
ms.sourcegitcommit: 7f8aebc72e7d0c8cff3990865c9f1316996a67d5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2017
---
# <a name="catalogrenameenvironment-ssisdb-database"></a>catalog.rename_environment (base de données SSISDB)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Renomme un environnement dans le catalogue [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```sql  
catalog.rename_environment [ @folder_name = ] folder_name  
    , [ @environment_name = ] environment_name  
    , [ @new_environment_name= ] new_environment_name  
```  
  
## <a name="arguments"></a>Arguments  
 [ @folder_name = ] *folder_name*  
 Nom du dossier qui contient l'environnement. *folder_name* est de type **nvarchar(128)**.  
  
 [ @environment_name = ] *environment_name*  
 Nom d'origine de l'environnement. *environment_name* est de type **nvarchar(128)**.  
  
 [ @new_environment_name = ] *new_environment_name*  
 Nouveau nom de l'environnement. *new_environment_name* est de type **nvarchar(128)**.  
  
## <a name="return-code-value"></a>Valeur du code de retour  
 0 (succès)  
  
## <a name="result-sets"></a>Jeux de résultats  
 Aucune  
  
## <a name="permissions"></a>Permissions  
 Cette procédure stockée requiert l'une des autorisations suivantes :  
  
-   Autorisations MODIFY sur l'environnement  
  
-   Appartenance au rôle de base de données **ssis_admin**  
  
-   Appartenance au rôle serveur **sysadmin**  
  
## <a name="errors-and-warnings"></a>Erreurs et avertissements  
 La liste suivante décrit quelques conditions qui peuvent générer une erreur ou un avertissement :  
  
-   Le nom d'environnement d'origine n'est pas valide  
  
-   Le nouveau nom a déjà été utilisé dans un environnement existant  
  
## <a name="remarks"></a>Notes  
 Les références environnementales des projets ne sont pas mises à jour automatiquement lorsque vous renommez l'environnement. Les références environnementales doivent être mises à jour en conséquence. Cette procédure stockée réussira même si les références environnementales sont arrêtées en modifiant le nom d'un environnement. Les références environnementales doivent être mises à jour après que cette procédure stockée s'est achevée.  
  
> [!NOTE]  
>  Lorsqu'une référence environnementale n'est pas valide, la validation et l'exécution des packages correspondants qui utilisent ces références échoueront.  
  
  
