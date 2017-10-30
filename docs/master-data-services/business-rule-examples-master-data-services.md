---
title: "Exemples de règles d’entreprise (Master Data Services) | Microsoft Docs"
ms.custom: 
ms.date: 01/05/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3974b9be-4b7c-4a37-ab26-1a36ef455744
caps.latest.revision: 21
author: smartysanthosh
ms.author: nagavo
manager: craigg
ms.workload: On Demand
ms.translationtype: HT
ms.sourcegitcommit: 0b832a9306244210e693bde7c476269455e9b6d8
ms.openlocfilehash: 57ecfaefcf4ba428e05617b89423e72774a50a51
ms.contentlocale: fr-fr
ms.lasthandoff: 09/07/2017

---
# <a name="business-rule-examples-master-data-services"></a>Exemples de règles d’entreprise (Master Data Services)
Cet article présente des exemples de règles d’entreprise pour [!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)]. Vous trouverez ces exemples dans les exemples de modèles qui sont inclus dans votre installation de [!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)].   
  
Pour obtenir des instructions sur la manière de déployer les exemples de modèles, consultez [Installation et configuration de Master Data Services](../master-data-services/master-data-services-installation-and-configuration.md).  
  
  
## <a name="business-rule-examples"></a>Exemples de règles d’entreprise  
Exemple de modèle |Entité  |Nom de la règle d’entreprise| Description  
---------|---------|---------|-----------|  
Customer    | Customer   | Person pmt terms| Spécifie les conditions de paiement par défaut des clients.          
Dans la règle d’entreprise suivante, si la valeur de l’attribut CustomerType répond à la `is equal` [rule condition](../master-data-services/business-rule-conditions-master-data-services.md), then the `defaults to` [rule action](../master-data-services/business-rule-conditions-master-data-services.md) is applied to the PaymentTerms attribute. Dans le cas contraire, aucune action n’est effectuée.  
```  
If  
    CustomerType is equal to 2  
Then  
    PaymentTerms defaults to CASH  
Else  
    None      
```  
  
**--------------------------------------------------**  
  
Exemple de modèle  |Entité  |Nom de la règle d’entreprise|Description    
---------|---------|---------|---------------  
Customer     | Customer    | Org pmt terms | Spécifie les conditions de paiement par défaut des organisations.         
Dans la règle d’entreprise suivante, si la valeur de l’attribut CustomerType répond à la `is equal` [rule condition](../master-data-services/business-rule-conditions-master-data-services.md), then the `defaults to` [rule action](../master-data-services/business-rule-actions-master-data-services.md) is applied to the PaymentTerms attribute. Dans le cas contraire, aucune action n’est effectuée.  
```  
If  
    CustomerType is equal to 1  
Then  
    PaymentTerms defaults to 210Net30  
Else  
    None  
```  
  
**--------------------------------------------------**  
  
  
Exemple de modèle  |Entité  |Nom de la règle d’entreprise| Description    
---------|---------|---------|-----------  
Product     |  Product       | DaysToManufacture |Spécifie la plage de jours avant la fabrication pour une fabrication en interne.          
Dans la règle d’entreprise suivante, si la valeur de l’attribut InHouseManufacture répond à la `is equal` [rule condition](../master-data-services/business-rule-conditions-master-data-services.md), then the `must be between` [rule action](../master-data-services/business-rule-actions-master-data-services.md) is applied to the DaysToManufacture attribute. Dans le cas contraire, aucune action n’est effectuée.  
```  
If  
    InHouseManufacture is equal to Y  
Then  
    DaysToManufacture must be between 1 and 10  
Else  
    None  
```  
  
**--------------------------------------------------**  
  
  
Exemple de modèle  |Entité  |Nom de la règle d’entreprise|Description    
---------|---------|---------|-------------  
Product     |Product         |Required fields| Spécifie les attributs obligatoires pour les membres de l’entité Product.           
Dans la règle d’entreprise suivante, si toutes les conditions sont réunies, `is required` [l’action de validation](../master-data-services/business-rule-actions-master-data-services.md) est effectuée pour les attributs spécifiés. Les valeurs de l’attribut ne peuvent pas être Null ni vides.  
```  
If  
    None  
Then  
    Name is required  
    ProductSubCategory is required  
    Color is required  
    StandardCost is required  
    SafetyStockLevel is required  
    ReorderPoint is required  
    InHouseManufacture is required  
    SellStartDate is required  
    FinishedGoodIndicator is required  
    ProductLine is required  
Else  
    None  
```  
  
