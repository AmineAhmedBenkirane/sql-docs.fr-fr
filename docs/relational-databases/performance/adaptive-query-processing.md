---
title: "Traitement de requêtes adaptatif dans les bases de données Microsoft SQL | Microsoft Docs | Microsoft Docs"
description: "Fonctionnalités de traitement de requêtes adaptatif pour améliorer les performances des requêtes dans SQL Server (2017 et versions ultérieures) et Azure SQL Database."
ms.custom: 
ms.date: 06/22/2017
ms.prod: sql-server-2017
ms.reviewer: 
ms.suite: 
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: 
ms.assetid: 
author: joesackmsft
ms.author: josack;monicar
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: fe6de2b16b9792a5399b1c014af72a2a5ee52377
ms.openlocfilehash: fdade5bce38348e80085643c5f6f5a2b4e9663c1
ms.contentlocale: fr-fr
ms.lasthandoff: 06/22/2017

---

# Traitement de requêtes adaptatif dans les bases de données SQL
<a id="adaptive-query-processing-in-sql-databases" class="xliff"></a>

[!INCLUDE[tsql-appliesto-ss2017-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2017-asdb-xxxx-xxx-md.md)]

Cet article décrit les fonctionnalités de traitement de requêtes adaptatif que vous pouvez utiliser pour améliorer les performances des requêtes dans SQL Server et Azure SQL Database :
- Retour d’allocation de mémoire en mode batch.
- Jointure adaptative en mode batch.
- Exécution entrelacée. 

Au niveau général, SQL Server exécute une requête de la façon suivante :
1. Le processus d’optimisation des requêtes génère un ensemble de plans d’exécution possibles pour une requête spécifique. Pendant ce temps, le coût des options de plan est estimé et le plan dont le coût estimé est le plus faible est utilisé.
1. Le processus d’exécution des requêtes prend le plan choisi par l’optimiseur de requête et l’utilise pour l’exécution.
    
Parfois, le plan choisi par l’optimiseur de requête n’est pas optimal pour diverses raisons. Par exemple, le nombre estimé de lignes dans le flux du plan de requête peut être incorrect. Les coûts estimés permettent de déterminer le plan à utiliser dans l’exécution. Si les estimations de cardinalité sont incorrectes, le plan d’origine est quand même utilisé malgré les mauvaises hypothèses de départ.

![Fonctionnalités de traitement de requêtes adaptatif](./media/1_AQPFeatures.png)

### Comment activer le traitement de requêtes adaptatif
<a id="how-to-enable-adaptive-query-processing" class="xliff"></a>
Vous pouvez faire en sorte que les charges de travail soient automatiquement éligibles au traitement de requêtes adaptatif en activant le niveau de compatibilité 140 pour la base de données.  Vous pouvez définir cette option à l’aide de Transact-SQL. Exemple :
```sql
ALTER DATABASE [WideWorldImportersDW] SET COMPATIBILITY_LEVEL = 140;
```
## Retour d’allocation de mémoire en mode batch
<a id="batch-mode-memory-grant-feedback" class="xliff"></a>
Le plan post-exécution d’une requête dans SQL Server inclut la quantité minimale de mémoire nécessaire pour l’exécution et la taille d’allocation de mémoire idéale pour que toutes les lignes tiennent dans la mémoire. Les performances sont réduites quand les tailles d’allocation de mémoire ne sont pas dimensionnées correctement. Si l’allocation de mémoire est excessive, une certaine quantité de mémoire est inutilisée et l’accès concurrentiel est réduit. Si l’allocation de mémoire est insuffisante, il en résulte des dépassements de capacité coûteux sur le disque. En apportant une solution à la répétition des charges de travail, le retour d’allocation de mémoire en mode batch recalcule la quantité de mémoire réelle nécessaire pour une requête et met à jour la valeur d’allocation pour le plan mis en cache.  Quand une instruction de requête identique est exécutée, la requête utilise la taille d’allocation de mémoire révisée, ce qui permet de réduire les allocations de mémoire excessives qui impactent l’accès concurrentiel et de corriger les allocations de mémoire sous-estimées qui provoquent des dépassements de capacité coûteux sur le disque.
Le graphe suivant montre un exemple d’utilisation du retour d’allocation de mémoire adaptative en mode batch. Pour la première exécution de la requête, la durée était de *88 secondes* en raison de dépassements de capacité importants :
```sql
DECLARE @EndTime datetime = '2016-09-22 00:00:00.000';
DECLARE @StartTime datetime = '2016-09-15 00:00:00.000';
SELECT TOP 10 hash_unique_bigint_id
FROM dbo.TelemetryDS
WHERE Timestamp BETWEEN @StartTime and @EndTime
GROUP BY hash_unique_bigint_id
ORDER BY MAX(max_elapsed_time_microsec) DESC;
```
![Dépassements de capacité importants](./media/2_AQPGraphHighSpills.png)

