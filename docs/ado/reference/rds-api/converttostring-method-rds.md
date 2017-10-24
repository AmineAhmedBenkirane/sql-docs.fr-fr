---
title: "ConvertToString, méthode (RDS) | Documents Microsoft"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
helpviewer_keywords:
- ConvertToString method [ADO]
ms.assetid: b3f36bc8-6f69-49b0-83cd-2ccd3afebfbe
caps.latest.revision: 16
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: b910522edc20c73164d03fd5f7f313c1eaffabd7
ms.contentlocale: fr-fr
ms.lasthandoff: 09/09/2017

---
# <a name="converttostring-method-rds"></a>ConvertToString, méthode (RDS)
Convertit un [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) en chaîne MIME qui représente les données du jeu d’enregistrements.  
  
> [!IMPORTANT]
>  À compter de Windows 8 et Windows Server 2012, les composants de serveur Services Bureau à distance ne sont plus inclus dans le système d’exploitation Windows (consultez Windows 8 et [Cookbook de compatibilité de Windows Server 2012](https://www.microsoft.com/en-us/download/details.aspx?id=27416) pour plus de détails). Composants du client Bureau à distance seront supprimées dans une future version de Windows. Évitez d'utiliser cette fonctionnalité dans de nouveaux travaux de développement, et prévoyez de modifier les applications qui utilisent actuellement cette fonctionnalité. La migration vers les applications qui utilisent des services Bureau à distance [Service de données WCF](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
DataFactory.ConvertToString(Recordset)  
```  
  
#### <a name="parameters"></a>Paramètres  
 *DataFactory*  
 Une variable objet qui représente un [RDSServer.DataFactory](../../../ado/reference/rds-api/datafactory-object-rdsserver.md) objet.  
  
 *Jeu d’enregistrements*  
 Une variable objet qui représente un **Recordset** objet.  
  
## <a name="remarks"></a>Notes  
 Avec des fichiers .asp, utilisez **ConvertToString** pour incorporer le **Recordset** dans une page HTML générée sur le serveur pour le transfert vers un ordinateur client.  
  
 **ConvertToString** du premier chargement de la **Recordset** dans le Service de curseur des tables, puis génère un flux au format MIME.  
  
 Sur le client, Service de données distant peut reconvertir la chaîne MIME entièrement fonctionnel **Recordset**. Elle fonctionne bien pour gérer moins de 400 lignes de données avec pas plus de largeur de 1 024 octets par ligne. Vous ne devez pas l’utiliser pour la diffusion en continu des données BLOB et des jeux de résultats volumineux via HTTP. Aucune compression simultanée n’est effectuée sur la chaîne de très grands jeux de données prendra beaucoup de temps au transport sur HTTP, par rapport au format optimisées sur le câble de tablegram définis et déployés par le Service de données distant en tant que son format de protocole de transport natifs.  
  
> [!NOTE]
>  Si vous utilisez Active Server Pages pour incorporer la chaîne MIME résultante dans une page HTML cliente, sachez que les versions de VBScript antérieures à 2.0 limitent la taille de la chaîne à 32 Ko. Si cette limite est dépassée, une erreur est retournée. Limitez l’étendue de requête relativement lors de l’utilisation de l’incorporation de MIME via des fichiers .asp. Pour résoudre ce problème, téléchargez la dernière version de VBScript à partir du site Web Microsoft Windows Script Technologies.  
  
## <a name="applies-to"></a>S'applique à  
 [DataFactory, objet (RDSServer)](../../../ado/reference/rds-api/datafactory-object-rdsserver.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple de méthode ConvertToString (VB)](../../../ado/reference/ado-api/converttostring-method-example-vb.md)   
 [Exemple de méthode ConvertToString (VBScript)](../../../ado/reference/rds-api/converttostring-method-example-vbscript.md)



