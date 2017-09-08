---
title: '@@REMSERVER (Transact-SQL) | Documents Microsoft'
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '@@REMSERVER'
- '@@REMSERVER_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- logins [SQL Server], remote servers
- remote servers [SQL Server], logins
- '@@REMSERVER function'
ms.assetid: 0bb451a9-3866-4064-963d-b74a2f864049
caps.latest.revision: 23
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 23ae1a37bcc84561a0ccedf10b1bb0c6ee7b6b73
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="remserver-transact-sql"></a>@@REMSERVER (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextDontUse](../../includes/ssnotedepnextdontuse-md.md)] Utilisez des serveurs liés et des procédures stockées de serveur lié à la place.  
  
 Retourne le nom du serveur de base de données distant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tel qu'il apparaît dans l'enregistrement de connexion.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
@@REMSERVER  
```  
  
## <a name="return-types"></a>Types de retour  
 **nvarchar (128)**  
  
## <a name="remarks"></a>Notes  
 @@REMSERVER permet à une procédure stockée vérifier le nom du serveur de base de données à partir de laquelle la procédure est exécutée.  
  
## <a name="examples"></a>Exemples  
 Cet exemple crée la procédure `usp_CheckServer` qui retourne le nom du serveur distant.  
  
```  
CREATE PROCEDURE usp_CheckServer  
AS  
SELECT @@REMSERVER;  
```  
  
 La procédure stockée suivante est créée sur `SEATTLE1`, le serveur local. L'utilisateur se connecte à un serveur distant, `LONDON2`, et exécute `usp_CheckServer`.  
  
```  
EXEC SEATTLE1...usp_CheckServer;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
---------------  
LONDON2  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions de configuration &#40;Transact-SQL&#41;](../../t-sql/functions/configuration-functions-transact-sql.md)   
 [Serveurs distants](../../database-engine/configure-windows/remote-servers.md)  
  
  