Si le retour d’allocation de mémoire est activé, pour la deuxième exécution, la durée est de *1 seconde* (au lieu de 88 secondes), les dépassements de capacité sont entièrement supprimés et l’allocation est plus importante : 

![Aucun dépassement de capacité](./media/3_AQPGraphNoSpills.png)

### Dimensionnement du retour d’allocation de mémoire
<a id="memory-grant-feedback-sizing" class="xliff"></a>
*Pour les allocations excessives*, si la mémoire allouée est plus de deux fois supérieure à la taille réelle de la mémoire utilisée, le retour d’allocation de mémoire recalcule l’allocation de mémoire et met à jour le plan mis en cache.  Les plans dont les allocations de mémoire sont inférieures à 1 Mo ne sont pas recalculés par rapport à d’éventuels dépassements.
*Pour les allocations de mémoire dont la taille est insuffisante* et qui entraînent un dépassement de capacité sur le disque pour les opérateurs en mode batch, le retour d’allocation de mémoire déclenche un nouveau calcul de l’allocation de mémoire. Les événements de dépassement de capacité sont signalés au retour d’allocation de mémoire et peuvent être exposés via l’événement XEvent *spilling_report_to_memory_grant_feedback*. Cet événement retourne l’ID de nœud du plan et la taille de données objet du dépassement de capacité de ce nœud.

### Retour d’allocation de mémoire et scénarios sensibles aux paramètres
<a id="memory-grant-feedback-and-parameter-sensitive-scenarios" class="xliff"></a>
Différentes valeurs de paramètre peuvent également nécessiter différents plans de requête pour maintenir une situation optimale. Ce type de requête est défini comme « sensible aux paramètres ». Pour les plans sensibles aux paramètres, le retour d’allocation de mémoire se désactive sur une requête si la mémoire requise est instable.  Le plan est désactivé après plusieurs exécutions répétées de la requête et ce comportement peut être observé en surveillant l’événement XEvent *memory_grant_feedback_loop_disabled* XEvent.

### Mise en cache du retour d’allocation de mémoire
<a id="memory-grant-feedback-caching" class="xliff"></a>
Le retour peut être stocké dans le plan mis en cache pour une seule exécution. Toutefois, ce sont les exécutions consécutives de cette instruction qui bénéficient des ajustements du retour d’allocation de mémoire. Cette fonctionnalité s’applique à l’exécution répétée d’instructions. Le retour d’allocation de mémoire modifie uniquement le plan mis en cache. Les modifications ne sont actuellement pas capturées dans le Magasin des requêtes.
Le retour n’est pas persistant si le plan est supprimé du cache. Le retour est également perdu en cas de basculement. Une instruction qui utilise OPTION(RECOMPILE) crée un plan et ne le met pas en cache. Parce qu’il n’est pas mis en cache, aucun retour d’allocation de mémoire n’est généré, et il n’est pas stocké pour cette compilation et l’exécution.  Toutefois, si une instruction équivalente (autrement dit, avec le même hachage de requête) qui n’utilise *pas* OPTION(RECOMPILE) a été mise en cache, puis réexécutée, l’instruction consécutive peut bénéficier du retour d’allocation de mémoire.

