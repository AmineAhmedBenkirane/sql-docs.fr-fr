---
title: APPLOCK_TEST (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 07/24/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- APPLOCK_TEST_TSQL
- APPLOCK_TEST
dev_langs:
- TSQL
helpviewer_keywords:
- locking [SQL Server], applications
- APPLOCK_TEST function
- applications [SQL Server], locks
- sessions [SQL Server], application locks
- testing application locks
ms.assetid: 4ea33d04-f8e9-46ff-ae61-985bd3eaca2c
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: f4009a151873bf989a39bc4fb91ec3a9963af9f2
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="applocktest-transact-sql"></a>APPLOCK_TEST (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Renvoie des informations indiquant si un verrou peut ou non être octroyé sur une ressource d'application à un propriétaire de verrou donné, sans qu'il y ait acquisition du verrou. APPLOCK_TEST est une fonction de verrouillage d'application qui agit sur la base de données active. L'étendue des verrous d'application est la base de données.
  
![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntaxe  
  
```sql
APPLOCK_TEST ( 'database_principal' , 'resource_name' , 'lock_mode' , 'lock_owner' )  
```  
  
## <a name="arguments"></a>Arguments  
**'** *principal_base_de_données* **'**  
Utilisateur, rôle ou rôle d'application qui peut se voir octroyer des autorisations sur des objets dans la base de données. L’appelant de la fonction doit être un membre du *principal_base_de_données*, **dbo**, ou **db_owner** rôle de base de données fixe afin d’appeler la fonction.
  
**'** *nom_ressource* **'**  
Nom de ressource de verrou spécifié par l'application cliente. L'application doit veiller à ce que la ressource soit unique. Le nom spécifié est haché en interne en une valeur qui peut être stockée dans le gestionnaire de verrous [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. *resource_name*est **nvarchar (255)** sans valeur par défaut. *resource_name* comparaison binaire et respecte la casse, indépendamment des paramètres de classement de la base de données actuelle.
  
**'** *argument lock_mode* **'**  
Mode de verrouillage à obtenir pour une ressource spécifique. *l’argument Lock_Mode* est **nvarchar(32)** et n’a aucune valeur par défaut. La valeur peut être une des opérations suivantes : **Shared**, **mise à jour**, **IntentShared**, **IntentExclusive**, **exclusif**.
  
**'** *lock_owner* **'**  
Est le propriétaire du verrou, qui est la *lock_owner* valeur lorsque le verrou a été demandé. *lock_owner* est **nvarchar(32)**. La valeur peut être **Transaction** (la valeur par défaut) ou **Session**. Si par défaut ou **Transaction** est explicitement spécifiée, APPLOCK_TEST doit être exécutée à partir d’une transaction.
  
## <a name="return-types"></a>Types de retour
**smallint**
  
## <a name="return-value"></a>Valeur retournée
Renvoie la valeur 0 lorsque le verrou ne peut pas être octroyé au propriétaire spécifié et renvoie la valeur 1 si le verrou peut être attribué.
  
## <a name="function-properties"></a>Propriétés de la fonction
**Non déterministes**
  
**Non indexable**
  
**Non Parallélisable**
  
## <a name="examples"></a>Exemples  
Dans l’exemple suivant, deux utilisateurs (**l’utilisateur A** et **utilisateur B**) dans des sessions différentes exécute la séquence suivante de [!INCLUDE[tsql](../../includes/tsql-md.md)] instructions.
  
**L’utilisateur A** s’exécute :
  
```sql
USE AdventureWorks2012;  
GO  
BEGIN TRAN;  
DECLARE @result int;  
EXEC @result=sp_getapplock  
    @DbPrincipal='public',  
    @Resource='Form1',  
    @LockMode='Shared',  
    @LockOwner='Transaction';  
SELECT APPLOCK_MODE('public', 'Form1', 'Transaction');  
GO  
```  
  
**L’utilisateur B** exécute ensuite :
  
```sql
Use AdventureWorks2012;  
GO  
BEGIN TRAN;  
SELECT APPLOCK_MODE('public', 'Form1', 'Transaction');  
--Result set: NoLock  
  
SELECT APPLOCK_TEST('public', 'Form1', 'Shared', 'Transaction');  
--Result set: 1 (Lock is grantable.)  
  
SELECT APPLOCK_TEST('public', 'Form1', 'Exclusive', 'Transaction');  
--Result set: 0 (Lock is not grantable.)  
GO  
```  
  
**L’utilisateur A** exécute ensuite :
  
```sql
EXEC sp_releaseapplock @Resource='Form1', @DbPrincipal='public';  
GO  
```  
  
**L’utilisateur B** exécute ensuite :
  
```sql
SELECT APPLOCK_TEST('public', 'Form1', 'Exclusive', 'Transaction');  
--Result set: '1' (The lock is grantable.)  
GO  
```  
  
**L’utilisateur A** et **utilisateur B** puis s’exécutent tous deux :
  
```sql
COMMIT TRAN;  
GO  
```  
  
## <a name="see-also"></a>Voir aussi
[APPLOCK_MODE &#40; Transact-SQL &#41;](../../t-sql/functions/applock-mode-transact-sql.md)  
[sp_getapplock &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-getapplock-transact-sql.md)  
[sp_releaseapplock &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-releaseapplock-transact-sql.md)
  
  
