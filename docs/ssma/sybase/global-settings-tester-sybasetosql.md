---
title: "Paramètres globaux (testeur) (SybaseToSQL) | Documents Microsoft"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 6f0b9cea-5a24-4e42-8bbf-c4516b00da23
caps.latest.revision: 7
author: Shamikg
ms.author: Shamikg
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 21178ca7326678504244658192d7395bab79a9ac
ms.contentlocale: fr-fr
ms.lasthandoff: 08/02/2017

---
# <a name="global-settings-tester-sybasetosql"></a>Paramètres globaux (testeur) (SybaseToSQL)
Utilisez la page testeur de la **paramètres globaux** boîte de dialogue pour spécifier les paramètres de SSMA testeur.  
  
Pour accéder aux paramètres testeur, sur le **outils** menu, sélectionnez **paramètres globaux**, puis cliquez sur **testeur** en bas du volet gauche.  
  
## <a name="options"></a>Options  
**Analyse de l’objet contrôlable**  
Ce paramètre spécifie s’il faut effectuer l’analyse des objets Testable. Sélectionnez **Oui** si vous souhaitez que le testeur de SSMA pour analyser et de rechercher automatiquement les objets dépendants. Ensemble d’option par défaut est **Oui**.  
  
Les options suivantes sont disponibles pour ce paramètre :  
  
1.  Oui  
  
2.  Non  
  
**Mode d’économie de tables auxiliaires**  
Ce paramètre spécifie comment enregistrer les tables auxiliaires internes créés pendant l’exécution du cas de test. Options suivantes peuvent être définies pour ce paramètre :  
  
1.  Toujours supprimer  
  
2.  Toujours enregistrer  
  
3.  Enregistrer en cas d’échec de la comparaison des tables  
  
4.  Demander à l’utilisateur si la comparaison de la Table a échoué  
  
L’option par défaut définie est : **toujours supprimer**.  
  
**Effectuer la restauration de données**  
Ce paramètre spécifie s’il faut effectuer une opération de restauration après l’exécution de chaque cas de test. Ensemble d’option par défaut est **non**.  
  
Les options suivantes sont disponibles pour ce paramètre :  
  
1.  Oui  
  
2.  Non  
  
**Arrêter l’exécution de tests après la première défaillance**  
Ce paramètre spécifie s’il faut arrêter le cas de test en cours d’exécution en cours, si une erreur s’est produite lors de l’exécution. Ensemble d’option par défaut est **Oui**.  
  
Les options suivantes sont disponibles pour ce paramètre :  
  
1.  Oui  
  
2.  Non  
  
## <a name="see-also"></a>Voir aussi  
[Terminer la préparation du cas de Test &#40; SybaseToSQL &#41;](../../ssma/sybase/finishing-test-case-preparation-sybasetosql.md)  
  

