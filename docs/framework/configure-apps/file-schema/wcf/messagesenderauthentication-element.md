---
title: <messageSenderAuthentication> (élément)
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 63b6e62b55759c47a7b453b3db7d91e0bc430b2d
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758753"
---
# <a name="messagesenderauthentication-element"></a>\<messageSenderAuthentication > élément
Spécifie les options d'authentification pour les expéditeurs du message du réseau pair à pair.  
  
 Pour plus d’informations sur la programmation de peer-to-peer, consultez [mise en réseau Peer-to-Peer](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<clientCredentials>  
\<peer>  
\<messageSenderAuthentication>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a>Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### <a name="attributes"></a>Attributs  
  
|Attribut|Description|  
|---------------|-----------------|  
|customCertificateValidatorType|Type et assembly utilisés pour valider un type personnalisé. Cet attribut doit être défini lorsque `certificateValidationMode` a la valeur `Custom`.|  
|certifcateValidationMode|Spécifie l'un de trois modes utilisés pour valider des informations d'identification. S'il est défini à `Custom`, un `customCertificateValidator` doit également être fourni.|  
|revocationMode|Un des modes utilisés pour vérifier des listes de certificat révoqués (CRL).|  
|trustedStoreLocation|L'un des deux emplacements du magasin du système : `LocalMachine` ou `CurrentUser`. Cette valeur est utilisée lorsqu'un certificat de service est négocié au client. La validation est effectuée sur le **personnes** stocker dans l’emplacement de magasin spécifié.|  
  
## <a name="customcertificatevalidatortype-attribute"></a>customCertificateValidatorType, attribut  
  
|Valeur|Description|  
|-----------|-----------------|  
|Chaîne|Facultatif. Spécifie le nom de type, l'assembly et d'autres données utilisées pour rechercher le type. Au minimum, un espace de noms et un nom de type sont requis. Les informations facultatives incluent : le nom de l'assembly, le numéro de version, la culture et le jeton de clé publique.|  
  
## <a name="certificatevalidationmode-attribute"></a>certificateValidationMode, attribut  
  
|Valeur|Description|  
|-----------|-----------------|  
|Énumération|Facultatif. Une des valeurs suivantes : `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust` et `Custom`. La valeur par défaut est `ChainTrust`. La valeur par défaut est `ChainTrust`.<br /><br /> Pour plus d’informations, consultez [utilisation des certificats](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## <a name="revocationmode-attribute"></a>revocationMode, attribut  
  
|Valeur|Description|  
|-----------|-----------------|  
|Énumération|Une des valeurs suivantes : `NoCheck`, `Online` et `Offline`. La valeur par défaut est `Online`.<br /><br /> Pour plus d’informations, consultez [utilisation des certificats](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## <a name="trustedstorelocation-attribute"></a>trustedStoreLocation, attribut  
  
|Valeur|Description|  
|-----------|-----------------|  
|Énumération|Une des valeurs suivantes : `LocalMachine` ou `CurrentUser`. La valeur par défaut est `CurrentUser`. Si l'application cliente s'exécute sous un compte système, le certificat se trouve généralement dans `LocalMachine`. Si l'application cliente s'exécute sous un compte d'utilisateur, le certificat se trouve généralement dans `CurrentUser`. La valeur par défaut est `CurrentUser`.|  
  
### <a name="child-elements"></a>Éléments enfants  
 Aucun.  
  
### <a name="parent-elements"></a>Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|[\<peer>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|Spécifie une information d'identification utilisée pour authentifier le client auprès d'un service homologue.|  
  
## <a name="remarks"></a>Notes  
 Cet élément doit être configuré si l'authentification des messages est sélectionnée. Pour les canaux de sortie, chaque message est signé à l’aide du certificat fourni par [ \<certificat >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md). Avant d'être remis à l'application, tous les messages sont vérifiés par rapport aux informations d'identification de message à l'aide du validateur spécifié par l'attribut `customCertificateValidatorType` de cet élément. Le validateur peut accepter ou rejeter les informations d'identification.  
  
## <a name="example"></a>Exemple  
 Les jeux de codes suivants affectent le mode de validation de l’expéditeur du message à `PeerOrChainTrust`.  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <messageSenderAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a>Voir aussi
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [Utilisation des certificats](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Réseaux homologues](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [Authentification de Message de canal homologue](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [Authentification personnalisée de canal homologue](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [Sécurisation des applications de canal homologue](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
