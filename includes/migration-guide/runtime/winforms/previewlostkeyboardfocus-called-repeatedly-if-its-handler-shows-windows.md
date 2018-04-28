### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a><span data-ttu-id="4db78-101">PreviewLostKeyboardFocus est appelé de façon répétée si son gestionnaire affiche une boîte de message Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4db78-101">PreviewLostKeyboardFocus is called repeatedly if its handler shows a Windows Forms message box</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4db78-102">Détails</span><span class="sxs-lookup"><span data-stu-id="4db78-102">Details</span></span>|<span data-ttu-id="4db78-103">À compter de la version 4.5 du .NET Framework, quand vous appelez <code>System.Windows.Forms.MessageBox.Show</code> à partir d’un gestionnaire <xref:System.Windows.UIElement.PreviewLostKeyboardFocus>, le gestionnaire est redéclenché quand la boîte de message est fermée, ce qui peut aboutir à une boucle infinie de boîtes de message.</span><span class="sxs-lookup"><span data-stu-id="4db78-103">Beginning in the .NET Framework 4.5, calling <code>System.Windows.Forms.MessageBox.Show</code> from a <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> handler will cause the handler to re-fire when the message box is closed, potentially resulting in an infinite loop of message boxes.</span></span>|
|<span data-ttu-id="4db78-104">Suggestion</span><span class="sxs-lookup"><span data-stu-id="4db78-104">Suggestion</span></span>|<span data-ttu-id="4db78-105">Il existe deux options pour contourner ce problème :</span><span class="sxs-lookup"><span data-stu-id="4db78-105">There are two options to work around this issue -</span></span><ol><li><span data-ttu-id="4db78-106">Vous pouvez appeler <code>System.Windows.MessageBox.Show</code> au lieu de <code>System.Windows.Forms.MessageBox.Show</code>.</span><span class="sxs-lookup"><span data-stu-id="4db78-106">It may be avoided by calling <code>System.Windows.MessageBox.Show</code> instead of <code>System.Windows.Forms.MessageBox.Show</code>.</span></span></li><li><span data-ttu-id="4db78-107">Vous pouvez afficher la boîte de message à partir d’un gestionnaire d’événements <xref:System.Windows.UIElement.LostKeyboardFocus> (au lieu du gestionnaire d’événements <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=name>).</span><span class="sxs-lookup"><span data-stu-id="4db78-107">It may be avoided by showing the message box from a <xref:System.Windows.UIElement.LostKeyboardFocus> event handler (as opposed to a <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=name> event handler).</span></span></li></ol>|
|<span data-ttu-id="4db78-108">Portée</span><span class="sxs-lookup"><span data-stu-id="4db78-108">Scope</span></span>|<span data-ttu-id="4db78-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4db78-109">Edge</span></span>|
|<span data-ttu-id="4db78-110">Version</span><span class="sxs-lookup"><span data-stu-id="4db78-110">Version</span></span>|<span data-ttu-id="4db78-111">4.5</span><span class="sxs-lookup"><span data-stu-id="4db78-111">4.5</span></span>|
|<span data-ttu-id="4db78-112">Type</span><span class="sxs-lookup"><span data-stu-id="4db78-112">Type</span></span>|<span data-ttu-id="4db78-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="4db78-113">Runtime</span></span>|
|<span data-ttu-id="4db78-114">API affectées</span><span class="sxs-lookup"><span data-stu-id="4db78-114">Affected APIs</span></span>|<ul><li><xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType></li></ul>|
