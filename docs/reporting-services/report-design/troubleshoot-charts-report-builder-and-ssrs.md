---
title: "Résoudre les problèmes graphiques (Générateur de rapports et SSRS) | Documents Microsoft"
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a327ffa-3b69-40d6-8015-cc01cfae9161
caps.latest.revision: 7
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: Machine Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: a84dbd7d608d2de7ced66e66b49288fbf8fe1682
ms.contentlocale: fr-fr
ms.lasthandoff: 06/13/2017

---
# <a name="troubleshoot-charts-report-builder-and-ssrs"></a>Résoudre les problèmes liés aux graphiques (Générateur de rapports et SSRS)
  Ces problèmes peuvent être utiles lors de l'utilisation de graphiques.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="why-does-my-chart-count-not-sum-the-values-on-the-value-axis"></a>Pourquoi est-ce que mon graphique compte, au lieu d'additionner, les valeurs sur l'axe des ordonnées ?  
 La plupart des types de graphiques requièrent des valeurs numériques le long de l'axe des ordonnées, qui est en général l'axe des Y, pour qu'ils se dessinent correctement. Si le type de données du champ de valeur est **String**, le graphique ne peut pas afficher de valeur numérique, y compris en présence de chiffres dans les champs. À la place, le graphique affiche le nombre total de lignes qui contiennent une valeur dans ce champ. Pour éviter ce problème, assurez-vous que les champs que vous utilisez pour les séries de valeurs sont destinés à contenir des données numériques, par opposition aux champs de chaîne qui sont destinés à contenir des nombres mis en forme.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphiques &#40;Générateur de rapports et SSRS&#41;](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)  
  
  
