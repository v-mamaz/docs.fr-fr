---
title: Utilisation d’Azure Key Vault pour protéger les secrets au moment de la production
description: Sécurité dans les microservices .NET et les applications web - Azure Key Vault est un excellent moyen de gérer les secrets d’application qui sont entièrement contrôlés par les administrateurs. Les administrateurs peuvent même affecter et révoquer des valeurs de développement sans que les développeurs aient à les gérer.
author: mjrousos
ms.author: wiwagn
ms.date: 10/19/2018
ms.openlocfilehash: 291d60f941e4280ff120296ce1c392df3300dc44
ms.sourcegitcommit: 542aa405b295955eb055765f33723cb8b588d0d0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362417"
---
# <a name="use-azure-key-vault-to-protect-secrets-at-production-time"></a>Utiliser Azure Key Vault pour protéger les secrets au moment de la production

Les secrets stockés comme variables d’environnement ou au moyen de l’outil Secret Manager sont toujours stockés localement sur l’ordinateur et non chiffrés. [Azure Key Vault](https://azure.microsoft.com/services/key-vault/) constitue une option de stockage des secrets plus sûre, offrant un emplacement centralisé et sécurisé pour le stockage des clés et des secrets.

Le package **Microsoft.Extensions.Configuration.AzureKeyVault** permet à une application ASP.NET Core de lire des informations de configuration à partir d’Azure Key Vault. Pour commencer à utiliser des secrets à partir d’Azure Key Valut, procédez comme suit :

1. Inscrivez votre application en tant qu’application Azure AD. (L’accès aux coffres de clés est géré par Azure AD.) Vous pouvez faire cela dans le portail de gestion Azure.\

   Si vous préférez que votre application s’authentifie avec un certificat plutôt qu’un mot de passe ou une clé secrète client, vous pouvez utiliser l’applet de commande PowerShell [New-AzureRmADApplication](/powershell/module/azurerm.resources/new-azurermadapplication). Le certificat que vous inscrivez auprès d’Azure Key Vault n’a besoin que de votre clé publique. (Votre application utilisera la clé privée.)

2. Accordez à l’application inscrite un accès au coffre de clés en créant un principal de service. Pour cela, vous pouvez utiliser les commandes PowerShell suivantes :

   ```powershell
   $sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
   Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
   ```

3. Ajoutez le coffre de clés comme source de configuration dans votre application en appelant la méthode d’extension <xref:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault%2A?displayProperty=nameWithType> quand vous créez une instance <xref:Microsoft.Extensions.Configuration.IConfigurationRoot>. Notez que l’appel d’`AddAzureKeyVault` nécessite l’ID de l’application qui a été inscrite et qui a obtenu l’accès au coffre de clés aux étapes précédentes.

   Vous pouvez également utiliser une surcharge de `AddAzureKeyVault` qui accepte un certificat à la place de la clé secrète client en incluant simplement une référence au package [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory).

> [!IMPORTANT]
> Nous vous recommandons d’inscrire Azure Key Vault en tant que dernier fournisseur de configuration, afin qu’il puisse remplacer les valeurs de configuration des fournisseurs précédents.

## <a name="additional-resources"></a>Ressources supplémentaires

- **Utilisation d’Azure Key Vault pour protéger les secrets d’application** \
  [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](/azure/guidance/guidance-multitenant-identity-keyvault)

- **Stockage sécurisé des secrets d’application en cours de développement** \
  [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](/aspnet/core/security/app-secrets)

- **Configuration de la protection des données** \
  [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](/aspnet/core/security/data-protection/configuration/overview)

- **Gestion et durée de vie des clés** \
  [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)

- Dépôt GitHub **Microsoft.Extensions.Configuration.KeyPerFile**. \
  [*https://github.com/aspnet/Configuration/tree/master/src/Config.KeyPerFile*](https://github.com/aspnet/Configuration/tree/master/src/Config.KeyPerFile)

>[!div class="step-by-step"]
>[Précédent](developer-app-secrets-storage.md)
>[Suivant](../key-takeaways.md)
