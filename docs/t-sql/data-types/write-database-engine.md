---
title: "Write (moteur de base de données) | Documents Microsoft"
ms.custom: 
ms.date: 7/23/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|data-types
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Write_TSQL
- Write
dev_langs: TSQL
helpviewer_keywords: Write [Database Engine]
ms.assetid: 7c554334-d2d9-4eae-a4ae-097aa4020e1a
caps.latest.revision: "13"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 11980f26c4af4a2dabb57e5cce242d7e89028d16
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="write-database-engine"></a>Write (moteur de base de données)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Écrit une représentation binaire de d’écriture **SqlHierarchyId** dans le passé **BinaryWriter**. L’écriture ne peut pas être appelée à l’aide de [!INCLUDE[tsql](../../includes/tsql-md.md)]. Utilisez plutôt CAST ou CONVERT.
  
## <a name="syntax"></a>Syntaxe  
  
```sql
void Write( BinaryWriter w )   
```  
  
## <a name="arguments"></a>Arguments  
*w*  
A **BinaryWriter** objet auquel la représentation binaire de ce **hierarchyid** nœud sera écrite.
  
## <a name="return-types"></a>Types de retour  
**CLR de type de retour : void**
  
## <a name="remarks"></a>Notes  
Écriture est utilisée en interne par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lorsqu’il est nécessaire, comme lors du chargement des données d’une **hierarchyid** colonne. Écriture est également appelée en interne lorsqu’une conversion est effectuée entre **hierarchyid** et **varbinary**.
  
## <a name="examples"></a>Exemples  
  
```sql
MemoryStream stream = new MemoryStream();  
BinaryWriter bw = new BinaryWriter(stream);  
hid.Write(bw);  
byte[] encoding = stream.ToArray();  
  
```  
  
## <a name="see-also"></a>Voir aussi
[Lecture &#40; moteur de base de données &#41;](../../t-sql/data-types/read-database-engine.md)  
[ToString &#40; moteur de base de données &#41;](../../t-sql/data-types/tostring-database-engine.md)  
[CAST et CONVERT &#40;Transact-SQL&#41;](../../t-sql/functions/cast-and-convert-transact-sql.md)  
[Référence de méthodes de type de données hierarchyid](http://msdn.microsoft.com/library/01a050f5-7580-4d5f-807c-7f11423cbb06)
  
  
