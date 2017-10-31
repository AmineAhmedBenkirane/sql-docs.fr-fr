---
title: ERROR_MESSAGE (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ERROR_MESSAGE_TSQL
- ERROR_MESSAGE
dev_langs:
- TSQL
helpviewer_keywords:
- ERROR_MESSAGE function
- errors [SQL Server], text of
- messages [SQL Server], text of
- TRY...CATCH [SQL Server]
- CATCH block
ms.assetid: f32877a6-5f17-418c-a32c-5a1a344b3c45
caps.latest.revision: 53
author: edmacauley
ms.author: edmaca
manager: cguyer
ms.workload: Active
ms.translationtype: MT
ms.sourcegitcommit: 77c7eb1fcde9b073b3c08f412ac0e46519763c74
ms.openlocfilehash: ad4e69ea267af2a9575558737e17e79bbdad684f
ms.contentlocale: fr-fr
ms.lasthandoff: 10/17/2017

---
# <a name="errormessage-transact-sql"></a>ERROR_MESSAGE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Retourne le texte du message de l'erreur qui a provoqué l'exécution du bloc CATCH d'une construction TRY…CATCH.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
ERROR_MESSAGE ( )   
```  
  
## <a name="return-types"></a>Types de retour  
 **nvarchar(4000)**  
  
## <a name="return-value"></a>Valeur retournée  
 Appelé dans un bloc CATCH, retourne le texte complet du message d'erreur qui a provoqué l'exécution du bloc CATCH. Le texte comprend les valeurs fournies pour tous les paramètres remplaçables, tels que les longueurs, les noms d'objet ou les heures.  
  
 Retourne NULL si l'appel a lieu en dehors de l'étendue d'un bloc CATCH.  
  
## <a name="remarks"></a>Notes  
 ERROR_MESSAGE peut être appelé partout dans l'étendue d'un bloc CATCH.  
  
 ERROR_MESSAGE retourne le message d'erreur indépendamment du nombre de fois ou de l'emplacement où il est exécuté dans l'étendue du bloc CATCH. Cela diffère des fonctions telles que @@ERROR, qui retourne uniquement un numéro d’erreur dans l’instruction immédiatement après celle qui provoque une erreur ou la première instruction d’un bloc CATCH bloquer.  
  
 Dans les blocs CATCH imbriqués, ERROR_MESSAGE retourne le message d'erreur spécifique à l'étendue du bloc CATCH dans lequel il est référencé. Par exemple, le bloc CATCH d'une construction TRY...CATCH externe peut comporter une construction TRY...CATCH imbriquée. Dans le bloc CATCH imbriqué, ERROR_MESSAGE retourne le message de l'erreur qui a appelé le bloc CATCH imbriqué. Si ERROR_MESSAGE est exécuté dans le bloc CATCH externe, il retourne le message de l'erreur qui a appelé ce bloc CATCH.  
  
## <a name="examples"></a>Exemples  
  
### <a name="a-using-errormessage-in-a-catch-block"></a>A. Utilisation de ERROR_MESSAGE dans un bloc CATCH  
 L'exemple de code suivant montre une instruction `SELECT` qui génère une erreur de division par zéro. Le message de l'erreur est retourné.  
  
```  
  
BEGIN TRY  
    -- Generate a divide-by-zero error.  
    SELECT 1/0;  
END TRY  
BEGIN CATCH  
    SELECT ERROR_MESSAGE() AS ErrorMessage;  
END CATCH;  
GO  
```  
  
### <a name="b-using-errormessage-in-a-catch-block-with-other-error-handling-tools"></a>B. Utilisation de ERROR_MESSAGE dans un bloc CATCH avec d'autres outils de traitement des erreurs  
 L'exemple de code suivant montre une instruction `SELECT` qui génère une erreur de division par zéro. Des informations relatives à l'erreur sont retournées en même temps que le message d'erreur.  
  
```  
  
BEGIN TRY  
    -- Generate a divide-by-zero error.  
    SELECT 1/0;  
END TRY  
BEGIN CATCH  
    SELECT  
        ERROR_NUMBER() AS ErrorNumber  
        ,ERROR_SEVERITY() AS ErrorSeverity  
        ,ERROR_STATE() AS ErrorState  
        ,ERROR_PROCEDURE() AS ErrorProcedure  
        ,ERROR_LINE() AS ErrorLine  
        ,ERROR_MESSAGE() AS ErrorMessage;  
END CATCH;  
GO  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Exemples : [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] et[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="c-using-errormessage-in-a-catch-block-with-other-error-handling-tools"></a>C. Utilisation de ERROR_MESSAGE dans un bloc CATCH avec d'autres outils de traitement des erreurs  
 L'exemple de code suivant montre une instruction `SELECT` qui génère une erreur de division par zéro. Des informations relatives à l'erreur sont retournées en même temps que le message d'erreur.  
  
```  
  
BEGIN TRY  
    -- Generate a divide-by-zero error.  
    SELECT 1/0;  
END TRY  
BEGIN CATCH  
    SELECT  
        ERROR_NUMBER() AS ErrorNumber  
        ,ERROR_SEVERITY() AS ErrorSeverity  
        ,ERROR_STATE() AS ErrorState  
        ,ERROR_PROCEDURE() AS ErrorProcedure  
        ,ERROR_MESSAGE() AS ErrorMessage;  
END CATCH;  
GO  
```  
  


