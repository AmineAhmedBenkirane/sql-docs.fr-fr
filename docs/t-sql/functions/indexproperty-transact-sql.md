---
title: INDEXPROPERTY (Transact-SQL) | Documents Microsoft
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- INDEXPROPERTY
- INDEXPROPERTY_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- INDEXPROPERTY function
- indexes [SQL Server], viewing
- indexes [SQL Server], properties
ms.assetid: 998d5788-4871-44a8-8125-0d9390868b84
caps.latest.revision: 56
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: cbd10b32ee6b2d88a97222c3a970452a4a628b83
ms.contentlocale: fr-fr
ms.lasthandoff: 09/01/2017

---
# <a name="indexproperty-transact-sql"></a>INDEXPROPERTY (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Retourne la valeur de la propriété de l'index ou des statistiques nommés en fonction d'un numéro d'identification de table, d'un nom d'index ou de statistiques et d'un nom de propriété spécifiés. Retourne la valeur NULL pour les index XML.  
  
 ![Icône de lien de rubrique](../../database-engine/configure-windows/media/topic-link.gif "Icône lien de rubrique") [Conventions de la syntaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
INDEXPROPERTY ( object_ID , index_or_statistics_name , property )   
```  
  
## <a name="arguments"></a>Arguments  
 *object_ID*  
 Expression qui contient le numéro d'identification d'objet de la table ou de la vue indexée dont les informations de propriété d'index doivent être fournies. *object_ID* est **int**.  
  
 *index_or_statistics_name*  
 Expression qui contient le nom de l'index ou des statistiques dont les informations de propriété doivent être retournées. *index_or_statistics_name* est **nvarchar (128)**.  
  
 *propriété*  
 Expression contenant le nom de la propriété de base de données à renvoyer. *propriété* est **varchar (128)**, et peut prendre l’une des valeurs suivantes.  
  
> [!NOTE]  
>  Sauf indication contraire, NULL est retourné lorsque *propriété* n’est pas un nom de propriété valide, *object_ID* n’est pas un ID d’objet valide, *object_ID* est un type d’objet non pris en charge pour la propriété spécifiée, ou l’appelant n’a pas l’autorisation d’afficher les métadonnées de l’objet.  
  
|Propriété| Description|Valeur|  
|--------------|-----------------|-----------|  
|**IndexDepth**|Profondeur de l'index|Nombre de niveaux d'index.<br /><br /> NULL = une entrée ou un index XML n'est pas valide.|  
|**IndexFillFactor**|Valeur de facteur de remplissage utilisée lors de la création et de la dernière restauration de l'index.|Facteur de remplissage|  
|**IndexID**|Identificateur d'index sur une table ou une vue indexée spécifiée|ID de l'index|  
|**IsAutoStatistics**|Les statistiques ont été générées par l'option AUTO_CREATE_STATISTICS de ALTER DATABASE.|1 = True<br /><br /> 0 = False ou index XML.|  
|**IsClustered**|Index est ordonné en clusters.|1 = True<br /><br /> 0 = False ou index XML.|  
|**IsDisabled**|L'index est désactivé.|1 = True<br /><br /> 0 = False<br /><br /> NULL = Entrée non valide.|  
|**IsFulltextKey**|L'index est la clé d'indexation sémantique et de texte intégral pour une table.|**S'applique à**: [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] et [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> 1 = True<br /><br /> 0 = False ou index XML.<br /><br /> NULL = Entrée non valide.|  
|**IsHypothetical**|L'index est hypothétique et ne peut être utilisé directement comme un chemin d'accès aux données. Les index hypothétiques conservent des statistiques au niveau des colonnes et sont gérés et utilisés par l'Assistant Paramétrage du moteur de base de données.|1 = True<br /><br /> 0 = False ou index XML<br /><br /> NULL = Entrée non valide.|  
|**IsPadIndex**|L'index spécifie l'espace à laisser ouvert sur chaque nœud intérieur.|**S'applique à**: [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] et [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> 1 = True<br /><br /> 0 = False ou index XML.|  
|**IsPageLockDisallowed**|Valeur de verrouillage de page définie par l'option ALLOW_PAGE_LOCKS de ALTER INDEX.|**S'applique à**: [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] et [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> 1 = le verrouillage des pages n'est pas autorisé.<br /><br /> 0 = le verrouillage des pages est autorisé.<br /><br /> NULL = Entrée non valide.|  
|**IsRowLockDisallowed**|Valeur de verrouillage de ligne définie par l'option ALLOW_ROW_LOCKS de ALTER INDEX.|**S'applique à**: [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] et [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> 1 = le verrouillage des lignes n'est pas autorisé.<br /><br /> 0 = le verrouillage des lignes est autorisé.<br /><br /> NULL = Entrée non valide.|  
|**IsStatistics**|*index_or_statistics_name* est statistiques créées par l’instruction CREATE STATISTICS ou par l’option AUTO_CREATE_STATISTICS de ALTER DATABASE.|1 = True<br /><br /> 0 = False ou index XML.|  
|**IsUnique**|L'index est unique.|1 = True<br /><br /> 0 = False ou index XML.|  
|**IsColumnstore**|L'index est un index columnstore optimisé en mémoire xVelocity.|**S'applique à**: [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] et [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> 1 = True<br /><br /> 0 = False|  
  
## <a name="return-types"></a>Types de retour  
 **int**  
  
## <a name="exceptions"></a>Exceptions  
 Retourne la valeur NULL en cas d'erreur ou si un appelant n'est pas autorisé à afficher l'objet.  
  
 Un utilisateur peut voir uniquement les métadonnées des éléments sécurisables qui lui appartiennent ou pour lesquels il dispose d'une autorisation. Cela signifie que les fonctions intégrées générant des métadonnées, telles que INDEXPROPERTY, peuvent retourner la valeur NULL si l'utilisateur ne dispose d'aucune autorisation sur l'objet. Pour plus d'informations, consultez [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="examples"></a>Exemples  
 L’exemple suivant retourne les valeurs pour le **IsClustered**, **IndexDepth**, et **IndexFillFactor** propriétés pour le `PK`_`Employee` \_ `BusinessEntityID` index de la `Employee` de table dans le [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] base de données.  
  
```  
SELECT   
    INDEXPROPERTY(OBJECT_ID('HumanResources.Employee'),  
        'PK_Employee_BusinessEntityID','IsClustered')AS [Is Clustered],  
    INDEXPROPERTY(OBJECT_ID('HumanResources.Employee'),  
        'PK_Employee_BusinessEntityID','IndexDepth') AS [Index Depth],  
    INDEXPROPERTY(OBJECT_ID('HumanResources.Employee'),  
        'PK_Employee_BusinessEntityID','IndexFillFactor') AS [Fill Factor];  
  
```  
  
 Voici l'ensemble de résultats obtenu :  
  
```  
Is Clustered Index Depth Fill Factor   
------------ ----------- -----------   
1            2           0  
  
(1 row(s) affected)  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Exemples : [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] et[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 L’exemple suivant examine les propriétés de l’un des index sur la `FactResellerSales` table.  
  
```  
-- Uses AdventureWorks  
  
SELECT   
INDEXPROPERTY(OBJECT_ID('dbo.FactResellerSales'),  
    'ClusteredIndex_6d10fa223e5e4c1fbba087e29e16a7a2','IsClustered') AS [Is Clustered],  
INDEXPROPERTY(OBJECT_ID('dbo.FactResellerSales'),  
    'ClusteredIndex_6d10fa223e5e4c1fbba087e29e16a7a2','IsColumnstore') AS [Is Columnstore Index],  
INDEXPROPERTY(OBJECT_ID('dbo.FactResellerSales'),  
    'ClusteredIndex_6d10fa223e5e4c1fbba087e29e16a7a2','IndexFillFactor') AS [Fill Factor];  
GO  
```  
  
## <a name="see-also"></a>Voir aussi  
 [CREATE INDEX &#40;Transact-SQL&#41;](../../t-sql/statements/create-index-transact-sql.md)   
 [Statistiques](../../relational-databases/statistics/statistics.md)   
 [sys.indexes &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-indexes-transact-sql.md)   
 [sys.index_columns &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-index-columns-transact-sql.md)   
 [sys.stats &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-stats-transact-sql.md)   
 [Sys.stats_columns &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-stats-columns-transact-sql.md)  
  
  


