---
title: "Comment : fournir une bitmap pour un contrôle en vue de l'afficher dans la boîte à outils"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
ms.openlocfilehash: aa32850b9bcd1a15a93bd6c80b2278278d12c417
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43746543"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a>Comment : fournir une bitmap pour un contrôle en vue de l'afficher dans la boîte à outils
Si vous souhaitez avoir une icône spéciale pour votre contrôle s’affichent dans le **boîte à outils**, vous pouvez spécifier une image particulière en utilisant le <xref:System.Drawing.ToolboxBitmapAttribute>. Cette classe est un *attribut*, c’est-à-dire un type spécial de classe que vous pouvez joindre à d’autres classes. Pour plus d’informations sur les attributs, consultez [vue d’ensemble des attributs (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) pour Visual Basic ou [attributs (c#)](../../../csharp/programming-guide/concepts/attributes/index.md) pour c#.  
  
 À l’aide de la <xref:System.Drawing.ToolboxBitmapAttribute>, vous pouvez spécifier une chaîne qui indique le chemin d’accès et le nom d’un bitmap de 16 par 16 pixels. Cette image bitmap apparaît alors en regard de votre contrôle lorsqu’elle est ajoutée à la **boîte à outils**. Vous pouvez également spécifier un <xref:System.Type>, auquel cas l’image bitmap associée à ce type est chargé. Si vous spécifiez à la fois un <xref:System.Type> et une chaîne, le contrôle recherche une ressource d’image avec le nom spécifié par le paramètre de chaîne dans l’assembly contenant le type spécifié par le <xref:System.Type> paramètre.  
  
### <a name="to-specify-a-toolbox-bitmap-for-your-control"></a>Pour spécifier une image de bitmap dans la boîte à outils concernant votre contrôle  
  
1.  Ajouter le <xref:System.Drawing.ToolboxBitmapAttribute> à la déclaration de classe de votre contrôle avant le `Class` mot clé pour visual Basic et au-dessus de la déclaration de classe pour Visual c#.  
  
    ```vb  
    ' Specifies the bitmap associated with the Button type.  
    <ToolboxBitmap(GetType(Button))> Class MyControl1  
    ' Specifies a bitmap file.  
    End Class  
    <ToolboxBitmap("C:\Documents and Settings\Joe\MyPics\myImage.bmp")> _  
       Class MyControl2  
    End Class  
    ' Specifies a type that indicates the assembly to search, and the name   
    ' of an image resource to look for.  
    <ToolboxBitmap(GetType(MyControl), "MyControlBitmap")> Class MyControl  
    End Class  
    ```  
  
    ```csharp  
    // Specifies the bitmap associated with the Button type.  
    [ToolboxBitmap(typeof(Button))]  
    class MyControl1 : UserControl  
    {  
    }  
    // Specifies a bitmap file.  
    [ToolboxBitmap(@"C:\Documents and Settings\Joe\MyPics\myImage.bmp")]  
    class MyControl2 : UserControl  
    {  
    }  
    // Specifies a type that indicates the assembly to search, and the name   
    // of an image resource to look for.  
    [ToolboxBitmap(typeof(MyControl), "MyControlBitmap")]  
    class MyControl : UserControl  
    {  
    }  
    ```  
  
2.  Regénérez le projet.  
  
    > [!NOTE]
    >  L’image bitmap n’apparaît pas dans la boîte à outils pour les composants et les contrôles générés automatiquement. Pour afficher l’image bitmap, rechargez le contrôle par le biais de la boîte de dialogue **Choisir des éléments de boîte à outils**. Pour plus d’informations, consultez l’article [Procédure pas à pas : remplissage automatique de la boîte à outils avec des composants personnalisés](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
## <a name="see-also"></a>Voir aussi

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [Procédure pas à pas : remplissage automatique de la boîte à outils avec des composants personnalisés](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [Développement de contrôles Windows Forms au moment du design](developing-windows-forms-controls-at-design-time.md)
- [Vue d’ensemble des attributs (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Attributs (C#)](../../../csharp/programming-guide/concepts/attributes/index.md)
