---
title: Portage de code de .NET Framework vers .NET Core
description: Présentation du processus de portage et d’outils qui peuvent s’avérer utiles lors du portage d’un projet .NET Framework vers .NET Core.
author: cartermp
ms.date: 12/07/2018
ms.custom: seodec18
ms.openlocfilehash: 870320c8467237e87a2675ec5cfb57647026d8ec
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55903568"
---
# <a name="port-your-code-from-net-framework-to-net-core"></a>Portage de votre code de .NET Framework vers .NET Core

Si vous avez du code qui s’exécute sur le .NET Framework, vous pouvez également être intéressé par l’exécution de votre code sur .NET Core. Voici une vue d’ensemble du processus de portage et une liste des outils qui peuvent s’avérer utiles lors du portage de votre vers .NET Core.

## <a name="overview-of-the-porting-process"></a>Vue d’ensemble du processus de portage

Il s’agit du processus que nous vous recommandons d’effectuer lors du portage de votre projet vers .NET Core. Chacune de ces étapes du processus est traitée plus en détail dans d’autres articles.

1. Identifiez et considérez vos dépendances tierces.

   Cette étape implique de comprendre ce que sont vos dépendances tierces, comment vous en dépendez, comment faire pour vérifier si elles s’exécutent aussi sur .NET Core, ainsi que les étapes à réaliser si ce n’est pas le cas. Elle explique également comment vous migrer vos dépendances vers le format [PackageReference](/nuget/consume-packages/package-references-in-project-files) utilisé dans .NET Core.

2. Reciblez tous les projets que vous voulez porter pour cibler le .NET Framework 4.7.2 ou version ultérieure.

   Cette étape garantit que vous pouvez utiliser des API alternatives pour des cibles spécifiques au .NET Framework si .NET Core ne prend en charge une API particulière.

3. Utilisez [l’analyseur .NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) pour analyser vos assemblys et développer un plan pour réaliser le portage en fonction de ses résultats.

   L’outil API Portability Analyzer analyse vos assemblys compilés et génère un rapport qui présente un résumé de portabilité générale ainsi qu’une analyse de chaque API que vous utilisez et qui n’est pas disponible sur .NET Core. Vous pouvez utiliser ce rapport parallèlement à une analyse de votre code base pour développer un plan de la façon dont vous allez porter votre code.

4. Porter le code de vos tests.

   Le portage vers .NET Core représentant un important changement pour votre code base, il est fortement recommandé de porter vos tests, pour pouvoir exécuter des tests au fil du portage de votre code. MSTest, xUnit et NUnit prennent tous en charge .NET Core.

5. Exécutez votre plan de portage !

La liste suivante présente les outils qui peuvent vous être utiles lors du processus de portage :

* .NET Portability Analyzer : [outil de ligne de commande](https://github.com/Microsoft/dotnet-apiport/releases) ou [Extension Visual Studio](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer), une chaîne d’outils qui permet de générer un rapport sur la portabilité de votre code entre le .NET Framework et .NET Core, avec une analyse des problèmes par assembly. Pour plus d’informations, consultez [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md).
* Analyseur d’API .NET : un analyseur Roslyn qui détecte les risques potentiels liés à la compatibilité des API C# sur différentes plateformes, et détecte les appels à des API déconseillées. Pour plus d'informations, consultez [Analyseur d’API .NET](../../standard/analyzers/api-analyzer.md).
* Reverse Package Search - A [service web pratique](https://packagesearch.azurewebsites.net) qui vous permet de rechercher un type et de trouver des packages contenant ce type.

En outre, vous pouvez essayer de porter des solutions plus petites ou des projets individuels au format de fichier de projet .NET Core avec l’outil [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017).

> [!WARNING] 
> CsprojToVs2017 est un outil tiers. Il n’existe aucune garantie que cet outil fonctionne pour tous vos projets, et il peut entraîner de légères modifications du comportement dont vous dépendez. CsprojToVs2017 doit être utilisé comme un _point de départ_ qui automatise les tâches de base pouvant être automatisées. Ce n’est pas une solution garantie pour la migration de formats de fichiers projet.

>[!div class="step-by-step"]
>[Next](net-framework-tech-unavailable.md)
