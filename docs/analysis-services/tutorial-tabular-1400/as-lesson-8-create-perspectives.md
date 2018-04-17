---
title: Analysis Services tutorial leçon 8 créer perspectives | Documents Microsoft
description: Décrit comment créer des perspectives dans le projet du didacticiel Analysis Services.
ms.prod_service: analysis-services, azure-analysis-services
services: analysis-services
ms.suite: pro-bi
documentationcenter: ''
author: Minewiskan
manager: kfile
editor: ''
tags: ''
ms.assetid: ''
ms.service: analysis-services
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: na
ms.date: 02/20/2018
ms.author: owend
monikerRange: '>= sql-analysis-services-2017 || = sqlallproducts-allversions'
ms.openlocfilehash: 7b6d5dd474719f33d285ac04f1643f330a618a7a
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="create-perspectives"></a>Créer des perspectives

[!INCLUDE[ssas-appliesto-sql2017-later-aas](../../includes/ssas-appliesto-sql2017-later-aas.md)]

Dans cette leçon, vous créez une perspective Internet Sales. Une perspective définit un sous-ensemble visualisable d'un modèle et des points de vue du modèle focalisés sur un domaine d'activité ou sur une application. Lorsqu’un utilisateur se connecte à un modèle à l’aide d’un point de vue, ils voient uniquement les objets de modèle (tables, colonnes, mesures, hiérarchies et KPI) en tant que champs définis dans cette perspective. Pour plus d’informations, consultez [Perspectives](../tabular-models/perspectives-ssas-tabular.md).
  
La perspective Internet Sales que vous créez dans cette leçon exclut l’objet de la table DimCustomer. Lorsque vous créez une perspective qui exclut certains objets de vue, cet objet existe toujours dans le modèle. Toutefois, il n’est pas visible dans une liste de champs de client création de rapports. Les colonnes calculées et les mesures incluses ou non dans une perspective peuvent toujours être calculées à partir de données d'objet exclues.  
  
L'objectif de cette leçon est plutôt de décrire comment créer des points de vue et de vous familiariser avec les outils de création de modèles tabulaires. Si vous développez ultérieurement ce modèle pour inclure des tables supplémentaires, vous pouvez créer des perspectives supplémentaires pour définir les différents points de vue du modèle, par exemple, l’inventaire et les ventes.  
  
Durée estimée pour effectuer cette leçon : **cinq minutes**  
  
## <a name="prerequisites"></a>Configuration requise  

Cet article fait partie d’un didacticiel de modélisation tabulaire, qui doit être effectué dans l’ordre. Avant d’effectuer les tâches de cette leçon, vous devez avoir terminé la leçon précédente : [leçon 7 : créer des indicateurs de Performance clés](../tutorial-tabular-1400/as-lesson-7-create-key-performance-indicators.md).  
  
## <a name="create-perspectives"></a>Créer des perspectives  
  
#### <a name="to-create-an-internet-sales-perspective"></a>Pour créer une perspective Internet Sales  
  
1.  Cliquez sur le **modèle** menu > **Perspectives** > **créer et gérer**.  
  
2.  Dans la boîte de dialogue **Perspectives** , cliquez sur **Nouvelle perspective**.  
  
3.  Double-cliquez sur le **nouvelle Perspective** en-tête de colonne, puis renommez **Internet Sales**.  
  
4.  Sélectionnez toutes les tables *sauf* **DimCustomer**.  
  
    ![en tant que-lesson8-perspectives](../tutorial-tabular-1400/media/as-lesson8-perspectives.png)
  
    Dans une prochaine leçon, vous utilisez la fonctionnalité analyser dans Excel pour tester cette perspective. La liste de champs de tableau croisé dynamique Excel inclut chaque table à l’exception de la table DimCustomer.  

## <a name="whats-next"></a>Quelle est l’étape suivante ?

[Leçon 9 : Créer des hiérarchies](../tutorial-tabular-1400/as-lesson-9-create-hierarchies.md).
  
  
  
  
