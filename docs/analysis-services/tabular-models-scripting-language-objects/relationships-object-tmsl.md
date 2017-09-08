---
title: Objet de relations (TMSL) | Documents Microsoft
ms.custom: 
ms.date: 05/30/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7588565f-ea34-4402-8be9-331188bdb8c2
caps.latest.revision: 7
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 260788cabb01d26215a51f0853b1b8dffc8163d5
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="relationships-object-tmsl"></a>Objet de relations (TMSL)

[!INCLUDE[ssas-appliesto-sql2016-later-aas](../../includes/ssas-appliesto-sql2016-later-aas.md)]

  Définit une relation entre une table source et cible, avec la possibilité de spécifier la cardinalité et la direction de filtres de requête et de sécurité.  
  
## <a name="object-definition"></a>Définition de l'objet  
 Tous les objets ont un ensemble commun de propriétés, y compris le nom, type, la description, une collection de propriétés et annotations. **Relation** objets ont également les propriétés suivantes.  
  
 isActive  
 Valeur booléenne qui indique si la relation est marquée comme Active ou Inactive. Une relation Active est automatiquement utilisée pour le filtrage entre les tables. Une relation Inactive peut être utilisée par les calculs DAX avec la fonction USERELATIONSHIP explicitement.  
  
 crossFilteringBehavior  
 Indique comment les relations influencent le filtrage des données. Consultez [bidirectionnelles entre les filtres pour les modèles tabulaires dans SQL Server 2016 Analysis Services](../../analysis-services/tabular-models/bi-directional-cross-filters-tabular-models-analysis-services.md) pour plus d’informations. Les valeurs valides sont les suivantes :  
  
-   OneDirection (1) : les lignes sélectionnées dans la terminaison « To » de la relation filtrent automatiquement les analyses de la table dans la terminaison « From » de la relation.  
  
-   BothDirections (2) - filtres sur des extrémités de la relation filtrent automatiquement l’autre table.  
  
-   Automatique (3) - le moteur analyse les relations et choisissez un des comportements en utilisant une heuristique.  
  
 joinOnDateBehavior  
 Lors de la jointure de deux colonnes de date/heure, indique s’il faut faire la jointure sur les parties date et heure, ou seulement sur la partie date.  
  
-   DateAndTime (1) - lors de la jonction de deux colonnes heure date, joignez les parties de date et d’heure.  
  
-   DatePartOnly (2) - lors de la jonction de deux colonnes heure date, joindre sur la partie de date uniquement.  
  
 relyOnReferentialIntegrity  
 N’est pas utilisé ; réservé à un usage ultérieur.  
  
 propriété securityFilteringBehavior  
 Énumération qui indique comment les relations influencent le filtrage des données lors de l’évaluation des expressions de la sécurité de niveau ligne. Les valeurs valides sont les suivantes :  
  
-   OneDirection (1) : les lignes sélectionnées dans la terminaison « To » de la relation filtrent automatiquement les analyses de la table dans la terminaison « From » de la relation.  
  
-   BothDirections (2) - filtres sur des extrémités de la relation filtrent automatiquement l’autre table.  
  
## <a name="usage"></a>Utilisation  
 Les objets de relation sont utilisés dans [Alter commande &#40; TMSL &#41; ](../../analysis-services/tabular-models-scripting-language-commands/alter-command-tmsl.md), [Créer commande &#40; TMSL &#41; ](../../analysis-services/tabular-models-scripting-language-commands/create-command-tmsl.md), [CreateOrReplace commande &#40; TMSL &#41; ](../../analysis-services/tabular-models-scripting-language-commands/createorreplace-command-tmsl.md), et [supprimer commande &#40; TMSL &#41; ](../../analysis-services/tabular-models-scripting-language-commands/delete-command-tmsl.md).  
  
 Lors de la création, du remplacement ou de modification d’un objet de relation, spécifiez toutes les propriétés en lecture-écriture de la définition d’objet. L’omission d’une propriété en lecture-écriture est considérée comme une suppression.  
  
## <a name="full-syntax"></a>Syntaxe complète  
 Voici la représentation sous forme de schéma d’un objet de relation.  
  
```  
"relationships": {  
          "type": "array",  
          "items": {  
            "anyOf": [  
              {  
                "description": "SingleColumnRelationship object of Tabular Object Model (TOM)",  
                "type": "object",  
                "properties": {  
                  "name": {  
                    "type": "string"  
                  },  
                  "isActive": {  
                    "type": "boolean"  
                  },  
                  "type": {  
                    "enum": [  
                      "singleColumn"  
                    ]  
                  },  
                  "crossFilteringBehavior": {  
                    "enum": [  
                      "oneDirection",  
                      "bothDirections",  
                      "automatic"  
                    ]  
                  },  
                  "joinOnDateBehavior": {  
                    "enum": [  
                      "dateAndTime",  
                      "datePartOnly"  
                    ]  
                  },  
                  "relyOnReferentialIntegrity": {  
                    "type": "boolean"  
                  },  
                  "securityFilteringBehavior": {  
                    "enum": [  
                      "oneDirection",  
                      "bothDirections"  
                    ]  
                  },  
                  "fromCardinality": {  
                    "enum": [  
                      "none",  
                      "one",  
                      "many"  
                    ]  
                  },  
                  "toCardinality": {  
                    "enum": [  
                      "none",  
                      "one",  
                      "many"  
                    ]  
                  },  
                  "fromColumn": {  
                    "type": "string"  
                  },  
                  "fromTable": {  
                    "type": "string"  
                  },  
                  "toColumn": {  
                    "type": "string"  
                  },  
                  "toTable": {  
                    "type": "string"  
                  },  
                  "annotations": {  
                    "type": "array",  
                    "items": {  
                      "description": "Annotation object of Tabular Object Model (TOM)",  
                      "type": "object",  
                      "properties": {  
                        "name": {  
                          "type": "string"  
                        },  
                        "value": {  
                          "anyOf": [  
                            {  
                              "type": "string"  
                            },  
                            {  
                              "type": "array",  
                              "items": {  
                                "type": "string"  
                              }  
                            }  
                          ]  
                        }  
                      },  
                      "additionalProperties": false  
                    }  
                  }  
                },  
                "additionalProperties": false  
              }  
            ]  
          }  
        }  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Tabular Model Scripting Language &#40;TMSL&#41; Reference [Informations de référence sur TMSL &#40;Tabular Model Scripting Language&#41;]](../../analysis-services/tabular-model-scripting-language-tmsl-reference.md)   
 [Créer des relations](../../integration-services/data-flow/transformations/create-relationships.md)  
  
  
