---
title: Élément (MDDataSet) (XMLA) de la cellule | Documents Microsoft
ms.custom: ''
ms.date: 03/16/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- Cell Element (MDDataSet)
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- microsoft.xml.analysis.cell
- http://schemas.microsoft.com/analysisservices/2003/engine#Cell
- urn:schemas-microsoft-com:xml-analysis#Cell
helpviewer_keywords:
- Cell element
ms.assetid: c4ea08a4-f653-4ade-be07-b91eb5b1ef32
caps.latest.revision: 13
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: d6c59b1833e211e43c9429e6bf4aeb265325d76d
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2018
---
# <a name="cell-element-mddataset-xmla"></a>Élément Cell (MDDataSet) (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]Contient des informations sur une cellule unique contenue par un parent [CellData](../../../analysis-services/xmla/xml-elements-properties/celldata-element-xmla.md) élément.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
<CellData>  
   <Cell CellOrdinal="unsignedInt">  
      <!-- Zero or more cell property values -->  
      <!-- or -->  
      <Error>...</Error>  
   </Cell>  
</CellData>  
```  
  
## <a name="element-characteristics"></a>Caractéristiques de l'élément  
  
|Caractéristique|Description|  
|--------------------|-----------------|  
|Type de données et longueur|None|  
|Valeur par défaut|None|  
|Cardinalité|0-n : élément facultatif pouvant apparaître plusieurs fois.|  
  
## <a name="element-relationships"></a>Relations entre les éléments  
  
|Relation|Élément|  
|------------------|-------------|  
|Éléments parents|[CellData](../../../analysis-services/xmla/xml-elements-properties/celldata-element-xmla.md)|  
|Éléments enfants|Zéro ou plusieurs valeurs de propriété de cellule ou [erreur](../../../analysis-services/xmla/xml-elements-properties/error-element-xmla.md)|  
  
## <a name="attributes"></a>Attributs  
  
|Attribute|Description|  
|---------------|-----------------|  
|CellOrdinal|Requis **unsignedInt** attribut. Position ordinale de la cellule dans le dataset multidimensionnel.|  
  
## <a name="remarks"></a>Notes   
 Dans le parent **racine** élément, le **Axes** élément est suivi par le **CellData** , une collection de **cellule** éléments contenant les valeurs de propriété pour chaque cellule retournée dans le dataset multidimensionnel. Le **cellule** élément contient le **CellOrdinal** attribut, qui indique la position ordinale de base zéro de la cellule dans le jeu de données multidimensionnel et à un élément pour chaque valeur de propriété de cellule associée à la cellule. Chaque valeur de propriété de cellule dans le **cellule** est définie par un élément XML distinct. La valeur de la propriété de cellule est les données contenues dans l’élément XML et le nom de la propriété de cellule, tel que défini dans le **CellInfo** élément de l’élément racine parent, correspond au nom de l’élément XML.  
  
 La syntaxe suivante décrit une valeur de propriété de cellule :  
  
```  
<CellProperty xsi:type="string">value</CellProperty>  
```  
  
 Le type de données d'une valeur de propriété de cellule est spécifié uniquement pour la propriété de cellule VALUE. Les types de données des autres propriétés de cellule sont déterminées par la définition de propriété de cellule incluse dans le **CellInfo** élément. Un élément de valeur de propriété de cellule peut être exclu si une valeur par défaut a été spécifiée (en incluant un **par défaut** , élément pour une définition de propriété de cellule contenue dans le **CellInfo** élément) pour une propriété de cellule, ou si aucune valeur par défaut n’a été spécifié et la valeur de la propriété de cellule a la valeur null.  
  
## <a name="cell-property-errors"></a>Erreurs de propriété de cellule  
 Si une propriété de cellule ne peut pas être retournée en raison d’une erreur qui se produit sur l’instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], telle qu’une erreur de calcul qui empêche que la valeur retournée pour une cellule donnée, une **erreur** élément remplace le contenu de la propriété de cellule en question. L'exemple XML suivant décrit une erreur de propriété de cellule :  
  
```  
<Cell CellOrdinal="0">  
   <Value xsi:type="xsd:double">  
      <Error>  
         <ErrorCode>2148497527</ErrorCode>  
         <Description>Unknown error</Description>  
      </Error>  
   </Value>  
