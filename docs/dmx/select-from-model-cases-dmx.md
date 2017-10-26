---
title: "SELECT FROM &lt;modèle&gt;. CAS (DMX) | Documents Microsoft"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SELECT
- CASES
- FROM
dev_langs:
- DMX
helpviewer_keywords:
- SELECT FROM <model>.CASES statement
- drillthrough [DMX]
ms.assetid: d58acb47-aaa6-40b7-b8c4-6a6700fbc1dd
caps.latest.revision: 55
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 7f5ec287b2da5998748c19a5000a0a95b658f853
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="select-from-ltmodelgtcases-dmx"></a>SELECT FROM &lt;modèle&gt;. CAS (DMX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Prend en charge l'extraction et retourne les cas qui ont été utilisés pour l'apprentissage du modèle. Vous pouvez également retourner des colonnes de structure qui ne sont pas incluses dans le modèle si l'extraction a été activée sur la structure d'exploration de données et sur le modèle d'exploration de données et que vous disposez des autorisations appropriées.  
  
 Si l'extraction n'est pas activée sur le modèle d'exploration de données, cette instruction échoue.  
  
> [!NOTE]  
>  En DMX (Data Mining Extensions), vous ne pouvez activer l'extraction que lors de la création du modèle. Vous pouvez ajouter l'extraction à un modèle existant à l'aide de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], mais le modèle doit être retraité avant que vous ne puissiez afficher ou interroger les cas.  
  
 Pour plus d’informations sur la façon d’activer l’extraction, consultez [créer un modèle d’exploration de données &#40; DMX &#41;](../dmx/create-mining-model-dmx.md), [SELECT INTO &#40; DMX &#41;](../dmx/select-into-dmx.md), et [modifier la STRUCTURE d’exploration de données &#40; DMX &#41;](../dmx/alter-mining-structure-dmx.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
SELECT [FLATTENED] [TOP <n>] <expression list> FROM <model>.CASES  
[WHERE <condition expression>][ORDER BY <expression> [DESC|ASC]]  
```  
  
## <a name="arguments"></a>Arguments  
 *n*  
 Ce paramètre est facultatif. Entier qui spécifie le nombre de lignes à retourner.  
  
 *liste d’expressions*  
 Liste d'expressions séparées par des virgules. Une expression peut comprendre des identificateurs de colonne, des fonctions définies par l'utilisateur, des fonctions VBA, etc.  
  
 Pour inclure une colonne de structure qui n'est pas incluse dans le modèle d'exploration de données, utilisez la fonction `StructureColumn('<structure column name>')`.  
  
 *model*  
 Identificateur du modèle  
  
 *expression de condition*  
 Condition pour restreindre les valeurs retournées de la liste des colonnes.  
  
 *expression*  
 Ce paramètre est facultatif. Expression qui retourne une valeur scalaire.  
  
## <a name="remarks"></a>Notes  
 Si l'extraction est activée à la fois sur le modèle d'exploration de données et la structure d'exploration de données, les utilisateurs membres d'un rôle qui a des autorisations d'extraction sur le modèle et la structure peuvent accéder aux colonnes de la structure d'exploration de données qui ne sont pas incluses dans le modèle d'exploration de données. Par conséquent, pour protéger les données sensibles ou personnelles, vous devez construire votre vue de source de données pour masquer les informations personnelles et accorder **AllowDrillthrough** autorisation sur une structure d’exploration de données uniquement lorsque cela est nécessaire.  
  
 Le [Lag &#40; DMX &#41;](../dmx/lag-dmx.md) fonction peut être utilisée avec les modèles de série chronologique pour retourner ou filtrer sur le délai entre chaque cas et la durée initiale.  
  
 À l’aide de la [IsInNode &#40; DMX &#41;](../dmx/isinnode-dmx.md) de fonction dans le **où** clause retourne uniquement les cas qui sont associées au nœud qui est spécifié par la colonne NODE_UNIQUE_NAME de l’ensemble de lignes de schéma.  
  
## <a name="examples"></a>Exemples  
 Les exemples suivants sont basés sur la structure d’exploration de données Targeted Mailing, qui est basé sur le [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)]de base de données et ses modèles d’exploration de données associée. Pour plus d’informations, consultez [Basic Data Mining Tutorial](http://msdn.microsoft.com/library/6602edb6-d160-43fb-83c8-9df5dddfeb9c).  
  
### <a name="example-1-drillthrough-to-model-cases-and-structure-columns"></a>Exemple 1 : Extraction dans des cas de modèles et des colonnes de structure  
 L'exemple suivant retourne les colonnes de tous les cas qui ont été utilisés pour tester le modèle Targeted Mailing. Si la structure d'exploration de données sur laquelle le modèle est construit ne possède pas de jeu de données du test d'exclusion, cette requête retourne 0 cas. Vous pouvez utiliser la liste d'expressions pour retourner uniquement les colonnes dont vous avez besoin.  
  
```  
SELECT * FROM [TM Decision Tree].Cases  
WHERE IsTestCase();  
```  
  
### <a name="example-2-drillthrough-to-training-cases-in-a-specific-node"></a>Exemple 2 : Extraction dans des cas d'apprentissage dans un nœud spécifique  
 L'exemple suivant retourne uniquement les cas utilisés pour l'apprentissage de Cluster 2. Le nœud pour Cluster 2 a la valeur '002' pour la colonne NODE_UNIQUE_NAME. L'exemple retourne également une colonne de structure, [Customer Key], qui ne faisait pas partie du modèle d'exploration de données, et fournit l'alias `CustomerID` pour la colonne. Notez que le nom de la colonne de structure est passé en tant que valeur de chaîne ; par conséquent, il doit être entre guillemets, et non entre crochets.  
  
```  
SELECT StructureColumn('Customer Key') AS CustomerID, *   
FROM [TM_Clustering].Cases  
WHERE IsTrainingCase()  
AND IsInNode('002')  
```  
  
 Pour retourner une colonne de structure, les autorisations d'extraction doivent être activées à la fois sur le modèle d'exploration de données et sur la structure d'exploration de données.  
  
> [!NOTE]  
>  La prise en charge de l'extraction varie selon le type de modèle d'exploration de données. Pour plus d’informations sur les modèles qui prennent en charge l’extraction, consultez [requêtes d’extraction &#40; exploration de données &#41;](../analysis-services/data-mining/drillthrough-queries-data-mining.md).  
  
## <a name="see-also"></a>Voir aussi  
 [SÉLECTIONNEZ &#40; DMX &#41;](../dmx/select-dmx.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Instructions de définition de données](../dmx/dmx-statements-data-definition.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Instructions de Manipulation de données](../dmx/dmx-statements-data-manipulation.md)   
 [Les Extensions d’exploration de données &#40; DMX &#41; Référence des instructions](../dmx/data-mining-extensions-dmx-statements.md)  
  
  

