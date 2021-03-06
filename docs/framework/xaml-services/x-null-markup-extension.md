---
title: x:Null, extension de balisage
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: 5f0856f50e73a090d0ef624e2fb894d68b73c07e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54553319"
---
# <a name="xnull-markup-extension"></a>x:Null, extension de balisage
Spécifie `null` en tant que valeur pour un membre XAML.  
  
## <a name="xaml-attribute-usage"></a>Utilisation d'attributs XAML  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a>Notes  
 Le mot clé pour une référence null dans C# et [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] a la valeur null. Le mot clé Microsoft Visual Basic pour une référence null est `Nothing`, mais vous utilisez toujours `{x:Null}` en tant que l’utilisation XAML, quel que soit le langage de code-behind associer avec le XAML.  
  
 Le `x:Null` extension de balisage ne possède aucune propriété définissable.  
  
 L’utilisation d’une valeur null est souvent associée à l’exposition des membres XAML d’un type CLR <xref:System.Nullable%601> valeur.  
  
 Le `x:Null` extension de balisage, comme toutes les extensions de balisage XAML, utilise les accolades (`{,}`) pour la gestion des valeurs d’attribut soient autre chose que des littéraux ou des références de gestionnaire d’événements de séquence d’échappement. Syntaxe d’attribut est la syntaxe plus fréquemment utilisée avec cette extension de balisage. Syntaxe d’élément objet `<x:Null />` est techniquement possible, mais est rarement utilisé, car le `x:Null` extension de balisage n’a pas les paramètres positionnels ou les arguments de construction.  
  
 Pour plus d’informations sur les extensions de balisage, consultez [Extensions de balisage et WPF XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 Dans les Services XAML .NET Framework, la gestion de cette extension de balisage est définie par le <xref:System.Windows.Markup.NullExtension> classe.  
  
## <a name="wpf-usage-notes"></a>Remarques sur l’utilisation WPF  
 Notez que `null` n’est pas nécessairement la valeur initiale non définie pour une propriété de dépendance de type référence. La valeur par défaut initiale peut varier pour chaque propriété de dépendance et peut être basée sur les métadonnées spécifiques à la propriété. De nombreuses propriétés de dépendance n’acceptent pas `null` en tant que valeur, par le biais de balisage ou le code en raison de leurs implémentations de rappel de validation. Pour plus d’informations sur les propriétés de dépendance, consultez [vue d’ensemble des propriétés de dépendance](../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
## <a name="see-also"></a>Voir aussi
- <xref:System.Windows.DependencyProperty.UnsetValue>
- [Vue d’ensemble du langage XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [Extensions de balisage et XAML WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
