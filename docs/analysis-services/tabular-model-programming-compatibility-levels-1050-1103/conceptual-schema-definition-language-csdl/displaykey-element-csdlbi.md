---
title: "L’élément DisplayKey (CSDLBI) | Documents Microsoft"
ms.custom: 
ms.date: 03/07/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: tabular-models
ms.reviewer: 
ms.suite: sql
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to: SQL Server 2016 Preview
ms.assetid: 7d881278-1e77-42e1-8cfc-f1bbd9ec2340
caps.latest.revision: "12"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 9b1144f3df09cbb9d19b994e6dccebf25b1cdd6c
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2017
---
# <a name="displaykey-element-csdlbi"></a>Élément DisplayKey (CSDLBI)
  L'élément DisplayKey contient une liste des éléments suivants qui constituent ensemble un identificateur fort. DisplayKey existe uniquement en tant qu'enfant de l'élément EntityType. Il peut référencer des colonnes ou des fins de rôles.  
  
## <a name="elements-and-attributes"></a>Éléments et attributs  
 Le tableau suivant répertorie les attributs de l'élément DisplayKey.  
  
|Nom|Est obligatoire|Description|  
|----------|-----------------|-----------------|  
|IsDisplayKey|Non|True ou False|  
  
## <a name="remarks"></a>Notes  
 Cet élément est pour les rapports. L'élément auquel vous appliquez cet attribut n'a pas besoin d'être la clé de table réelle, seulement un élément que vous présenterez comme clé. Toutefois, la colonne utilisée pour l'élément DisplayKey doit contenir des valeurs uniques.  
  
## <a name="example"></a>Exemple  
 **Tabulaire**  
  
 L'exemple de code suivant, en CSDLBI version 1.1, illustre une colonne du modèle de données de l'exemple de base de données AdventureWorks qui a été désignée comme élément DisplayKey de la table.  
  
```  
<sample in progress>  
```  
  
## <a name="example"></a>Exemple  
 **(Multidimensionnel)**  
  
 L'exemple suivant, en CSDLBI version 1.1, illustre un extrait de la représentation du cube Contoso Operations. Dans ce modèle, la colonne Color a été marquée en tant que clé d’affichage pour la table Bikes.  
  
```  
  
<EntityType   
    Name="Bike">  
.. .. ..  
<Property   
    Name="Color"   
    Type="String"   
    MaxLength="Max"   
    Unicode="true"   
    FixedLength="false">  
<bi:Property   
    ContextualNameRule="Context"   
    Alignment="Left" Units="counts"   
    SortDirection="Descending"   
    IsRightToLeft="true"   
    DefaultAggregateFunction="Max" />  
</Property>  
.. .. ..  
<bi:EntityType>  
   <bi:DisplayKey>  
      <bi:MemberRef Name="Color" />  
   </bi:DisplayKey>>  
.. .. ..  
</bi:EntityType>  
</EntityType>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Présentation du modèle d’objet tabulaire au niveau de compatibilité 1050 1103 via des niveaux](../../../analysis-services/tabular-model-programming-compatibility-levels-1050-1103/representation/understanding-tabular-object-model-at-levels-1050-through-1103.md)   
 [Concepts CSDLBI](../../../analysis-services/tabular-model-programming-compatibility-levels-1050-1103/csdlbi-concepts.md)  
  
  