### Suivi de l’activité du retour d’allocation de mémoire
<a id="tracking-memory-grant-feedback-activity" class="xliff"></a>
Vous pouvez suivre les événements du retour d’allocation de mémoire à l’aide de l’événement XEvent *memory_grant_updated_by_feedback*.  Cet événement effectue le suivi de l’historique du nombre d’exécutions actuel, du nombre de fois que le plan a été mis à jour par le retour d’allocation de mémoire, de l’allocation de mémoire supplémentaire idéale avant modification et l’allocation de mémoire supplémentaire idéale après que le retour d’allocation de mémoire a modifié le plan mis en cache.

### Retour d’allocation de mémoire, resource governor et indicateurs de requête
<a id="memory-grant-feedback-resource-governor-and-query-hints" class="xliff"></a>
La mémoire réelle allouée respecte la limite de mémoire de requête déterminée par l’indicateur de requête ou resource governor.

## Jointures adaptatives en mode batch
<a id="batch-mode-adaptive-joins" class="xliff"></a>
La fonctionnalité des jointures adaptatives en mode batch permet de choisir de différer une jointure hachée ou une méthode de jointure de boucles imbriquées *tant que* la première entrée n’a pas été analysée.  L’opérateur de jointure adaptative définit un seuil qui sert à déterminer le moment où il faut basculer vers un plan de boucles imbriquées. Votre plan peut, par conséquent, passer dynamiquement à une meilleure stratégie de jointure pendant l’exécution.
Fonctionnement de l’opération :
- Si le nombre de lignes de l’entrée de jointure de génération est suffisamment petit pour qu’une jointure de boucles imbriquées soit plus optimale qu’une jointure hachée, votre plan bascule sur un algorithme de boucles imbriquées.
- Si l’entrée de jointure de génération dépasse un seuil spécifique de nombre de lignes, aucun basculement ne se produit et votre plan se poursuit avec une jointure hachée.

La requête suivante est utilisée pour illustrer un exemple de jointure adaptative :

```sql
SELECT  [fo].[Order Key], [si].[Lead Time Days],
[fo].[Quantity]
FROM    [Fact].[Order] AS [fo]
INNER JOIN [Dimension].[Stock Item] AS [si]
       ON [fo].[Stock Item Key] = [si].[Stock Item Key]
WHERE   [fo].[Quantity] = 360;
```

Cette requête retourne 336 lignes.  En activant les statistiques des requêtes actives, nous observons le plan suivant :

![Résultat de la requête : 336 lignes](./media/4_AQPStats336Rows.png)

Dans le plan, nous voyons les éléments suivants :
- Nous avons une analyse d’index columnstore utilisée pour fournir des lignes pendant la phase de génération de la jointure hachée.
- Nous avons le nouvel opérateur de jointure adaptative. Cet opérateur définit un seuil qui sert à déterminer le moment où il faut basculer vers un plan de boucles imbriquée.  Dans notre exemple, le seuil est de 78 lignes.  Tout plan avec &gt;= 78 lignes utilise une jointure hachée.  Si le nombre de lignes est inférieur au seuil, une jointure de boucles imbriquées est utilisée.
- Comme dans notre exemple nous obtenons 336 lignes, nous dépassons le seuil et la deuxième branche représente donc la phase de sondage d’une opération de jointure hachée standard. Notez que les statistiques des requêtes actives affichent les lignes qui sont traitées par les opérateurs – dans notre exemple « 672 sur 672 ».
- La dernière branche est notre recherche d’index cluster que doit utiliser la jointure de boucles imbriquées, pour laquelle le seuil n’a pas été dépassé. Notez que nous voyons « 0 sur 336 » lignes affichées (la branche n’est pas utilisée).
 Maintenant nous allons comparer le plan avec la même requête, mais cette fois pour une seule ligne dans la table :
 
```sql
SELECT  [fo].[Order Key], [si].[Lead Time Days],
[fo].[Quantity]
FROM    [Fact].[Order] AS [fo]
INNER JOIN [Dimension].[Stock Item] AS [si]
       ON [fo].[Stock Item Key] = [si].[Stock Item Key]
WHERE   [fo].[Quantity] = 361;
```
La requête retourne une ligne.  En activant les statistiques des requêtes actives, nous observons le plan suivant :

