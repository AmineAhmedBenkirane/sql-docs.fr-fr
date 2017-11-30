---
title: xp_logevent (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- xp_logevent
- xp_logevent_TSQL
dev_langs: TSQL
helpviewer_keywords: xp_logevent
ms.assetid: 7b379ad0-5b12-4d2e-9c52-62465df1fdbd
caps.latest.revision: "30"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 9ac262c1d16baf15eb9f1eafd05960f8d1905ec9
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/27/2017
---
# <a name="xplogevent-transact-sql"></a>xp_logevent (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Enregistre un message défini par l’utilisateur dans le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fichier journal dans l’Observateur d’événements Windows. xp_logevent peut être utilisé pour envoyer une alerte sans envoyer de message au client.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
xp_logevent { error_number , 'message' } [ , 'severity' ]  
```  
  
## <a name="arguments"></a>Arguments  
 *error_number*  
 Numéro d'erreur défini par l'utilisateur, supérieur à 50000. La valeur maximale est 2147483647 (2^31 - 1).  
  
 **'** *message* **'**  
 Chaîne de caractères d'une longueur maximale de 2048 caractères.  
  
 **'** *gravité* **'**  
 Une des trois chaînes de caractères INFORMATIONAL, WARNING ou ERROR. *gravité* est facultatif, avec INFORMATIONAL comme valeur par défaut.  
  
## <a name="return-code-values"></a>Valeurs des codes de retour  
 0 (réussite) ou 1 (échec)  
  
## <a name="result-sets"></a>Jeux de résultats  
 xp_logevent retourne ce message d'erreur pour l'exemple de code ci-dessous :  
  
 `The command(s) completed successfully.`  
  
## <a name="remarks"></a>Notes  
 Lorsque vous envoyez des messages à partir de [!INCLUDE[tsql](../../includes/tsql-md.md)] procédures, déclencheurs, lots et ainsi de suite, utilisent l’instruction RAISERROR au lieu de xp_logevent. xp_logevent ne pas appeler un gestionnaire de messages d’un client ou@ERROR. Pour écrire des messages dans l'Observateur d'événements Windows et dans le journal des erreurs de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans une instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], exécutez l'instruction RAISERROR.  
  
## <a name="permissions"></a>Permissions  
 Il faut appartenir au rôle de base de données fixe db_owner de la base de données master ou au rôle serveur fixe sysadmin.  
  
## <a name="examples"></a>Exemples  
 Cet exemple enregistre le message dans l'Observateur d'événements Windows et transmet les variables au message.  
  
```  
DECLARE @@TABNAME varchar(30, @@USERNAME varchar(30),DECLARE @@MESSAGE varchar(255);  
SET @@TABNAME = 'customers';  
SET @@USERNAME = USER_NAME();  
SELECT @@MESSAGE = 'The table ' + @@TABNAME + ' is not owned by the user   
   ' + @@USERNAME + '.';  
  
USE master;  
EXEC xp_logevent 60000, @@MESSAGE, informational;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [PRINT &#40;Transact-SQL&#41;](../../t-sql/language-elements/print-transact-sql.md)   
 [RAISERROR &#40;Transact-SQL&#41;](../../t-sql/language-elements/raiserror-transact-sql.md)   
 [Procédures stockées système &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [Étendues générales des procédures stockées &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/general-extended-stored-procedures-transact-sql.md)  
  
  
