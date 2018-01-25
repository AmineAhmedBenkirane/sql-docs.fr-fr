---
title: ASSEMBLYPROPERTY (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 07/24/2017
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
- ASSEMBLYPROPERTY_TSQL
- ASSEMBLYPROPERTY
dev_langs: TSQL
helpviewer_keywords:
- ASSEMBLYPROPERTY statement
- assemblies [CLR integration], properties
ms.assetid: cf03d1b1-724c-48bf-a8df-3fe2586b150a
caps.latest.revision: "40"
author: barbkess
ms.author: barbkess
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a38d9f773e010ab779204d7c92b351d88c0d08f7
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="assemblyproperty-transact-sql"></a>ASSEMBLYPROPERTY (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

Renvoie des informations sur une propriété d'un assembly.
  
![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntaxe  
  
```sql
ASSEMBLYPROPERTY('assembly_name', 'property_name')  
```  
  
## <a name="arguments"></a>Arguments  
*assembly_name*  
Nom de l'assembly.
  
*property_name*  
Nom de la propriété sur laquelle des informations doivent être extraites. *property_name* peut prendre l’une des valeurs suivantes.
  
|Valeur| Description|  
|---|---|
|**CultureInfo**|Paramètres régionaux de l'assembly.|  
|**PublicKey**|Clé publique ou jeton de clé publique de l'assembly.|  
|**MvID**|Numéro d'identification de version complet de l'assembly, qui est généré par le compilateur.|  
|**VersionMajor**|Composant principal (première partie) du numéro d'identification de version en quatre parties de l'assembly.|  
|**VersionMinor**|Composant mineur (deuxième partie) du numéro d'identification de version en quatre parties de l'assembly.|  
|**VersionBuild**|Composant de version (troisième partie) du numéro d'identification de version en quatre parties de l'assembly.|  
|**VersionRevision**|Composant de révision (quatrième partie) du numéro d'identification de version en quatre parties de l'assembly.|  
|**SimpleName**|Nom simple de l'assembly.|  
|**Architecture**|Architecture du processeur de l'assembly.|  
|**CLRName**|Chaîne canonique qui encode le nom simple, le numéro de version, les paramètres régionaux, la clé publique, et l'architecture de l'assembly. Cette valeur identifie de façon univoque l'assembly du côté CLR (Common Language Runtime).|  
  
## <a name="return-type"></a>Type de retour
**sql_variant**
  
## <a name="examples"></a>Exemples  
L'exemple suivant suppose qu'un assembly `HelloWorld` est enregistré dans la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]. Pour plus d’informations, consultez [exemple Hello World](http://msdn.microsoft.com/library/fed6c358-f5ee-4d4c-9ad6-089778383ba7).
  
```sql
USE AdventureWorks2012;  
GO  
SELECT ASSEMBLYPROPERTY ('HelloWorld' , 'PublicKey');  
```  
  
## <a name="see-also"></a>Voir aussi
[CREATE ASSEMBLY &#40;Transact-SQL&#41;](../../t-sql/statements/create-assembly-transact-sql.md)  
[DROP ASSEMBLY &#40;Transact-SQL&#41;](../../t-sql/statements/drop-assembly-transact-sql.md)
  
  
