---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: eb5459625cf58feeef5ba29d76e74691a4f87cc8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278419"
---
# <a name="dns"></a>\<dns>
Spécifie l'identité attendue du serveur. Cette identité est valide pour le mode d'authentification du certificat X509 si le certificat du serveur contient un DNS avec la même valeur. Elle est également valide pour le mode d'authentification Windows si le SPN a la même valeur.  
  
 Pour plus d’informations sur la définition de la valeur de l’élément, consultez [identité de Service et d’authentification](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
 \<identity>  
\<dns>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a>Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### <a name="attributes"></a>Attributs  
  
|Attribut|Description|  
|---------------|-----------------|  
|par défaut|Système DNS du certificat. Le système DNS est un protocole standard utilisé pour localiser des ordinateurs sur un réseau IP. Les utilisateurs peuvent se souvenir de noms complets, tels que [ https://go.microsoft.com/fwlink/?prd=10929 ](https://go.microsoft.com/fwlink/?prd=10929) ou [ https://go.microsoft.com/fwlink/?LinkID=96165 ](https://go.microsoft.com/fwlink/?LinkID=96165), il est plus facile que le nombre que des adresses, 207.46.131.137.|  
  
### <a name="child-elements"></a>Éléments enfants  
 Aucun.  
  
### <a name="parent-elements"></a>Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|[\<identity>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Spécifie l'identité du service à authentifier par le client.|  
  
## <a name="example"></a>Exemple  
 Le code de configuration suivant spécifie le système DNS d'un certificat X.509 utilisé pour authentifier un serveur.  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a>Voir aussi
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [Identité du service et authentification](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
