---
title: Protection des informations de connexion
ms.date: 03/30/2017
ms.assetid: 1471f580-bcd4-4046-bdaf-d2541ecda2f4
ms.openlocfilehash: 4c8992abc30690be8e9ef9c208b0a0bd3ddf6116
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56091953"
---
# <a name="protecting-connection-information"></a>Protection des informations de connexion
La protection de l'accès à votre source de données représente l'un de vos principaux objectifs lorsque vous sécurisez une application. Une chaîne de connexion présente une vulnérabilité potentielle si elle n'est pas sécurisée. Le stockage d'informations de connexion au format texte brut ou sa conservation dans la mémoire risque de compromettre l'ensemble de votre système. Chaînes de connexion incorporées dans votre code source peuvent être lu à l’aide de la [Ildasm.exe (désassembleur IL)](../../../../docs/framework/tools/ildasm-exe-il-disassembler.md) pour afficher le langage intermédiaire Microsoft (MSIL) dans un assembly compilé.  
  
 Des vulnérabilités de sécurité impliquant des chaînes de connexion peuvent se produire en fonction du type d'authentification utilisé, de la manière dont les chaînes de connexion sont conservées dans la mémoire et sur le disque, et des techniques utilisées pour les construire au moment de l'exécution.  
  
## <a name="use-windows-authentication"></a>Utiliser l'authentification Windows  
 Pour aider à limiter l'accès à votre source de données, vous devez sécuriser des informations de connexion telles que l'ID utilisateur, le mot de passe et le nom de source de données. Afin d’éviter l’exposition d’informations utilisateur, nous recommandons d’utiliser l’authentification Windows (parfois appelé *sécurité intégrée*) autant que possible. L'authentification Windows est spécifiée dans une chaîne de connexion à l'aide des mots clés `Integrated Security` ou `Trusted_Connection`, ce qui supprime le recours à un ID utilisateur et à un mot de passe. Lors de l'utilisation de l'authentification Windows, les utilisateurs sont authentifiés par Windows et l'accès aux ressources de serveur et de base de données est déterminé en octroyant des autorisations aux utilisateurs et aux groupes Windows.  
  
 Dans les cas où l'utilisation de l'authentification Windows n'est pas possible, vous devez être extrêmement prudent, car les informations d'authentification utilisateur sont exposées dans la chaîne de connexion. Dans une application ASP.NET, vous pouvez configurer un compte Windows en tant qu'identité fixe utilisée pour la connexion à des bases de données et autres ressources réseau. Vous activez l’emprunt d’identité dans l’élément d’identité dans le **web.config** fichier et spécifiez un nom d’utilisateur et le mot de passe.  
  
```xml  
<identity impersonate="true"   
        userName="MyDomain\UserAccount"   
        password="*****" />  
```  
  
 Le compte d'identité fixe doit être un compte avec des privilèges faibles auquel seules les autorisations nécessaires dans la base de données ont été octroyées. En outre, vous devez chiffrer le fichier de configuration afin que le nom d'utilisateur et le mot de passe ne soient pas exposés en texte clair.  
  
## <a name="do-not-use-universal-data-link-udl-files"></a>N'utilisez pas de fichiers UDL (Universal Data Link)  
 Évitez de stocker des chaînes de connexion pour <xref:System.Data.OleDb.OleDbConnection> dans un fichier UDL (Universal Data Link). Les fichiers UDL sont stockés en texte clair et ne peuvent pas être chiffrés. Un fichier UDL est une ressource basée sur un fichier externe pour votre application et il ne peut pas être sécurisé ou chiffré à l'aide du .NET Framework.  
  
## <a name="avoid-injection-attacks-with-connection-string-builders"></a>Évitez les attaques par injection à l'aide de générateurs de chaînes de connexion  
 Une attaque par injection de chaîne de connexion peut se produire lorsqu'une concaténation de chaîne dynamique est utilisée pour générer des chaînes de connexion en fonction de l'entrée utilisateur. Si l'entrée utilisateur n'est pas validée et que du texte ou des caractères malveillants ne sont pas placés dans une séquence d'échappement, un attaquant peut éventuellement accéder à des données sensibles ou à d'autres ressources sur le serveur. Pour résoudre ce problème, ADO.NET 2.0 a introduit de nouvelles classes de générateur de chaîne de connexion pour valider la syntaxe de chaîne de connexion et garantir que des paramètres supplémentaires ne sont pas introduits. Pour plus d’informations, consultez [Builders de chaînes de connexion](../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
## <a name="use-persist-security-infofalse"></a>Utilisez Persist Security Info=False  
 La valeur par défaut pour `Persist Security Info` est False ; nous vous recommandons d'utiliser cette valeur par défaut dans toutes les chaînes de connexion. Le paramétrage de `Persist Security Info` avec la valeur `true` ou `yes` permet d'obtenir des informations sensibles pour la sécurité, dont l'ID utilisateur et le mot de passe, à partir d'une connexion une fois celle-ci ouverte. Lorsque `Persist Security Info` possède la valeur `false` ou `no`, les informations de sécurité sont ignorées après leur utilisation pour ouvrir la connexion, ce qui garantit qu'une source qui n'est pas digne de confiance ne dispose pas d'un accès à des informations sensibles sur la sécurité.  
  
## <a name="encrypt-configuration-files"></a>Chiffrez les fichiers de configuration  
 Vous pouvez également stocker des chaînes de connexion dans des fichiers de configuration, ce qui évite d'avoir à les incorporer dans le code de votre application. Les fichiers de configuration sont des fichiers XML standard pour lesquels le .NET Framework a défini un ensemble commun d'éléments. Chaînes de connexion dans les fichiers de configuration sont généralement stockées à l’intérieur de la  **\<connectionStrings >** élément dans le **app.config** pour une application Windows, ou le  **Web.config** fichier pour une application ASP.NET. Pour plus d’informations sur les principes de base du stockage, la récupération et chiffrement des chaînes de connexion à partir des fichiers de configuration, consultez [chaînes de connexion et les fichiers de Configuration](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).  
  
## <a name="see-also"></a>Voir aussi
- [Sécurisation des applications ADO.NET](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [Chiffrement des informations de Configuration à l’aide de la Configuration protégée](https://docs.microsoft.com/previous-versions/aspnet/53tyfkaw(v=vs.100))
- [Sécurité dans .NET](../../../standard/security/index.md)
- [Fournisseurs managés ADO.NET et centre de développement DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
