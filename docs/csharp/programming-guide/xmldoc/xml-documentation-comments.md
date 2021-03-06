---
title: Commentaires de documentation XML - Guide de programmation C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.xml
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
ms.openlocfilehash: c40f8ee189733aa1ae58f8e46c3b7cce005ad9d7
ms.sourcegitcommit: e39d93d358974b9ed4541cedf4e25c0101015c3c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "55204728"
---
# <a name="xml-documentation-comments-c-programming-guide"></a>Commentaires de documentation XML (Guide de programmation C#)
Dans Visual C #, vous pouvez créer de la documentation de votre code en incluant des éléments XML dans des champs de commentaire spéciaux (indiqués par trois barres obliques) dans le code source, juste avant le bloc de code auquel les commentaires font référence, par exemple :  
  
```csharp  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass {}  
```  
  
 Quand vous utilisez l’option [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) pour compiler, le compilateur recherche toutes les balises XML dans le code source et crée un fichier de documentation XML. Pour créer la documentation finale basée sur le fichier généré par le compilateur, vous pouvez créer un outil personnalisé ou utiliser un outil tel que [DocFX](https://dotnet.github.io/docfx/) ou [Sandcastle](https://github.com/EWSoftware/SHFB).  
  
 Pour faire référence à des éléments XML (par exemple, votre fonction traite des éléments XML spécifiques que vous souhaitez décrire dans un commentaire de documentation XML), vous pouvez utiliser le mécanisme de citation standard (`<` et `>`).  Pour faire référence aux identificateurs génériques dans les éléments de référence de code (`cref`), vous pouvez utiliser des caractères d’échappement (par exemple, `cref="List&lt;T&gt;"`) ou des accolades (`cref="List{T}"`).  En tant que cas particulier, le compilateur analyse les accolades comme des crochets pointus pour rendre le commentaire de documentation moins fastidieux à créer lorsqu'il s'agit de faire référence aux identificateurs génériques.  
  
> [!NOTE]
>  Les commentaires de documentation XML ne sont pas des métadonnées. Ils ne sont pas inclus dans l'assembly compilé et ne sont donc pas accessibles par réflexion.  
  
## <a name="in-this-section"></a>Dans cette section  
  
-   [Balises recommandées pour les commentaires de documentation](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)  
  
-   [Traitement du fichier XML](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md)  
  
-   [Délimiteurs pour les balises de documentation](../../../csharp/programming-guide/xmldoc/delimiters-for-documentation-tags.md)  
  
-   [Guide pratique pour utiliser les fonctionnalités de la documentation XML](../../../csharp/programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md)  
  
## <a name="related-sections"></a>Rubriques connexes  
 Pour plus d'informations, voir :  
  
-   [/doc (Traiter les commentaires de documentation)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
  
## <a name="c-language-specification"></a>Spécification du langage C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Voir aussi

- [Guide de programmation C#](../../../csharp/programming-guide/index.md)
