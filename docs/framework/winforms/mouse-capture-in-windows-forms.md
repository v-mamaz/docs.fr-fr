---
title: Capture de la souris dans les Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: ca16d2fa2339f8d9110bb748a687f90e093598fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690326"
---
# <a name="mouse-capture-in-windows-forms"></a>Capture de la souris dans les Windows Forms
*Capture de souris* signifie qu’un contrôle prend de toutes les entrées de souris. Lorsqu’un contrôle a capturé la souris, il reçoit l’entrée de la souris soit ou non le pointeur dans ses bordures.  
  
## <a name="setting-mouse-capture"></a>Définition de Capture de la souris  
 Dans les Windows Forms, la souris est capturée par le contrôle lorsque l’utilisateur appuie sur un bouton de la souris sur un contrôle, et la souris est relâchée par le contrôle lorsque l’utilisateur relâche le bouton de la souris.  
  
 Le <xref:System.Windows.Forms.Control.Capture%2A> propriété de la <xref:System.Windows.Forms.Control> classe spécifie si un contrôle a capturé la souris. Pour déterminer quand un contrôle perd la capture de la souris, gérez le <xref:System.Windows.Forms.Control.MouseCaptureChanged> événement.  
  
 Seule la fenêtre de premier plan peut capturer la souris. Lorsqu’une fenêtre d’arrière-plan tente de capturer la souris, la fenêtre reçoit des messages uniquement pour les événements de souris qui se produisent lorsque le pointeur de la souris se trouve dans la partie visible de la fenêtre. En outre, même si la fenêtre de premier plan a capturé la souris, l’utilisateur peut toujours cliquer sur une autre fenêtre, plaçant au premier plan. Lorsque la souris est capturée, les touches de raccourci ne fonctionnent pas.  
  
## <a name="see-also"></a>Voir aussi
- [Entrée de la souris dans une application Windows Forms](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
