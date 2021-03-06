---
title: "'<typename>' ne peut pas hériter de <type> '<basetypename>' car il étend l'accès du <type> de base en dehors de l'assembly"
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: 226c85f887ecc706a5cb554c2163742f10896141
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269820"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a>«\<nom_type >' ne peut pas hériter \<type > '\<nom_type_base >', car il étend l’accès de la base de \<type > en dehors de l’assembly
Une classe ou interface hérite d’une classe de base ou interface a, mais un niveau d’accès moins restrictif.  
  
 Par exemple, un `Public` interface hérite d’un `Friend` interface, ou un `Protected` hérite de la classe un `Private` classe. Cela expose la classe de base ou une interface pour accéder aux au-delà du niveau prévu.  
  
 **ID d’erreur :** BC30910  
  
## <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Modifier le niveau d’accès de la classe dérivée ou une interface soit au moins aussi restrictifs que celui de la classe de base ou l’interface.  
  
     ou  
  
-   Si le niveau d’accès moins restrictif, supprimez le `Inherits` instruction. Vous ne peut pas hériter d’une classe de base plus restreinte ou une interface.  
  
## <a name="see-also"></a>Voir aussi
- [Class (instruction)](../../../visual-basic/language-reference/statements/class-statement.md)
- [Interface (instruction)](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Inherits (instruction)](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Niveaux d’accès dans Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
