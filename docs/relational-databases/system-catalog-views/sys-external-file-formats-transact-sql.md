---
title: sys.external_file_formats (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: a89efb2c-0a3a-4b64-9284-6e93263e29ac
caps.latest.revision: 
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 08318355eebbff784da00fc27303af1abbf17a31
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2018
---
# <a name="sysexternalfileformats-transact-sql"></a>sys.external_file_formats (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2016-xxxx-asdw-pdw-md.md)]

  Contient une ligne pour chaque format de fichier externe dans la base de données actuelle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssSDS](../../includes/sssds-md.md)], et [!INCLUDE[ssSDW](../../includes/sssdw-md.md)].  
  
 Contient une ligne pour chaque format de fichier externe sur le serveur pour [!INCLUDE[ssPDW](../../includes/sspdw-md.md)].  
  
|Nom de la colonne|Type de données| Description|Plage|  
|-----------------|---------------|-----------------|-----------|  
|file_format_id|**int**|ID d’objet pour le format de fichier externe.||  
|name|**sysname**|Nom du format de fichier. dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et [!INCLUDE[ssSDW](../../includes/sssdw-md.md)], il est unique pour la base de données. Dans [!INCLUDE[ssPDW](../../includes/sspdw-md.md)], il est unique pour le serveur.||  
|format_type|**tinyint**|Le type de format de fichier.|DELIMITEDTEXT, RCFILE, ORC, PARQUET|  
|field_terminator|**nvarchar(10)**|Pour format_type = DELIMITEDTEXT, il s’agit de la marque de fin de champ.||  
|string_delimiter|**nvarchar(10)**|Pour format_type = DELIMITEDTEXT, c’est le délimiteur de chaîne.||  
|date_format|**nvarchar(50)**|Pour format_type = DELIMITEDTEXT, c’est la date défini par l’utilisateur et le format d’heure.||  
|use_type_default|**bit**|Pour format_type = texte délimité, spécifie comment gérer les valeurs manquantes lorsque PolyBase est l’importation de données à partir de fichiers texte HDFS [!INCLUDE[ssSDW](../../includes/sssdw-md.md)].|0 – stocker des valeurs manquantes en tant que la chaîne « NULL ».<br /><br /> 1 – stocker les valeurs manquantes en tant que valeur par défaut de la colonne.|  
|serde_method|**nvarchar(255)**|Pour format_type = RCFILE, c’est la méthode de sérialisation/désérialisation.||  
|row_terminator|**nvarchar(10)**|Pour format_type = DELIMITEDTEXT, c’est la chaîne de caractères qui arrête chaque ligne dans le fichier Hadoop externe.|Toujours '\n'.|  
|encodage|**nvarchar(10)**|Pour format_type = DELIMITEDTEXT, c’est la méthode de codage du fichier Hadoop externe.|Toujours « UTF-8'.|  
|data_compression|**nvarchar(255)**|La méthode de compression de données pour les données externes.|Pour format_type = DELIMITEDTEXT :<br /><br /> -   'org.apache.hadoop.io.compress.DefaultCodec'<br />-   'org.apache.hadoop.io.compress.GzipCodec'<br /><br /> Pour format_type = RCFILE :<br /><br /> -   'org.apache.hadoop.io.compress.DefaultCodec'<br /><br /> Pour format_type = ORC :<br /><br /> -   'org.apache.hadoop.io.compress.DefaultCodec'<br />-   'org.apache.hadoop.io.compress.SnappyCodec'<br /><br /> Pour format_type = PARQUET :<br /><br /> -   'org.apache.hadoop.io.compress.GzipCodec'<br />-   'org.apache.hadoop.io.compress.SnappyCodec'|  
  
## <a name="permissions"></a>Autorisations  
 La visibilité des métadonnées dans les affichages catalogue est limitée aux éléments sécurisables qu'un utilisateur détient ou pour lesquels des autorisations lui ont été accordées. Pour plus d'informations, consultez [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Voir aussi  
 [sys.external_data_sources &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-external-data-sources-transact-sql.md)   
 [sys.external_tables &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-external-tables-transact-sql.md)   
 [CREATE EXTERNAL FILE FORMAT &#40;Transact-SQL&#41;](../../t-sql/statements/create-external-file-format-transact-sql.md)  
  
  