**--------------------------------------------------**  
  
  
Exemple de modèle  |Entité  |Nom de la règle d’entreprise|Description    
---------|---------|---------|-----------  
Product     | Product        |  Std Cost| Exige que le coût standard soit supérieur à 0.        
Dans la règle d’entreprise suivante, si toutes les conditions sont réunies, `must be greater than` [rule action](../master-data-services/business-rule-actions-master-data-services.md) is applied to the StandardCost attribute of products.  
```  
If  
    None  
Then  
    StandardCost must be greater than 0  
Else  
    None  
```  
  
**--------------------------------------------------**  
  
  
Exemple de modèle  |Entité  |Nom de la règle d’entreprise|Description    
---------|---------|---------|------------  
Product     | Product        | FG MSRP Cost|Spécifie que si le produit est un produit fini, le prix de vente conseillé et les coûts du revendeur doivent être supérieurs à 0.           
  
Dans la règle d’entreprise suivante, si la valeur de l’attribut FinishedGoodIndicator répond à la `is equal` [rule condition](../master-data-services/business-rule-conditions-master-data-services.md), the `must be greater than` [rule action](../master-data-services/business-rule-actions-master-data-services.md) is applied to the MSRP and DealerCost attributes.  
```  
If  
    FinishedGoodIndicator is equal to Y  
Then  
    MSRP must be greater than 0  
    DealerCost must be greater than 0  
Else  
    None  
```  
  
**--------------------------------------------------**  
  
  
Exemple de modèle  |Entité  |Nom de la règle d’entreprise|Description    
---------|---------|---------|------------  
Product     | Product        |  Default Name| Spécifie le nom de produit par défaut sur la base des valeurs des attributs Color et Class. Lorsque la valeur de l’attribut Color n’est pas YLO et que la valeur de l’attribut Class n’est pas NA, le nom par défaut est Yellow NA.         
Dans la règle d’entreprise suivante, si la valeur des attributs Class et Color ne répondent pas à la condition de règle `is equal` , `defaults to` [l’action de règle](../master-data-services/business-rule-actions-master-data-services.md) est appliquée à l’attribut Name.  
```  
If  
    (Color is equal to YLO AND Class is equal to NA) is not true  
Then  
    Name defaults to Yellow NA  
Else  
    Name defaults to Other  
```  
  
**--------------------------------------------------**  
  
  
**Pour afficher les exemples de règles d’entreprise dans les exemples de modèles**  
1. Accédez au site web [!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)] que vous avez configuré après l’installation de MDS, puis cochez la case **Administration système** .   
Pour obtenir des instructions sur la configuration du site web, consultez [Installation et configuration de Master Data Services](../master-data-services/master-data-services-installation-and-configuration.md).  
2. Cliquez sur l’exemple de modèle qui contient la règle d’entreprise, comme indiqué dans les tableaux ci-dessus, puis cliquez sur **Entités**.  
3. Cliquez sur l’entité à laquelle la règle s’applique, comme indiqué dans les tableaux ci-dessus, puis cliquez sur **Règles d’entreprise**.  
4. Cliquez sur le nom de la règle d’entreprise que vous souhaitez afficher. L’interface utilisateur se développe pour afficher les instructions **If**, **Then** et **Else** .  
  
## <a name="did-this-article-help-you-were-listening"></a>Cet article vous a-t-il été utile ? Nous sommes à votre écoute   
Quels renseignements souhaitez-vous obtenir ? Avez-vous trouvé ce que vous cherchiez ? Nous tenons compte de vos commentaires pour améliorer le contenu de nos articles. Veuillez envoyer vos commentaires à l’adresse suivante : [sqlfeedback@microsoft.com](mailto:sqlfeedback@microsoft.com).   
  
  
  
  


