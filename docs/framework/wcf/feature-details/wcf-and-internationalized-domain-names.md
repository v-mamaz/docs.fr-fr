---
title: WCF et IDN (Internationalized Domain Names)
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: 83c6f3c2afec0f2b6b8fccca4bd8252e9ab35400
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54571585"
---
# <a name="wcf-and-internationalized-domain-names"></a>WCF et IDN (Internationalized Domain Names)
La prise en charge a été ajoutée pour tenir compte des services WCF avec des noms IDN (Internationalized Domain Names). Un nom de domaine international est un nom de domaine qui contient des caractères non ASCII. Cette prise en charge inclut la capacité d'héberger un service WCF avec un nom IDN et un client WCF pour parler à un service Web avec un nom IDN.  
  
## <a name="systemuri-and-idn"></a>System.Uri et IDN  
 <xref:System.Uri> contient deux propriétés : <xref:System.Uri.Host%2A> et <xref:System.Uri.DnsSafeHost%2A>. Ces propriétés contiennent des valeurs Unicode ou Punycode en fonction des paramètres de configuration pour IDN.  
  
 L'IDN est activé dans le fichier de configuration d'une application à l'aide du XML suivant  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 Le \<idn > élément contient l’attribut activé qui peut être définie à une des valeurs suivantes :  
  
1.  « None »  
  
2.  "AllExceptIntranet"  
  
3.  « Tout »  
  
 Lorsque le paramètre IDN a la valeur « None », aucuns conversions ne sont effectuées par Uri.Host ou Uri.DnsSafeHost. Lorsque le paramètre IDN a la valeur « All », uri. Hôte reste Unicode et uri. DnsSafeHost est converti en Punycode. Lorsque le paramètre IDN a la valeur « AllExceptIntranet », les uri. DnsSafeHost est converti en Punycode pour les adresses internet et reste Unicode pour les adresses intranet. Ce paramètre est important pour la résolution de noms DNS correcte. Notez qu'il n'est pas nécessaire de configurer ce paramètres pour Windows 8 et les versions plus récentes.  
  
> [!WARNING]
>  Vous ne devez jamais coder une adresse en dur à l'aide de Punycode. WCF le convertit pour vous en fonction des paramètres de configuration que vous appliquez.  
  
> [!WARNING]
>  Lorsque vous ajoutez des caractères Unicode à applicationHost.exe.config, enregistrez le fichier à l'aide de l'encodage UTF-8.  
  
## <a name="see-also"></a>Voir aussi
- <xref:System.Uri?displayProperty=nameWithType>
