---
title: "Élément KPI (CSDLBI) | Documents Microsoft"
ms.custom: 
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
applies_to: SQL Server 2016 Preview
ms.assetid: 203ee6e8-eef2-4476-b09f-bd95e492ddaa
caps.latest.revision: "13"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 28f4f65bc65ac1a5d231717ddbc552e83ef302de
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2018
---
# <a name="kpi-element-csdlbi"></a>Élément KPI (CSDLBI)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]L’élément Kpi définit un calcul qui peut être utilisé comme un indicateur de Performance clé (KPI). Dans un modèle de données Business Intelligence, les indicateurs de performance clés sont basés sur les mesures et, comme telles, la définition de l'indicateur de performance clé contient toutes les métadonnées associées à des mesures, ainsi que les informations nécessaires pour la présentation des valeurs d'indicateur de performance clé, notamment un graphique par défaut.  
  
 L'élément Kpi ne spécifie pas la formule, contenue dans la définition de la mesure, mais spécifie plutôt les métadonnées supplémentaires associées aux mesures utilisées comme indicateur de performance clé. Une fois que vous avez désigné une mesure en tant qu'indicateur de performance clé, vous ne pouvez pas l'utiliser comme mesure dans d'autres contextes.  
  
## <a name="elements-and-attributes"></a>Éléments et attributs  
 Le tableau suivant répertorie les éléments et les attributs qui définissent l'élément Kpi.  
  
|Nom   |Est obligatoire|Description|  
|----------|-----------------|-----------------|  
|Documentation|non|Description du KPI.|  
|KpiGoal|Oui|Référence à une colonne qui contient des valeurs qui peuvent être utilisées comme cible.<br /><br /> Consultez [Élément PropertyRef &#40;CSDLBI&#41;](../../../analysis-services/tabular-model-programming-compatibility-levels-1050-1103/conceptual-schema-definition-language-csdl/propertyref-element-csdlbi.md).|  
|KpiStatus|Oui|Référence à une colonne qui contient des valeurs qui représentent l'état actuel de l'indicateur de performance clé.|  
|StatusGraphic|Oui|Référence à une image qui indique une progression négative, neutre ou positive sur les cibles définies dans l'indicateur de performance clé.|  
  
## <a name="remarks"></a>Notes   
 Lorsque vous concevez un modèle, vous pouvez créer un indicateur de performance clé en créant une mesure, puis en attribuant la mesure à utiliser comme indicateur de performance clé. Vous ajoutez ensuite des informations spécifiques aux indicateurs de performance clés, tels qu'un graphique à utiliser dans l'affichage des tendances.  
  
## <a name="example"></a> Exemple  
 **Tabulaire**  
  
 L'exemple suivant, dans CSDLBI version 1.0, illustre un indicateur de performance clé qui mesure les ventes, de l'exemple de modèle tabulaire AdventureWorks.  
  
```  
  
<Property Name="InternetCurrSalesPerf" Type="Double">  
  <bi:Measure>  
    <bi:Kpi StatusGraphic="Three Stars Colored">  
      <bi:KpiGoal>  
        <bi:PropertyRef Name="v_InternetCurrSalesPerf_Goal" />  
      </bi:KpiGoal>  
      <bi:KpiStatus>  
        <bi:PropertyRef Name="v_InternetCurrSalesPerf_Status" />  
      </bi:KpiStatus>  
    </bi:Kpi>  
  </bi:Measure>  
</Property>  
  
```  
  
## <a name="example"></a> Exemple  
 **(Multidimensionnel)**  
  
 L'exemple suivant, en CSDLBI version 1.1, illustre un indicateur de performance clé du cube Contoso Operations.  
  
```  
<Property Name="Sum_of_SalesAmount" Type="Decimal" Precision="19" Scale="4">  
   <Documentation>  
     <Summary>KPI Description</Summary>  
   </Documentation>  
     <bi:Measure   
         Caption="Sum of SalesAmount"   
         ReferenceName="Sum of SalesAmount"   
         FormatString="\$#,0.00;(\$#,0.00);\$#,0.00">  
     <bi:Kpi   
           StatusGraphic="Three Circles Colored">  
         <bi:KpiGoal>  
            <bi:PropertyRef Name="v_Sum_of_SalesAmount_Goal" />  
          </bi:KpiGoal>  
          <bi:KpiStatus>  
              <bi:PropertyRef Name="v_Sum_of_SalesAmount_Status" />  
          </bi:KpiStatus>  
     </bi:Kpi>  
     </bi:Measure>  
</Property>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Informations techniques de référence sur les annotations pour le décisionnel dans CSDL](../../../analysis-services/tabular-model-programming-compatibility-levels-1050-1103/conceptual-schema-definition-language-csdl/technical-reference-for-bi-annotations-to-csdl.md)  
  
  
