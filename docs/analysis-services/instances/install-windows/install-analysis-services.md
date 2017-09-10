---
title: Installer Analysis Services | Documents Microsoft
ms.custom:
- SQL2016_New_Updated
ms.date: 04/11/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd6ac80d-b735-4e3e-a024-489f1409ad33
caps.latest.revision: 20
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 4ba3bacb78e49319db1e458d776cead3429e6c60
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="install-sql-server-analysis-services"></a>Installer SQL Server Analysis Services
  SQL Server Analysis Services est un serveur de base de données analytique hébergeant des modèles tabulaires, des cubes multidimensionnels et des modèles d’exploration de données que vous pouvez accéder à partir de rapports, feuilles de calcul et tableaux de bord.  
  
 Analysis Services est multi-instance, ce qui signifie que vous pouvez installer plusieurs copies sur un seul ordinateur ou exécuter des versions anciennes et nouvelles côte à côte. Les instances que vous installez sont exécutées dans un des trois modes, selon ce que vous avez spécifié pendant l’installation : multidimensionnel et exploration de données, tabulaire ou SharePoint. Si vous souhaitez utiliser plusieurs modes, vous devez avoir une instance distincte pour chacun.  
  
 Après avoir installé le serveur dans un mode donné, vous pouvez l’utiliser pour héberger des solutions conformes à ce mode. Par exemple, un serveur en mode tabulaire est indispensable si vous souhaitez accéder aux données du modèle tabulaire par le réseau.  
  
## <a name="get-tools-and-designers"></a>Obtenir les outils et les concepteurs  
 Le programme d’installation de SQL Server n’installe plus les concepteurs de modèles ou les outils de gestion utilisés pour la conception de solutions ou l’administration de serveurs. Dans cette version, les outils ont une installation distincte, que vous pouvez obtenir à partir des liens suivants :  
  
-   [Télécharger SQL Server Management Studio (SSMS)](https://msdn.microsoft.com/library/mt238290.aspx)  
  
-   [Télécharger SSDT (SQL Server Data Tools)](https://msdn.microsoft.com/library/mt204009.aspx)  
  
 Vous aurez besoin de SSMS et SSDT pour travailler avec des données et des instances d’Analysis Services. Outils peuvent être installés n’importe où, mais veillez à configurer des ports sur le serveur avant de tenter une connexion. Pour plus d'informations, consultez [Configure the Windows Firewall to Allow Analysis Services Access](../../../analysis-services/instances/configure-the-windows-firewall-to-allow-analysis-services-access.md) .  
  
## <a name="install-using-a-wizard"></a>Installer à l’aide d’un assistant  
 La liste suivante montre les pages de l’assistant Installation de SQL Server utilisées pour installer Analysis Services :  
  
1.  Sélectionnez **Analysis Services** dans l'Arborescence de fonctionnalités dans l'Installation.  
  
     ![Arborescence de fonctionnalités du programme d’installation d’Analysis Services](../../../analysis-services/instances/install-windows/media/ssas-setupas.gif "arborescence de fonctionnalités du programme d’installation d’Analysis Services")  
  
2.  Dans la page Configuration d’Analysis Services, sélectionnez un mode. En mode tabulaire est la valeur par défaut...  
  
     ![Page d’installation avec les options de configuration d’Analysis Services](../../../analysis-services/instances/install-windows/media/ssas-setupasconfig.png "page le programme d’installation avec les options de configuration d’Analysis Services")  
  
  En mode tabulaire utilise le moteur analytique d’en mémoire xVelocity (VertiPaq), qui est le stockage par défaut pour les modèles tabulaires. Après avoir déployé les modèles tabulaires sur le serveur, vous pouvez configurer de manière sélective les solutions tabulaires pour utiliser le stockage de disque de DirectQuery comme alternative au stockage gourmand en mémoire.  
 
 Multidimensionnel et exploration de données en mode utilisation MOLAP comme stockage par défaut pour les modèles déployés dans Analysis Services. Après avoir déployé sur le serveur, vous pouvez configurer une solution pour utiliser ROLAP si vous souhaitez exécuter des requêtes directement sur la base de données relationnelle plutôt que de stocker les données de la requête dans une base de données multidimensionnelle Analysis Services.  
  

  
 La gestion de la mémoire et les paramètres d’E/S peuvent être ajustés pour obtenir de meilleures performances lors de l’utilisation des modes de stockage qui ne sont pas définis par défaut. Pour plus d’informations, consultez [Propriétés du serveur dans Analysis Services](../../../analysis-services/server-properties/server-properties-in-analysis-services.md) .  
  
## <a name="command-line-setup"></a>Installation à partir de ligne de commande  
 L’installation de SQL Server inclut un paramètre (**ASSERVERMODE**) qui spécifie le mode serveur. L'exemple suivant illustre une installation par ligne de commande qui installe Analysis Services en mode serveur tabulaire.  
  
```  
  
Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /FEATURES=AS /ASSERVERMODE=TABULAR /INSTANCENAME=ASTabular /INDICATEPROGRESS/ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
```  
  
 **INSTANCENAME** doit contenir moins de 17 caractères.  
  
 Toutes les valeurs de compte de l'espace réservé doivent être remplacées par des comptes valides et un mot de passe.  
  
 La casse est prise en compte pour**ASSERVERMODE** .  Toutes les valeurs doivent être exprimées en majuscules. Le tableau suivant décrit les valeurs valides pour **ASSERVERMODE**.  
  
|Valeur|Description|  
|-----------|-----------------|  
|TABULAR|Ceci est la valeur par défaut. Si vous ne définissez pas **ASSERVERMODE**, le serveur est installé en mode tabulaire.|
|MULTIDIMENSIONAL|Cette valeur est facultative.|  
|POWERPIVOT|Cette valeur est facultative. En pratique, si vous définissez le paramètre **ROLE** , le mode serveur est automatiquement défini sur 1, ce qui rend **ASSERVERMODE** facultatif pour une installation de [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] pour SharePoint. Pour plus d’informations, consultez [Installer Power Pivot à partir de l’invite de commandes](http://msdn.microsoft.com/en-us/7f1f2b28-c9f5-49ad-934b-02f2fa6b9328).|  
  
  
## <a name="see-also"></a>Voir aussi  
 [Déterminer le mode serveur d'une instance Analysis Services](../../../analysis-services/instances/determine-the-server-mode-of-an-analysis-services-instance.md)   
 [Modélisation tabulaire (SSAS tabulaire)](https://msdn.microsoft.com/library/hh212945(v=sql.110).aspx)  
  
  

