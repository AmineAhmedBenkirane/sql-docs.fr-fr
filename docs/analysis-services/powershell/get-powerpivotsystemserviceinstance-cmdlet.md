---
title: Applet de commande Get-PowerPivotSystemServiceInstance | Documents Microsoft
ms.custom: 
ms.date: 03/01/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: analysis-services
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 56027a8e-1949-4349-b616-68c8b1d2963c
caps.latest.revision: "9"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 2e52176bc32adbaee46a22d3c4df6a331cf7c39b
ms.sourcegitcommit: f1a6944f95dd015d3774a25c14a919421b09151b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2017
---
# <a name="get-powerpivotsystemserviceinstance-cmdlet"></a>Applet de commande Get-PowerPivotSystemServiceInstance
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]Retourne une ou plusieurs instances de [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] Service système en cours d’exécution sur les serveurs d’applications dans la batterie de serveurs.  

>[!NOTE] 
>Cet article peut contenir des exemples et des informations obsolètes. Utilisez l’applet de commande Get-Help pour la dernière version.
  
 **S'applique à :** SharePoint 2010 et SharePoint 2013.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Get-PowerPivotSystemServiceInstance [-Identity <PowerPivotMidTierServiceInstancePipeBind>] [<CommonParameters>]  
```  
  
## <a name="description"></a>Description  
 L’applet de commande Get-PowerPivotSystemServiceInstance retourne les propriétés d’une ou plusieurs instances du service système [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] s’exécutant dans la batterie. L'applet de commande indique le type de l'application, son état (en ligne ou hors connexion), et son identité. Pour afficher les propriétés supplémentaires d'une instance spécifique, ajoutez le paramètre Identity et l'option format-list à l'applet de commande.  
  
## <a name="parameters"></a>Paramètres  
  
### <a name="-identity-powerpivotmidtierserviceinstancepipebind"></a>-Identité \<PowerPivotMidTierServiceInstancePipeBind >  
 Spécifie l'instance de service à obtenir. La valeur doit être un GUID valide qui identifie l'objet de manière unique dans la batterie.  
  
|||  
|-|-|  
|Requis ?|false|  
|Position ?|0|  
|Valeur par défaut||  
|Accepter l'entrée de pipeline ?|true|  
|Accepter les caractères génériques ?|false|  
  
### <a name="commonparameters"></a>\<Paramètres_courants >  
 Cette applet de commande prend en charge les paramètres communs : Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, WarningVariable, OutBuffer et OutVariable. Pour plus d’informations, consultez [About_CommonParameters](http://go.microsoft.com/fwlink/?linkID=227825)  
  
## <a name="inputs-and-outputs"></a>Entrées et sorties  
 Le type d'entrée correspond au type des objets que vous pouvez canaliser vers l'applet de commande. Le type de retour correspond au type des objets retournés par l'applet de commande.  
  
|||  
|-|-|  
|Entrées|Aucun.|  
|Sorties|Aucun.|  
  
## <a name="example-1"></a>Exemple 1  
  
```  
C:\PS>Get-PowerPivotSystemServiceInstance -Identity 1234567-890a-bcde-fghijklm | format-list| format-list  
```  
  
 Cet exemple retourne les propriétés supplémentaires de l'instance spécifiée, notamment le nom du serveur, la version et l'état de la mise à niveau.  
  
  