![Résultat de la requête : une ligne](./media/5_AQPStatsOneRow.png)

Dans le plan, nous voyons les éléments suivants :
- Avec une ligne retournée, vous pouvez maintenant voir le flux des lignes dans la recherche d’index cluster.
- En parallèle, comme nous n’avons pas poursuivi la phase de génération de jointure hachée, vous ne voyez aucun flux de lignes pour la deuxième branche.

### Avantages de la jointure adaptative
<a id="adaptive-join-benefits" class="xliff"></a>
Ce sont les charges de travail avec des variations fréquentes entre les grandes et les petites analyses d’entrée de jointure qui bénéficient le plus de cette fonctionnalité.

### Surcharge de jointure adaptative
<a id="adaptive-join-overhead" class="xliff"></a>
Les jointures adaptatives nécessitent davantage de mémoire que les jointures de boucles imbriquées d’index en cas de plan équivalent. La mémoire supplémentaire est demandée comme si la boucle imbriquée était une jointure hachée. Une opération discontinue engendre également une surcharge pendant la phase de génération contrairement à la diffusion d’une boucle imbriquée, en cas de jointure équivalente. Ce coût supplémentaire apporte une certaine flexibilité dans les scénarios où le nombre de lignes peut fluctuer dans l’entrée de génération.

### Mise en cache et réutilisation des jointures adaptatives
<a id="adaptive-join-caching-and-re-use" class="xliff"></a>
Les jointures adaptatives en mode batch fonctionnent pour l’exécution initiale d’une instruction et, une fois compilées, les exécutions consécutives restent adaptatives en fonction du seuil des jointures adaptatives compilées et du flux des lignes de runtime dans la phase de génération de l’entrée externe.

### Suivi de l’activité des jointures adaptatives
<a id="tracking-adaptive-join-activity" class="xliff"></a>
L’opérateur de jointure adaptative a les attributs d’opérateur de plan suivants :

| Attribut de plan |  Description |
|--- |--- |
| AdaptiveThresholdRows | Montre l’utilisation du seuil pour passer d’une jointure hachée à une jointure de boucles imbriquées. |
| EstimatedJoinType | Type de jointure probable. |
| ActualJoinType | Dans un plan réel, indique l’algorithme de jointure qui a finalement été choisi en fonction du seuil. |

Le plan estimé montre la forme du plan de jointure adaptative, ainsi que le seuil de jointure adaptative défini et un type de jointure estimé.

### Interopérabilité des jointures adaptatives et du Magasin des requêtes
<a id="adaptive-join-and-query-store-interoperability" class="xliff"></a>
Le Magasin des requêtes capture un plan de jointure adaptative en mode batch et est capable de forcer son application.

### Instructions éligibles pour la jointure adaptative
<a id="adaptive-join-eligible-statements" class="xliff"></a>
Une jointure logique doit respecter certaines conditions pour être assimilée à une jointure adaptative en mode batch :
- Le niveau de compatibilité de la base de données est 140
- La requête est une instruction SELECT (les instructions de modification des données ne sont actuellement pas éligibles)
- La jointure est éligible pour être exécutée à la fois par une jointure de boucles imbriquées indexées ou par un algorithme physique de jointure hachée
- La jointure hachée utilise le mode batch quand un index columnstore est présent dans la requête globale ou quand la jointure référence directement la table d’index columnstore
- Les solutions alternatives générées de la jointure de boucles imbriquées et de la jointure hachée doivent avoir le même premier enfant (référence externe)

### Efficacité des jointures adaptatives et des boucles imbriquées
<a id="adaptive-joins-and-nested-loop-efficiency" class="xliff"></a>
Si une jointure adaptative bascule sur une opération de boucles imbriquées, elle utilise les lignes déjà lues dans la génération de jointure hachée. L’opérateur ne relit *pas* les lignes de référence externe.

