---
title: "Développement d’un composant de flux de données personnalisé | Documents Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: extending-packages-custom-objects
ms.reviewer: 
ms.suite: sql
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data flow task [Integration Services], extending
- data flow [Integration Services], extending
- extending data flow task [Integration Services]
- components [Integration Services], data flow
ms.assetid: be126913-2a9a-41c9-9bf5-a7b0a0aea2f8
caps.latest.revision: 57
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: On Demand
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: f25c74b52eaccb6c7b0e92cb7dace3d56f3cdd83
ms.contentlocale: fr-fr
ms.lasthandoff: 08/03/2017

---
# <a name="developing-a-custom-data-flow-component"></a>Développement d'un composant de flux de données personnalisé
  La tâche de flux de données comprend des composants qui se connectent à diverses sources de données et qui transforment et acheminent ces données à haut débit. [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] fournit un modèle d’objet extensible qui permet aux développeurs de créer des sources personnalisées, des transformations et destinations que vous pouvez utiliser dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] et dans des packages déployés. Cette section contient des rubriques qui vous guideront afin de développer des composants de flux de données personnalisés.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Création d’un composant de flux de données personnalisé](../../../integration-services/extending-packages-custom-objects/data-flow/creating-a-custom-data-flow-component.md)  
 Décrit les étapes initiales permettant de créer un composant de flux de données personnalisé.  
  
 [Méthodes de conception d’un composant de flux de données](../../../integration-services/extending-packages-custom-objects/data-flow/design-time-methods-of-a-data-flow-component.md)  
 Décrit les méthodes de conception à implémenter dans un composant de flux de données personnalisé.  
  
 [Méthodes d’exécution d’un composant de flux de données](../../../integration-services/extending-packages-custom-objects/data-flow/run-time-methods-of-a-data-flow-component.md)  
 Décrit les méthodes d'exécution à implémenter dans un composant de flux de données personnalisé.  
  
 [Plan d’exécution et Allocation de mémoire tampon](../../../integration-services/extending-packages-custom-objects/data-flow/execution-plan-and-buffer-allocation.md)  
 Décrit le plan d'exécution du flux de données et l'allocation des tampons de données.  
  
 [Utilisation des Types de données dans le flux de données](../../../integration-services/extending-packages-custom-objects/data-flow/working-with-data-types-in-the-data-flow.md)  
 Explique comment le flux mappe les types de données [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] aux types de données managées .NET Framework.  
  
 [Validation d’un composant de flux de données](../../../integration-services/extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md)  
 Explique les méthodes utilisées pour valider la configuration du composant et reconfigurer les métadonnées du composant.  
  
 [Implémentation des métadonnées externes](../../../integration-services/extending-packages-custom-objects/data-flow/implementing-external-metadata.md)  
 Explique comment utiliser des colonnes de métadonnées externes pour la validation des données.  
  
 [Composant de flux de déclenchement et définition d’événements dans les données](../../../integration-services/extending-packages-custom-objects/data-flow/raising-and-defining-events-in-a-data-flow-component.md)  
 Explique comment déclencher des événements prédéfinis et personnalisés.  
  
 [Enregistrement et définition d’entrées de journal dans les données de composant de flux](../../../integration-services/extending-packages-custom-objects/data-flow/logging-and-defining-log-entries-in-a-data-flow-component.md)  
 Explique comment créer et écrire des entrées de journal personnalisées.  
  
 [À l’aide de sorties d’erreur dans un composant de flux de données](../../../integration-services/extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md)  
 Explique comment rediriger des lignes d'erreur vers une autre sortie.  
  
 [La mise à niveau la Version d’un composant de flux de données](../../../integration-services/extending-packages-custom-objects/data-flow/upgrading-the-version-of-a-data-flow-component.md)  
 Explique comment mettre à jour les métadonnées de composant enregistrées lorsqu'une nouvelle version de votre composant est utilisée pour la première fois.  
  
 [Développement d’une Interface utilisateur pour un composant de flux de données](../../../integration-services/extending-packages-custom-objects/data-flow/developing-a-user-interface-for-a-data-flow-component.md)  
 Explique comment implémenter un éditeur personnalisé pour un composant.  
  
 [Composants de flux de développement de Types spécifiques de données](../../../integration-services/extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md)  
 Contient des informations sur le développement des trois types de composants de flux de données : sources, transformations et destinations.  
  
## <a name="reference"></a>Référence  
 <xref:Microsoft.SqlServer.Dts.Pipeline>  
 Contient les classes et les interfaces qui permettent de créer des composants de flux de données personnalisés.  
  
 <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper>  
 Contient les classes et interfaces qui composent le modèle objet de tâche de flux de données, lequel est utilisé pour créer des composants de flux de données personnalisés ou générer une tâche de flux de données.  
  
 <xref:Microsoft.SqlServer.Dts.Pipeline.Design>  
 Contient les classes et interfaces utilisées pour créer l'interface utilisateur des composants de flux de données.  
  
 [Integration Services Error and Message Reference](../../../integration-services/integration-services-error-and-message-reference.md)  
 Répertorie les codes d'erreur [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] prédéfinis avec leur nom symbolique et leur description.  
  
## <a name="related-sections"></a>Sections connexes  
  
### <a name="information-common-to-all-custom-objects"></a>Informations communes à tous les objets personnalisés  
 Pour obtenir les informations communes à tous les types d'objets personnalisés que vous pouvez créer dans [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], consultez les rubriques suivantes :  
  
 [Développement d’objets personnalisés pour Integration Services](../../../integration-services/extending-packages-custom-objects/developing-custom-objects-for-integration-services.md)  
 Décrit les étapes de base de l’implémentation de tous les types d’objets personnalisés pour [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].  
  
 [Persistance des objets personnalisés](../../../integration-services/extending-packages-custom-objects/persisting-custom-objects.md)  
 Décrit la persistance personnalisée et explique les situations dans lesquelles elle est nécessaire.  
  
 [Génération, déploiement et débogage d’objets personnalisés](../../../integration-services/extending-packages-custom-objects/building-deploying-and-debugging-custom-objects.md)  
 Décrit les techniques permettant de générer, signer, déployer et déboguer des objets personnalisés.  
  
### <a name="information-about-other-custom-objects"></a>Informations sur les autres objets personnalisés  
 Pour plus d’informations sur les autres types d’objets personnalisés que vous pouvez créer dans [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], consultez les rubriques suivantes :  
  
 [Développement d’une tâche personnalisée](../../../integration-services/extending-packages-custom-objects/task/developing-a-custom-task.md)  
 Explique comment programmer des tâches personnalisées.  
  
 [Développement d’un gestionnaire de connexions personnalisé](../../../integration-services/extending-packages-custom-objects/connection-manager/developing-a-custom-connection-manager.md)  
 Explique comment programmer des gestionnaires de connexions personnalisés.  
  
 [Développement d’un fournisseur de journal personnalisé](../../../integration-services/extending-packages-custom-objects/log-provider/developing-a-custom-log-provider.md)  
 Explique comment programmer des modules fournisseurs d'informations personnalisés.  
  
 [Développement d’un énumérateur ForEach personnalisé](../../../integration-services/extending-packages-custom-objects/foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 Décrit comment programmer des énumérateurs personnalisés.  
  
## <a name="see-also"></a>Voir aussi  
 [Étendre le flux de données avec le composant Script](../../../integration-services/extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md)   
 [Comparaison des Solutions de script et des objets personnalisés](../../../integration-services/extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md)  
  
  

