---
title: <see> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 9faf1ec7211493b8c0058439e9a6e3bcb293ea99
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289521"
---
# <a name="see-visual-basic"></a>\<consultez > (Visual Basic)
Spécifie un lien vers un autre membre.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>Paramètres  
 `member`  
 Référence à un membre ou un champ qu’il est possible d’appeler à partir de l’environnement de compilation actuel. Le compilateur vérifie que l’élément de code donné existe, et qu’il passe `member` au nom d’élément dans le code XML de sortie. `member` doit apparaître entre guillemets doubles (" ").  
  
## <a name="remarks"></a>Notes  
 Utilisez le `<see>` balise pour spécifier un lien à partir du texte. Utilisez [ \<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) pour indiquer le texte que vous souhaitez voir apparaître dans une section « Voir aussi ».  
  
 Compilez avec [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) pour placer les commentaires de documentation dans un fichier en vue de les traiter.  
  
## <a name="example"></a>Exemple  
 Cet exemple utilise le `<see>` balise dans le `UpdateRecord` section pour faire référence à la section Notes le `DoesRecordExist` (méthode).  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/see_1.vb)]  
  
## <a name="see-also"></a>Voir aussi
- [Étiquettes XML pour les commentaires](../../../visual-basic/language-reference/xmldoc/index.md)