### Lignes du seuil adaptatif
<a id="adaptive-threshold-rows" class="xliff"></a>
Le graphique suivant montre un exemple d’intersection entre le coût d’une jointure hachée et le coût d’une jointure de boucles imbriquées alternative.  À ce point d’intersection, le seuil est déterminé, qui détermine à son tour l’algorithme réel utilisé pour l’opération de jointure.

![Seuil de jointure](./media/6_AQPJoinThreshold.png)

## Exécution entrelacée pour les fonctions table à instructions multiples
<a id="interleaved-execution-for-multi-statement-table-valued-functions" class="xliff"></a>
L’exécution entrelacée change la limite unidirectionnelle entre les phases d’exécution et d’optimisation pour l’exécution d’une seule requête, et permet d’adapter les plans selon les estimations de cardinalité révisées. Pendant l’optimisation, si nous rencontrons un candidat pour l’exécution entrelacée, c’est-à-dire des **fonctions table à instructions multiples (MSTVF)**, nous suspendons l’optimisation, exécutons la sous-arborescence applicable, capturons des estimations de cardinalité précises, puis reprenons l’optimisation pour les opérations en aval.
Les MSTVF ont une estimation de cardinalité fixe égale à 100 dans SQL Server 2014 et SQL Server 2016, et égale à 1 pour les versions antérieures. L’exécution entrelacée entraîne des problèmes de performance des charges de travail qui sont liés à ces estimations de cardinalité fixes associées aux fonctions table à instructions multiples.

L’image suivante illustre une sortie de statistiques de requêtes actives, un sous-ensemble d’un plan d’exécution global qui montre l’impact des estimations de cardinalité fixes des MSTVF. Vous pouvez comparer le flux de lignes réel et les lignes estimées. Il y a trois zones notables dans le plan (le flux va de droite à gauche) :
1. L’analyse de table MSTVF utilise une estimation fixe de 100 lignes. Dans cet exemple, toutefois, l’analyse de table présente un flux de *527 597* lignes, comme indiqué dans les statistiques des requêtes actives par les chiffres « 527597 sur 100 » (nombre réel sur nombre estimé). L’estimation fixe est donc considérablement biaisée.
1. Pour l’opération de boucles imbriquées, seules 100 lignes sont supposées être retournées par le côté extérieur de la jointure. Étant donné le nombre élevé de lignes retournées par la MSTVF, vous avez tout intérêt à utiliser un autre algorithme de jointure.
1. Pour l’opération de correspondance de hachage, notez le petit symbole d’avertissement qui indique dans ce cas un dépassement de capacité sur le disque.

![Flux de lignes par rapport aux lignes estimées](./media/7_AQPFlowThreeAreas.png)

Comparez le plan précédent au plan réel généré avec l’exécution entrelacée :

![Plan entrelacé](./media/8_AQPInterleavedEnabledPlan.png)

1. Notez que l’analyse de table MSTVF reflète maintenant une estimation de cardinalité précise. Notez également la réorganisation de cette analyse de table et des autres opérations.
1. Concernant les algorithmes de jointure, nous sommes passés d’une opération de boucles imbriquées à une opération de correspondance de hachage, qui est plus adaptée étant donné le nombre important de lignes concernées.
1. Notez également que nous n’avons plus d’avertissements de dépassement de capacité, car nous allouons davantage de mémoire en fonction du nombre de lignes réel de l’analyse de table MSTVF.

### Instructions éligibles pour l’exécution entrelacée
<a id="interleaved-execution-eligible-statements" class="xliff"></a>
Les instructions de référence MSTVF dans l’exécution entrelacée doivent être en lecture seule et ne pas faire partie d’une opération de modification de données. Par ailleurs, les MSTVF ne sont pas éligibles pour l’exécution entrelacée si elles sont utilisées à l’intérieur de CROSS APPLY.

### Avantages de l’exécution entrelacée
<a id="interleaved-execution-benefits" class="xliff"></a>
En règle générale, plus le décalage est important entre le nombre de lignes réel et estimé, associé au nombre d’opérations de plan en aval, plus l’impact sur les performances est élevé.
En général, l’exécution entrelacée bénéficie aux requêtes dans les situations suivantes :
1. Il y a un décalage important entre le nombre réel et le nombre estimé de lignes pour le jeu de résultats intermédiaire (dans ce cas, la MSTVF) et...
1. ...la requête globale est sensible à un changement de taille du résultat intermédiaire. Cela se produit généralement quand une arborescence complexe englobe la sous-arborescence dans le plan de requête.
Une simple instruction « SELECT * » d’une MSTVF ne tire aucun bénéfice de l’exécution entrelacée.

