---
title: "catalog.configure_catalog (base de données SSISDB) | Microsoft Docs"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 72690c61-f462-4c25-9fce-08a687b0bd41
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 6d1f8926d398a90214a5ad1903f04ac1e29d8854
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="catalogconfigurecatalog-ssisdb-database"></a>catalog.configure_catalog (base de données SSISDB)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Configure le catalogue [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en définissant une propriété de catalogue sur une valeur spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```sql
catalog.configure_catalog [ @property_name = ] property_name , [ @property_value = ] property_value  
```  
  
## <a name="arguments"></a>Arguments  
 [ @property_name = ] *property_name*  
 Nom de la propriété de catalogue. *property_name* est de type **nvarchar(255)**. Pour plus d’informations sur les propriétés disponibles, consultez [catalog.catalog_properties &#40;base de données SSISDB&#41;](../../integration-services/system-views/catalog-catalog-properties-ssisdb-database.md).  
  
 [ @property_value = ] *property_value*  
 Valeur de la propriété de catalogue. *property_value* est de type **nvarchar(255)**. Pour plus d’informations sur les valeurs de propriété, consultez [catalog.catalog_properties &#40;base de données SSISDB&#41;](../../integration-services/system-views/catalog-catalog-properties-ssisdb-database.md).  
  
## <a name="return-code-values"></a>Valeurs des codes de retour  
 0 (réussite) ou 1 (échec)  
  
## <a name="result-sets"></a>Jeux de résultats  
 None  
  
## <a name="remarks"></a>Notes   
 Cette procédure stockée détermine si le *property_value* est valide pour chaque *property_name*.  
  
 Cette procédure stockée peut être effectuée uniquement lorsqu'il n'y a pas d'exécution active, c'est-à-dire pas d'exécutions en attente, en file d'attente, en cours d'exécution ou suspendues.  
  
 Pendant que le catalogue est configuré, toutes les autres procédures stockées du catalogue échouent avec le message d’erreur « La configuration du serveur est en cours ».
  
 Lorsque le catalogue est configuré, une entrée est écrite dans le journal des opérations.  
  
## <a name="permissions"></a>Autorisations  
 Cette procédure stockée requiert l'une des autorisations suivantes :  
  
-   Appartenance au rôle de base de données **ssis_admin**  
  
-   Appartenance au rôle serveur **sysadmin**  
  
## <a name="errors-and-warnings"></a>Erreurs et avertissements  
 La liste suivante décrit quelques conditions qui peuvent générer une erreur ou un avertissement :  
  
-   La propriété n'existe pas  
  
-   La valeur de la propriété n'est pas valide  
  
  
