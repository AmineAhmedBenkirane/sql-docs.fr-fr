---
title: App_name (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 07/24/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- APP_NAME_TSQL
- APP_NAME
dev_langs:
- TSQL
helpviewer_keywords:
- name checking for current session [SQL Server]
- sessions [SQL Server], application names
- applications [SQL Server], names
- current session application names
- APP_NAME function
ms.assetid: e491e192-9b30-4243-bc19-33c133fe08a8
caps.latest.revision: 35
author: edmacauley
ms.author: edmaca
manager: cguyer
ms.workload: On Demand
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: c4f63ae216bad0269415ac5e0aa57a7543500f0c
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="appname-transact-sql"></a>APP_NAME (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Retourne le nom de l'application pour la session en cours si un nom a été défini par l'application.
  
> [!IMPORTANT]  
>  Le nom de l'application est fourni par le client et n'est aucunement vérifié. N’utilisez pas **APP_NAME** dans le cadre d’une vérification de sécurité.  
  
![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntaxe  
  
```sql
  
APP_NAME  ( )  
```  
  
## <a name="return-types"></a>Types de retour  
**nvarchar (128)**
  
## <a name="remarks"></a>Notes  
Utilisez **APP_NAME** lorsque vous souhaitez exécuter des actions différentes pour différentes applications. Par exemple, pour mettre en forme une date de plusieurs façons pour différentes applications ou pour retourner un message d'informations à certaines applications.
  
Pour définir un nom d’application dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], dans le **se connecter au moteur de base de données** boîte de dialogue, cliquez sur **Options**. Sur le **paramètres de connexion supplémentaires** onglet, fournissez un **application** attribut dans le format`;app='application_name'`
  
## <a name="examples"></a>Exemples  
L'exemple suivant vérifie si l'application cliente qui a lancé ce traitement est une session `SQL Server Management Studio` et fournit une date au format US ou ANSI.
  
```sql
USE AdventureWorks2012;  
GO  
IF APP_NAME() = 'Microsoft SQL Server Management Studio - Query'  
PRINT 'This process was started by ' + APP_NAME() + '. The date is ' + CONVERT ( varchar(100) , GETDATE(), 101) + '.';  
ELSE   
PRINT 'This process was started by ' + APP_NAME() + '. The date is ' + CONVERT ( varchar(100) , GETDATE(), 102) + '.';  
GO  
```  
  
## <a name="see-also"></a>Voir aussi
[Fonctions système &#40; Transact-SQL &#41;](../../relational-databases/system-functions/system-functions-for-transact-sql.md)  
[Fonctions](../../t-sql/functions/functions.md)
  
  

