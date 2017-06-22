---
title: "Résoudre des problèmes courants JSON dans SQL Server | Microsoft Docs"
ms.custom:
- SQL2016_New_Updated
ms.date: 07/07/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-json
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JSON, FAQ
ms.assetid: feae120b-55cc-4601-a811-278ef1c551f9
caps.latest.revision: 9
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 439b568fb268cdc6e6a817f36ce38aeaeac11fab
ms.openlocfilehash: 94435e9fb466887a00c8d22076f229481a83f280
ms.contentlocale: fr-fr
ms.lasthandoff: 06/22/2017

---
# <a name="solve-common-issues-with-json-in-sql-server"></a>Résoudre des problèmes courants JSON dans SQL Server
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

 Vous pouvez trouver ici des réponses aux questions courantes sur la prise en charge de JSON intégrée à SQL Server.  
 
## <a name="for-json-and-json-output"></a>Sortie FOR JSON et JSON

### <a name="for-json-path-or-for-json-auto"></a>FOR JSON PATH ou FOR JSON AUTO ?  
 **Question.** Je souhaite créer un résultat de texte JSON à partir d’une simple requête SQL sur une seule table. FOR JSON PATH et FOR JSON AUTO produisent le même résultat. Quelle option dois-je utiliser ?  
  
 **Réponse.** Utilisez FOR JSON PATH. Bien qu’il n’existe aucune différence dans la sortie JSON, le mode AUTO applique une logique supplémentaire qui vérifie si les colonnes doivent être imbriquées. Considérez PATH comme l’option par défaut.  

### <a name="create-a-nested-json-structure"></a>Créer une structure JSON imbriquée  
 **Question.** Je souhaite produire un JSON complexe avec plusieurs tableaux au même niveau. FOR JSON PATH peut créer des objets imbriqués à l’aide de chemins d’accès, et FOR JSON AUTO crée un niveau d’imbrication supplémentaire pour chaque table. Ni un de ces deux options me permet de générer la sortie souhaitée. Comment puis-je créer un format JSON personnalisé que les options existantes ne prennent pas directement en charge ?  
  
 **Réponse.** Vous pouvez créer une structure de données en ajoutant des requêtes FOR JSON en tant qu’expressions de colonne qui retournent du texte JSON. Vous pouvez également créer un JSON manuellement à l’aide de la fonction JSON_QUERY. Le l’exemple suivant illustre ces techniques.  
  
```sql  
SELECT col1, col2, col3,  
     (SELECT col11, col12, col13 FROM t11 WHERE t11.FK = t1.PK FOR JSON PATH) as t11,  
     (SELECT col21, col22, col23 FROM t21 WHERE t21.FK = t1.PK FOR JSON PATH) as t21,  
     (SELECT col31, col32, col33 FROM t31 WHERE t31.FK = t1.PK FOR JSON PATH) as t31,  
     JSON_QUERY('{"'+col4'":"'+col5+'"}' as t41  
FROM t1  
FOR JSON PATH  
```  
  
Chaque résultat d’une requête FOR JSON ou de la fonction JSON_QUERY dans des expressions de colonne est mis en forme comme un sous-objet JSON imbriqué distinct et inclus dans le résultat principal.  

### <a name="prevent-double-escaped-json-in-for-json-output"></a>Empêcher une double séquence d’échappement JSON dans une sortie FOR JSON  
 **Question.** J’ai du texte JSON stocké dans une colonne de table. Je souhaite l’inclure dans la sortie de FOR JSON. Mais FOR JSON échappe tous les caractères dans le JSON, afin d’obtenir une chaîne JSON au lieu d’un objet imbriqué, comme indiqué dans l’exemple suivant.  
  
```sql  
SELECT 'Text' AS myText, '{"day":23}' AS myJson  
FOR JSON PATH  
```  
  
 Cette requête produit la sortie suivante :  
  
```json  
[{"myText":"Text", "myJson":"{\"day\":23}"}]  
```  
  
 Comment éviter cela ? Je veux que `{"day":23}` soit retourné en tant qu’objet JSON, pas comme du texte dans une séquence d’échappement.  
  
 **Réponse.** Un objet JSON stocké dans une colonne de texte ou un littéral est traité comme n’importe quel texte. Autrement dit, il a entouré de doubles guillemets et séquence d’échappement. Si vous voulez retourner un objet JSON sans séquence d’échappement, passer la colonne JSON en tant qu’argument à la fonction JSON_QUERY, comme illustré dans l’exemple suivant.  
  
```sql  
SELECT col1, col2, col3, JSON_QUERY(jsoncol1) AS jsoncol1  
FROM tab1  
FOR JSON PATH  
```  
  
 JSON_QUERY sans son deuxième paramètre facultatif retourne uniquement le premier argument comme résultat. Étant donné que JSON_QUERY retourne toujours un JSON valide, FOR JSON sait que ce résultat ne doit pas être échappé.

### <a name="json-generated-with-the-withoutarraywrapper-clause-is-escaped-in-for-json-output"></a>Un JSON généré avec la clause WITHOUT_ARRAY_WRAPPER est placé dans une séquence d’échappement dans la sortie JSON  
 **Question.** J’essaie de mettre en forme une expression de colonne à l’aide de FOR JSON et de l’option WITHOUT_ARRAY_WRAPPER.  
  
