---
title: dbo.syscategories (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-tables
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- dbo.syscategories_TSQL
- syscategories
- syscategories_TSQL
- dbo.syscategories
dev_langs:
- TSQL
helpviewer_keywords:
- syscategories system table
ms.assetid: eb2cb75c-dc58-4a5b-b329-664e9fe20ce0
caps.latest.revision: 
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 870bd7217d215b7304ceed911d0dd8da2cca5837
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2018
---
# <a name="dbosyscategories-transact-sql"></a>dbo.syscategories (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Contient les catégories utilisées par [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour organiser les travaux, les alertes et les opérateurs. Cette table est stockée dans le **msdb** base de données.  
  
|Nom de colonne|Type de données| Description|  
|-----------------|---------------|-----------------|  
|**category_id**|**int**|Identifiant de la catégorie|  
|**category_class**|**int**|Type d'élément dans la catégorie :<br /><br /> **1** = travail<br /><br /> **2** = alerte<br /><br /> **3** = (opérateur)|  
|**category_type**|**tinyint**|Type de catégorie :<br /><br /> **1** = local<br /><br /> **2** = multiserveur<br /><br /> **3** = none|  
|**nom**|**sysname**|Nom de la catégorie|  
  
  
