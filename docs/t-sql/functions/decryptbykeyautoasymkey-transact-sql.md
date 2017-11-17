---
title: DECRYPTBYKEYAUTOASYMKEY (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 09/09/2015
ms.prod: sql-non-specified
ms.prod_service: sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DECRYPTBYKEYAUTOASYMKEY_TSQL
- DECRYPTBYKEYAUTOASYMKEY
dev_langs:
- TSQL
helpviewer_keywords:
- DECRYPTBYKEYAUTOASYMSKEY function
ms.assetid: 5521d4cf-740c-4ede-98b6-4ba90b84e32d
caps.latest.revision: 23
author: edmacauley
ms.author: edmaca
manager: cguyer
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 74aa8bad7e6d848296ef2997017758883226ac48
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="decryptbykeyautoasymkey-transact-sql"></a>DECRYPTBYKEYAUTOASYMKEY (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Déchiffre à l'aide d'une clé symétrique automatiquement déchiffrée à l'aide d'une clé asymétrique.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
DecryptByKeyAutoAsymKey ( akey_ID , akey_password   
    , { 'ciphertext' | @ciphertext }  
  [ , { add_authenticator | @add_authenticator }   
  [ , { authenticator | @authenticator } ] ] )  
```  
  
## <a name="arguments"></a>Arguments  
 *akey_ID*  
 ID de la clé asymétrique servant à protéger la clé symétrique. *akey_ID* est **int**.  
  
 *akey_password*  
 Mot de passe qui protège la clé privée de la clé asymétrique. Peut être NULL si la clé privée est protégée par la clé principale de la base de données. *akey_password* est **nvarchar**.  
  
 '*texte chiffré*'  
 Données chiffrées avec la clé. *texte chiffré* est **varbinary**.  
  
 @ciphertext  
 Est une variable de type **varbinary** qui contient les données chiffrées avec la clé.  
  
 *add_authenticator*  
 Indique si un authentificateur a été chiffré en même temps que le texte en clair. Il doit s'agir de la valeur transmise à EncryptByKey lors du chiffrement des données. La valeur est 1 si un authentificateur a été utilisé. *add_authenticator* est **int**.  
  
 @add_authenticator  
 Indique si un authentificateur a été chiffré en même temps que le texte en clair. Il doit s'agir de la valeur transmise à EncryptByKey lors du chiffrement des données.  
  
 *authentificateur*  
 Données à partir desquelles un authentificateur peut être généré. Doit correspondre à la valeur qui a été fournie à EncryptByKey. *l’authentificateur* est **sysname**.  
  
 @authenticator  
 Variable contenant les données à partir desquelles l'authentificateur sera généré. Doit correspondre à la valeur qui a été fournie à EncryptByKey.  
  
## <a name="return-types"></a>Types de retour  
 **varbinary** avec une taille maximale de 8 000 octets.  
  
## <a name="remarks"></a>Notes  
 DecryptByKeyAutoAsymKey combine les fonctionnalités de OPEN SYMMETRIC KEY et de DecryptByKey. Dans une seule opération, il déchiffre une clé symétrique et utilise cette clé pour déchiffrer le texte chiffré.  
  
## <a name="permissions"></a>Permissions  
 Requiert l'autorisation VIEW DEFINITION sur la clé symétrique et CONTROL sur la clé asymétrique.  
  
## <a name="examples"></a>Exemples  
 L'exemple suivant montre comment utiliser `DecryptByKeyAutoAsymKey` pour simplifier le code qui effectue le déchiffrement. Ce code doit être exécuté sur une base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] qui n'a pas encore de clé principale de base de données.  
  
```  
--Create the keys and certificate.  
USE AdventureWorks2012;  
CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'mzkvdMlk979438teag$$ds987yghn)(*&4fdg^';  
OPEN MASTER KEY DECRYPTION BY PASSWORD = 'mzkvdMlk979438teag$$ds987yghn)(*&4fdg^';  
CREATE ASYMMETRIC KEY SSN_AKey   
    WITH ALGORITHM = RSA_2048 ;   
GO  
CREATE SYMMETRIC KEY SSN_Key_02 WITH ALGORITHM = DES  
    ENCRYPTION BY ASYMMETRIC KEY SSN_AKey;  
GO  
--  
--Add a column of encrypted data.  
ALTER TABLE HumanResources.Employee  
    ADD EncryptedNationalIDNumber2 varbinary(128);   
OPEN SYMMETRIC KEY SSN_Key_02  
   DECRYPTION BY ASYMMETRIC KEY SSN_AKey;  
UPDATE HumanResources.Employee  
SET EncryptedNationalIDNumber2  
    = EncryptByKey(Key_GUID('SSN_Key_02'), NationalIDNumber);  
GO  
--Close the key used to encrypt the data.  
CLOSE SYMMETRIC KEY SSN_Key_02;  
--  
--There are two ways to decrypt the stored data.  
--  
--OPTION ONE, using DecryptByKey()  
--1. Open the symmetric key.  
--2. Decrypt the data.  
--3. Close the symmetric key.  
OPEN SYMMETRIC KEY SSN_Key_02  
   DECRYPTION BY ASYMMETRIC KEY SSN_AKey;  
SELECT NationalIDNumber, EncryptedNationalIDNumber2    
    AS 'Encrypted ID Number',  
    CONVERT(nvarchar, DecryptByKey(EncryptedNationalIDNumber2))   
    AS 'Decrypted ID Number'  
    FROM HumanResources.Employee;  
CLOSE SYMMETRIC KEY SSN_Key_02;  
--  
--OPTION TWO, using DecryptByKeyAutoAsymKey()  
SELECT NationalIDNumber, EncryptedNationalIDNumber2   
    AS 'Encrypted ID Number',  
    CONVERT(nvarchar, DecryptByKeyAutoAsymKey ( AsymKey_ID('SSN_AKey') , NULL ,EncryptedNationalIDNumber2))   
    AS 'Decrypted ID Number'  
    FROM HumanResources.Employee;  
GO  
```  
  
## <a name="see-also"></a>Voir aussi  
 [OPEN SYMMETRIC KEY &#40;Transact-SQL&#41;](../../t-sql/statements/open-symmetric-key-transact-sql.md)   
 [ENCRYPTBYKEY &#40; Transact-SQL &#41;](../../t-sql/functions/encryptbykey-transact-sql.md)   
 [DECRYPTBYKEY &#40; Transact-SQL &#41;](../../t-sql/functions/decryptbykey-transact-sql.md)   
 [Hiérarchie de chiffrement](../../relational-databases/security/encryption/encryption-hierarchy.md)  
  
  

