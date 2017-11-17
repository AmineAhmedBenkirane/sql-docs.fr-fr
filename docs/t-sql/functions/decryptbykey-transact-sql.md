---
title: DECRYPTBYKEY (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/06/2017
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
- DecryptByKey_TSQL
- DECRYPTBYKEY
dev_langs:
- TSQL
helpviewer_keywords:
- symmetric keys [SQL Server], DecryptByKey function
- decryption [SQL Server], keys
- decryption [SQL Server], symmetric keys
- DECRYPTBYKEY function
ms.assetid: 6edf121f-ac62-4dae-90e6-6938f32603c9
caps.latest.revision: 39
author: edmacauley
ms.author: edmaca
manager: cguyer
ms.workload: On Demand
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 0debd61d7a6c43c076f2e868379e85db65e90ab1
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="decryptbykey-transact-sql"></a>DECRYPTBYKEY (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Déchiffre des données à l'aide d'une clé symétrique.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
DecryptByKey ( { 'ciphertext' | @ciphertext }   
    [ , add_authenticator, { authenticator | @authenticator } ] )  
```  
  
## <a name="arguments"></a>Arguments  
 *texte chiffré*  
 Données chiffrées avec la clé. *texte chiffré* est **varbinary**.  
  
 **@ciphertext**  
 Est une variable de type **varbinary** qui contient les données qui ont été chiffrées avec la clé.  
  
 *add_authenticator*  
 Indique si un authentificateur a été chiffré en même temps que le texte en clair. Doit avoir la même valeur que celle passée à EncryptByKey lors du chiffrement des données. *add_authenticator* est **int**.  
  
 *authentificateur*  
 Données à partir desquelles produire un authentificateur. Doit correspondre à la valeur qui a été fournie à EncryptByKey. *l’authentificateur* est **sysname**.  
  
 **@authenticator**  
 Variable contenant les données à partir desquelles l'authentificateur sera généré. Doit correspondre à la valeur qui a été fournie à EncryptByKey.  
  
## <a name="return-types"></a>Types de retour  
 **varbinary** avec une taille maximale de 8 000 octets.  
  
## <a name="remarks"></a>Notes  
 DecryptByKey utilise une clé symétrique. Cette clé symétrique doit déjà être ouverte dans la base de données. Plusieurs clés peuvent être ouvertes en même temps. Vous n'avez pas besoin d'ouvrir la clé tout de suite avant de déchiffrer le texte chiffré.  
  
 Le chiffrement et le déchiffrement symétriques sont relativement rapides et adaptés à la manipulation de grandes quantités de données.  
  
## <a name="permissions"></a>Permissions  
 Requiert l'ouverture de la clé symétrique dans la session en cours. Pour plus d’informations, consultez [OPEN SYMMETRIC KEY &#40; Transact-SQL &#41; ](../../t-sql/statements/open-symmetric-key-transact-sql.md).  
  
## <a name="examples"></a>Exemples  
  
### <a name="a-decrypting-by-using-a-symmetric-key"></a>A. Déchiffrement à l'aide d'une clé symétrique  
 L'exemple suivant déchiffre du texte chiffré à l'aide d'une clé symétrique.  
  
```  
-- First, open the symmetric key with which to decrypt the data.  
OPEN SYMMETRIC KEY SSN_Key_01  
   DECRYPTION BY CERTIFICATE HumanResources037;  
GO  
  
-- Now list the original ID, the encrypted ID, and the   
-- decrypted ciphertext. If the decryption worked, the original  
-- and the decrypted ID will match.  
SELECT NationalIDNumber, EncryptedNationalID   
    AS 'Encrypted ID Number',  
    CONVERT(nvarchar, DecryptByKey(EncryptedNationalID))   
    AS 'Decrypted ID Number'  
    FROM HumanResources.Employee;  
GO  
```  
  
### <a name="b-decrypting-by-using-a-symmetric-key-and-an-authenticating-hash"></a>B. Déchiffrement à l'aide d'une clé symétrique et d'un hachage d'authentification  
 L'exemple suivant déchiffre des données qui ont été chiffrées à l'aide d'un authentificateur.  
  
```  
-- First, open the symmetric key with which to decrypt the data  
OPEN SYMMETRIC KEY CreditCards_Key11  
   DECRYPTION BY CERTIFICATE Sales09;  
GO  
  
-- Now list the original card number, the encrypted card number,  
-- and the decrypted ciphertext. If the decryption worked,   
-- the original number will match the decrypted number.  
SELECT CardNumber, CardNumber_Encrypted   
    AS 'Encrypted card number', CONVERT(nvarchar,  
    DecryptByKey(CardNumber_Encrypted, 1 ,   
    HashBytes('SHA1', CONVERT(varbinary, CreditCardID))))   
    AS 'Decrypted card number' FROM Sales.CreditCard;  
GO  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [ENCRYPTBYKEY &#40; Transact-SQL &#41;](../../t-sql/functions/encryptbykey-transact-sql.md)   
 [CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;](../../t-sql/statements/create-symmetric-key-transact-sql.md)   
 [ALTER SYMMETRIC KEY &#40;Transact-SQL&#41;](../../t-sql/statements/alter-symmetric-key-transact-sql.md)   
 [DROP SYMMETRIC KEY &#40;Transact-SQL&#41;](../../t-sql/statements/drop-symmetric-key-transact-sql.md)   
 [Hiérarchie de chiffrement](../../relational-databases/security/encryption/encryption-hierarchy.md)   
 [Choisir un algorithme de chiffrement](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md)  
  
  

