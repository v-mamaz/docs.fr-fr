---
title: 'Procédure : Animer une propriété sans utiliser de storyboard'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- non-Storyboard animation
- local animation [WPF]
- animation [WPF], non-Storyboard (local)
ms.assetid: d411db70-4df7-487d-82bc-95a7c1b2e7f8
ms.openlocfilehash: f2cb3533010579f912da62cb2f7fe28d982890c7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678133"
---
# <a name="how-to-animate-a-property-without-using-a-storyboard"></a>Procédure : Animer une propriété sans utiliser de storyboard
Cet exemple montre comment appliquer une animation à une propriété sans utiliser un <xref:System.Windows.Media.Animation.Storyboard>.  
  
> [!NOTE]
>  La fonctionnalité n’est pas disponible en langage [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Pour plus d’informations sur l’animation d’une propriété en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], consultez [Animer une propriété à l’aide d’un storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).  
  
 Pour appliquer une animation locale à une propriété, utilisez le <xref:System.Windows.UIElement.BeginAnimation%2A> (méthode). Cette méthode accepte deux paramètres : un <xref:System.Windows.DependencyProperty> qui spécifie la propriété à animer et l’animation à appliquer à cette propriété.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment animer la couleur d’arrière-plan et de la largeur d’un <xref:System.Windows.Controls.Button>.  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 Une variété de classes d’animation dans le <xref:System.Windows.Media.Animation> espace de noms existe pour animer différents types de propriétés. Pour plus d’informations sur l’animation de propriétés, consultez [Vue d’ensemble de l’animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Pour plus d’informations sur les propriétés de dépendance (le type de propriétés présentées dans ces exemples) et leurs fonctionnalités, consultez [Vue d’ensemble des propriétés de dépendance](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
 Il existe d’autres façons d’animer sans utiliser <xref:System.Windows.Media.Animation.Storyboard> objets ; pour plus d’informations, consultez [vue d’ensemble des Techniques d’Animation propriété](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
## <a name="see-also"></a>Voir aussi
- <xref:System.Windows.Media.Animation.AnimationTimeline>
- <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Vue d’ensemble des techniques d’animation de propriétés](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
- [Vue d’ensemble de l’animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