</Cell>  
```  
  
## <a name="calculating-cell-ordinal-values"></a>Calcul des valeurs ordinales d'une cellule  
 Les axes de référence pour une cellule peut être calculée d’après un **CellOrdinal** valeur d’attribut. Point de vue conceptuel, les cellules sont numérotées dans un dataset comme si le jeu de données ont été un *p*-tableau dimensionnel, où *p* est le nombre d’axes. Les cellules sont traitées dans l'ordre ligne-champ.  
  
 Imaginez une requête demandant quatre mesures sur les colonnes et une jointure croisée de deux états (State) avec quatre trimestres (Quarter) sur les lignes. En suivant le résultat du dataset, la **CellOrdinal** propriété pour la partie du résultat du dataset affichée en gras est le jeu {9, 10, 11, 13, 14, 15, 17, 18, 19}. Il s’agit du jeu, car les cellules sont numérotées dans l’ordre ligne-champ, en commençant par un **CellOrdinal** 0 pour la cellule supérieure gauche.  
  
|État|Quarter|Unit Sales|Store Cost|Store Sales|Sales Count|  
|-----------|-------------|----------------|----------------|-----------------|-----------------|  
|California|Q1|16890|14431.09|36175.2|5498|  
||Q2|18052|15332.02|38396.75|5915|  
||3E TRIMESTRE|18370|**15672.83**|**39394.05**|**6014**|  
||Q4|21436|**18094.5**|**45201.84**|**7015**|  
|Oregon|Q1|19287|**16081.07**|**40170.29**|**6184**|  
||Q2|15079|12678.96|31772.88|4799|  
||3E TRIMESTRE|16940|14273.78|35880.46|5432|  
||Q4|16353|13738.68|34453.44|5196|  
|Washington|Q1|30114|25240.08|63282.86|9906|  
||Q2|29479|24953.25|62496.64|9654|  
||3E TRIMESTRE|30538|25958.26|64997.38|10007|  
||Q4|34235|29172.72|73016.34|11217|  
  
 Si l'on applique la formule présentée dans la figure, l'axe k = 0 possède Uk = 4 membres et l'axe k = 1 possède Uk = 8 tuples. P = 2 correspond au nombre total d'axes dans la requête. Si l'on définit la cellule correspondant à {California, Q3, Store Cost} en tant que valeur S0, la somme de départ est i = 0 à 1. Pour i = 0, la valeur ordinale du tuple sur l'axe 0 de {Store Cost} est 1. Pour i = 1, l'ordinal du tuple de {CA, Q3} est 2.  
  
 Pour i = 0, Ei = 1, c’est le cas pour i = 0 la somme est 1 * 1 = 1 et pour i = 1, la somme est 2 (valeur ordinale du tuple) heures 4 (valeur Ei calculée sous la forme 1 \* 4), ou 8. La somme de 1 + 8 est ensuite 9, soit l'ordinal de cette cellule.  
  
## <a name="example"></a> Exemple  
 L’exemple suivant illustre la structure de la **cellule** élément, y compris la valeur, FORMATTED_VALUE et FORMAT_STRING des valeurs de propriété pour chaque cellule de la cellule.  
  
```  
<CellData>  
   <Cell CellOrdinal="0">  
      <Value xsi:type="xsd:double">16890</Value>  
      <FmtValue>16,890.00</FmtValue>  
      <FormatString>Standard</FormatString>  
   </Cell>  
   <Cell CellOrdinal="1">  
      <Value xsi:type="xsd:int">50</Value>  
      <FmtValue>50</FmtValue>  
      <FormatString>Standard</FormatString>  
   </Cell>  
   <Cell CellOrdinal="2">  
      <Value xsi:type="xsd:double">36175.2</Value>  
      <FmtValue>$36,175.20</FmtValue>  
      <FormatString>Currency</FormatString>  
   </Cell>  
</CellData>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Type de données MDDataSet &#40; XMLA &#41;](../../../analysis-services/xmla/xml-data-types/mddataset-data-type-xmla.md)   
 [Propriétés &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
