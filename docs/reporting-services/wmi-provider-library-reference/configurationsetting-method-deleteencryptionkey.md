---
title: "DeleteEncryptionKey, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
apiname: DeleteEncryptionKey (WMI MSReportServer_ConfigurationSetting Class)
apilocation: reportingservices.mof
apitype: MOFDef
helpviewer_keywords: DeleteEncryptionKey method
ms.assetid: ed2f25b6-6a63-468d-9279-a577ca01b096
caps.latest.revision: "20"
author: guyinacube
ms.author: asaxton
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: af4082207a3add7572850672798990a0941035a2
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="configurationsetting-method---deleteencryptionkey"></a>Méthode ConfigurationSetting - DeleteEncryptionKey
  Supprime les clés de chiffrement de la base de données du serveur de rapports.  
  
## <a name="syntax"></a>Syntaxe  
  
```vb  
Public Sub DeleteEncryptionKeys(ByVal InstallationID As String, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void DeleteEncryptionKeys(string InstallationID, out Int32 HRESULT,   
    out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a>Paramètres  
 *InstallationID*  
 ID d'installation d'un serveur de rapports figurant dans la table de clés de la base de données du serveur de rapports.  
  
 *HRESULT*  
 [out] Valeur indiquant si l'appel a réussi ou échoué.  
  
 *ExtendedErrors[]*  
 [out] Tableau de chaînes contenant les erreurs supplémentaires retournées par l'appel.  
  
## <a name="return-value"></a>Valeur retournée  
 Retourne un paramètre HRESULT indiquant si l'appel de la méthode a abouti ou a échoué. Une valeur 0 indique que l'appel de méthode a réussi. Une valeur différente de zéro indique qu'une erreur s'est produite.  
  
## <a name="remarks"></a>Notes  
 La méthode *DeleteEncryptionKey* supprime les entrées de la table de clés pour les serveurs de rapports qui ont accès aux informations sécurisées dans la base de données du serveur de rapports. Si le paramètre *InstallationID* spécifié ne correspond pas à un ID d'installation figurant dans la base de données, la méthode retourne une erreur.  
  
## <a name="requirements"></a>Spécifications  
 **Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Membres MSReportServer_ConfigurationSetting](../../reporting-services/wmi-provider-library-reference/msreportserver-configurationsetting-members.md)  
  
  