```sql  
SELECT 'Text' as myText,  
   (SELECT 12 day, 8 mon FOR JSON PATH, WITHOUT_ARRAY_WRAPPER) as myJson  
FOR JSON PATH   
```  
  
 Il semble que le texte retourné par la requête FOR JSON soit placé dans une séquence d’échappement en tant que texte brut. Cela se produit uniquement si WITHOUT_ARRAY_WRAPPER est spécifié. Pourquoi ce texte n’est-il pas considéré comme un objet JSON et inclus sans séquence d’échappement dans le résultat ?  
  
 **Réponse.** Si vous spécifiez la `WITHOUT_ARRAY_WRAPPER` option interne `FOR JSON`, le texte JSON qui en résulte n’est pas nécessairement valide JSON. Par conséquent externe `FOR JSON` suppose qu’il est en texte brut et la chaîne d’échappement. Si vous êtes sûr que le fichier JSON de sortie n’est valide, retour à la ligne avec la `JSON_QUERY` afin de le promouvoir pour correctement au format JSON, comme indiqué dans l’exemple suivant.  
  
```sql  
SELECT 'Text' as myText,  
      JSON_QUERY((SELECT 12 day, 8 mon FOR JSON PATH, WITHOUT_ARRAY_WRAPPER)) as myJson  
FOR JSON PATH    
```  

## <a name="openjson-and-json-input"></a>Entrée OPENJSON et JSON

### <a name="return-a-nested-json-sub-object-from-json-text-with-openjson"></a>Retourner un sous-objet JSON imbriqué à partir d’un texte JSON avec OPENJSON  
 **Question.** Impossible d’ouvrir un tableau d’objets JSON complexes qui contient les deux valeurs scalaires, des objets et des tableaux en utilisant OPENJSON avec un schéma explicite. Si référence une clé dans la clause WITH, seules les valeurs scalaires sont retournées. Les objets et tableaux sont retournés en tant que valeurs Null. Comment puis-je extraire des objets ou des tableaux en tant qu’objets JSON ?  
  
 **Réponse.** Si vous voulez retourner un objet ou un tableau en tant que colonne, utilisez l’option AS JSON dans la définition de colonne, comme indiqué dans l’exemple suivant.  
  
```sql  
SELECT scalar1, scalar2, obj1, obj2, arr1  
FROM OPENJSON(@json)  
    WITH ( scalar1 int,  
        scalar2 datetime2,  
        obj1 NVARCHAR(MAX) AS JSON,  
        obj2 NVARCHAR(MAX) AS JSON,  
        arr1 NVARCHAR(MAX) AS JSON)  
```  

### <a name="return-long-text-value-with-openjson-instead-of-jsonvalue"></a>Valeur de texte long avec OPENJSON au lieu de JSON_VALUE de retour
 **Question.** J’ai une clé description dans un texte JSON qui contient du texte long. `JSON_VALUE(@json, '$.description')` retourne la valeur NULL au lieu d’une valeur.  
  
 **Réponse.** JSON_VALUE est conçue pour retourner des valeurs scalaires courtes. En règle générale, la fonction retourne NULL au lieu d’une erreur de dépassement. Si vous voulez retourner des valeurs plus longues, utilisez OPENJSON, qui prend en charge les valeurs de NVARCHAR (MAX), comme dans l’exemple suivant.  
  
```sql  
SELECT myText FROM OPENJSON(@json) WITH (myText NVARCHAR(MAX) '$.description')  
```  

### <a name="handle-duplicate-keys-with-openjson-instead-of-jsonvalue"></a>Gérer des clés en double avec OPENJSON au lieu de JSON_VALUE
 **Question.** J’ai des clés en double dans le texte JSON. JSON_VALUE retourne uniquement la première clé trouvée dans le chemin d’accès. Comment puis-je retrouver toutes les clés portant le même nom ?  
  
 **Réponse.** Les fonctions scalaires JSON intégrées retournent uniquement la première occurrence de l’objet référencé. Si vous avez besoin de plus d’une clé, utilisez la fonction table incluse OPENJSON, comme dans l’exemple suivant.  
  
```sql  
SELECT value FROM OPENJSON(@json, '$.info.settings')  
WHERE [key] = 'color'  
```  

### <a name="openjson-requires-compatibility-level-130"></a>OPENJSON requiert le niveau de compatibilité 130  
 **Question.** J’essaie d’exécuter OPENJSON dans SQL Server 2016, et j’obtiens l’erreur suivante.  
  
 `Msg 208, Level 16, State 1 ‘Invalid object name OPENJSON’`  
  
 **Réponse.** La fonction OPENJSON est disponible uniquement sous le niveau de compatibilité 130. Si votre base de données est associée à un niveau de compatibilité inférieure à 130, OPENJSON est masqué. Les autres fonctions JSON sont disponibles à tous les niveaux de compatibilité.  
 
## <a name="other-questions"></a>Autres questions

### <a name="reference-keys-that-contain-non-alphanumeric-characters-in-json-text"></a>Clés de référence contenant des caractères non alphanumériques dans du texte JSON  
 **Question.** J’ai des clés contenant des caractères non alphanumériques dans mon texte JSON. Comment puis-je référencer ces propriétés ?  
  
 **Réponse.** Vous devez les mettre entre guillemets dans les chemins d’accès JSON. Par exemple, `JSON_VALUE(@json, '$."$info"."First Name".value')`.
 
## <a name="learn-more-about-the-built-in-json-support-in-sql-server"></a>En savoir plus sur la fonction intégrée prise en charge de JSON dans SQL Server  
Pour un grand nombre de solutions spécifiques, utilisez des cas et des recommandations, consultez le [billets de blog sur la prise en charge intégrée de JSON](http://blogs.msdn.com/b/sqlserverstorageengine/archive/tags/json/) dans SQL Server et dans la base de données SQL Azure par programme Jovan Popovic Gestionnaire Microsoft.