### Surcharge de l’exécution entrelacée
<a id="interleaved-execution-overhead" class="xliff"></a>
La surcharge doit être minime, voire nulle. Les MSTVF ont déjà été matérialisées avant l’introduction de l’exécution entrelacée, toutefois, cette fois nous autorisons une optimisation différée et nous tirons parti de l’estimation de cardinalité de l’ensemble des lignes matérialisées.
Comme c’est le cas avec n’importe quel changement affectant le plan, certains plans peuvent changer à un point tel que l’amélioration de la cardinalité de la sous-arborescence entraîne un plan complètement inadapté pour la requête globale. Pour atténuer cet effet, vous pouvez rétablir le niveau de compatibilité ou utiliser le Magasin des requêtes pour forcer l’utilisation de la version non régressée du plan.

### Exécution entrelacée et exécutions consécutives
<a id="interleaved-execution-and-consecutive-executions" class="xliff"></a>
Une fois qu’un plan d’exécution entrelacée est mis en cache, le plan avec les estimations révisées issues de la première exécution est utilisé pour les exécutions consécutives sans nouvelle instanciation de l’exécution entrelacée.

### Suivi de l’activité d’exécution entrelacée
<a id="tracking-interleaved-execution-activity" class="xliff"></a>
Vous pouvez voir les attributs d’utilisation dans le plan d’exécution de requête réel :

| Attribut de plan |  Description |
| --- | --- |
| ContainsInterleavedExecutionCandidates | S’applique au nœud *QueryPlan*, quand la valeur est « true », cela signifie que le plan contient des candidats pour l’exécution entrelacée. |
| IsInterleavedExecuted | L’attribut est à l’intérieur de l’élément RuntimeInformation sous le RelOp pour le nœud TVF. Quand la valeur est « true », cela signifie que l’opération a été matérialisée dans le cadre d’une opération d’exécution entrelacée. |

Vous pouvez également suivre les occurrences d’exécution entrelacée via les événements XEvent suivants :

| XEvent |  Description |
| ---- | --- |
| interleaved_exec_status | Cet événement se déclenche quand l’exécution entrelacée se produit. |
| interleaved_exec_stats_update | Cet événement décrit les estimations de cardinalité mises à jour par l’exécution entrelacée. |
| Interleaved_exec_disabled_reason | Cet événement se déclenche quand une requête avec un candidat possible pour l’exécution entrelacée n’obtient pas l’exécution entrelacée. |

Une requête doit être exécutée pour permettre à l’exécution entrelacée de réviser les estimations de cardinalité MSTVF. Toutefois, le plan d’exécution estimé montre toujours s’il y a des candidats pour l’exécution entrelacée via l’attribut ContainsInterleavedExecutionCandidates.

### Mise en cache de l’exécution entrelacée
<a id="interleaved-execution-caching" class="xliff"></a>
Si un plan est effacé ou supprimé du cache, à l’exécution de la requête c’est une nouvelle compilation qui utilise l’exécution entrelacée.
Une instruction qui utilise OPTION(RECOMPILE) crée un plan à l’aide de l’exécution entrelacée et ne le met pas en cache.

### Interopérabilité de l’exécution entrelacée et du Magasin des requêtes
<a id="interleaved-execution-and-query-store-interoperability" class="xliff"></a>
L’utilisation des plans qui utilisent l’exécution entrelacée peut être forcée. Le plan est la version dont les estimations de cardinalité ont été corrigées en fonction de l’exécution initiale.

Voir aussi [Centre de performances pour le moteur de base de données SQL Server et Azure SQL Database](https://docs.microsoft.com/en-us/sql/relational-databases/performance/performance-center-for-sql-server-database-engine-and-azure-sql-database)



