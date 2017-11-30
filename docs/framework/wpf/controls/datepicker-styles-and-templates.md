---
title: "Styles et modèles DatePicker"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], DatePicker
- DatePicker [WPF], styles and templates
- templates [WPF], DatePicker
- parts [WPF], DatePicker
- styles [WPF], DatePicker
- states [WPF], DatePicker
ms.assetid: c430a657-692f-44bd-a549-2341f92d6115
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fbe8a3935da2d9aa928467b4c64da455f3b53c5f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="datepicker-styles-and-templates"></a><span data-ttu-id="1e5df-102">Styles et modèles DatePicker</span><span class="sxs-lookup"><span data-stu-id="1e5df-102">DatePicker Styles and Templates</span></span>
<span data-ttu-id="1e5df-103">Cette rubrique décrit les styles et modèles pour la <xref:System.Windows.Controls.DatePicker> contrôle.</span><span class="sxs-lookup"><span data-stu-id="1e5df-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DatePicker> control.</span></span> <span data-ttu-id="1e5df-104">Vous pouvez modifier la valeur par défaut <xref:System.Windows.Controls.ControlTemplate> pour donner une apparence unique au contrôle.</span><span class="sxs-lookup"><span data-stu-id="1e5df-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="1e5df-105">Pour plus d’informations, consultez [Personnalisation de l’apparence d’un contrôle existant en créant un ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="1e5df-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="datepicker-parts"></a><span data-ttu-id="1e5df-106">Composants de DatePicker</span><span class="sxs-lookup"><span data-stu-id="1e5df-106">DatePicker Parts</span></span>  
 <span data-ttu-id="1e5df-107">Le tableau suivant répertorie les composants nommés pour le <xref:System.Windows.Controls.DatePicker> contrôle.</span><span class="sxs-lookup"><span data-stu-id="1e5df-107">The following table lists the named parts for the <xref:System.Windows.Controls.DatePicker> control.</span></span>  
  
|<span data-ttu-id="1e5df-108">Élément</span><span class="sxs-lookup"><span data-stu-id="1e5df-108">Part</span></span>|<span data-ttu-id="1e5df-109">Type</span><span class="sxs-lookup"><span data-stu-id="1e5df-109">Type</span></span>|<span data-ttu-id="1e5df-110">Description</span><span class="sxs-lookup"><span data-stu-id="1e5df-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1e5df-111">PART_Root</span><span class="sxs-lookup"><span data-stu-id="1e5df-111">PART_Root</span></span>|<xref:System.Windows.Controls.Grid>|<span data-ttu-id="1e5df-112">La racine du contrôle.</span><span class="sxs-lookup"><span data-stu-id="1e5df-112">The root of the control.</span></span>|  
|<span data-ttu-id="1e5df-113">PART_Button</span><span class="sxs-lookup"><span data-stu-id="1e5df-113">PART_Button</span></span>|<xref:System.Windows.Controls.Button>|<span data-ttu-id="1e5df-114">Le bouton qui ouvre et ferme le <xref:System.Windows.Controls.Calendar>.</span><span class="sxs-lookup"><span data-stu-id="1e5df-114">The button that opens and closes the <xref:System.Windows.Controls.Calendar>.</span></span>|  
|<span data-ttu-id="1e5df-115">PART_TextBox</span><span class="sxs-lookup"><span data-stu-id="1e5df-115">PART_TextBox</span></span>|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|<span data-ttu-id="1e5df-116">La zone de texte qui vous permet d’entrer une date.</span><span class="sxs-lookup"><span data-stu-id="1e5df-116">The text box that allows you to input a date.</span></span>|  
|<span data-ttu-id="1e5df-117">PART_Popup</span><span class="sxs-lookup"><span data-stu-id="1e5df-117">PART_Popup</span></span>|<xref:System.Windows.Controls.Primitives.Popup>|<span data-ttu-id="1e5df-118">La fenêtre contextuelle pour le <xref:System.Windows.Controls.DatePicker> contrôle.</span><span class="sxs-lookup"><span data-stu-id="1e5df-118">The popup for the <xref:System.Windows.Controls.DatePicker> control.</span></span>|  
  
## <a name="datepicker-states"></a><span data-ttu-id="1e5df-119">États de DatePicker</span><span class="sxs-lookup"><span data-stu-id="1e5df-119">DatePicker States</span></span>  
 <span data-ttu-id="1e5df-120">Le tableau suivant répertorie les états visuels pour le <xref:System.Windows.Controls.DatePicker> contrôle.</span><span class="sxs-lookup"><span data-stu-id="1e5df-120">The following table lists the visual states for the <xref:System.Windows.Controls.DatePicker> control.</span></span>  
  
|<span data-ttu-id="1e5df-121">Nom VisualState</span><span class="sxs-lookup"><span data-stu-id="1e5df-121">VisualState Name</span></span>|<span data-ttu-id="1e5df-122">Nom VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="1e5df-122">VisualStateGroup Name</span></span>|<span data-ttu-id="1e5df-123">Description</span><span class="sxs-lookup"><span data-stu-id="1e5df-123">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1e5df-124">Normale</span><span class="sxs-lookup"><span data-stu-id="1e5df-124">Normal</span></span>|<span data-ttu-id="1e5df-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="1e5df-125">CommonStates</span></span>|<span data-ttu-id="1e5df-126">État par défaut.</span><span class="sxs-lookup"><span data-stu-id="1e5df-126">The default state.</span></span>|  
|<span data-ttu-id="1e5df-127">Désactivé</span><span class="sxs-lookup"><span data-stu-id="1e5df-127">Disabled</span></span>|<span data-ttu-id="1e5df-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="1e5df-128">CommonStates</span></span>|<span data-ttu-id="1e5df-129">Le <xref:System.Windows.Controls.DatePicker> est désactivé.</span><span class="sxs-lookup"><span data-stu-id="1e5df-129">The <xref:System.Windows.Controls.DatePicker> is disabled.</span></span>|  
|<span data-ttu-id="1e5df-130">Valide</span><span class="sxs-lookup"><span data-stu-id="1e5df-130">Valid</span></span>|<span data-ttu-id="1e5df-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1e5df-131">ValidationStates</span></span>|<span data-ttu-id="1e5df-132">Le contrôle utilise le <xref:System.Windows.Controls.Validation> classe et le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propriété jointe est `false`.</span><span class="sxs-lookup"><span data-stu-id="1e5df-132">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="1e5df-133">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="1e5df-133">InvalidFocused</span></span>|<span data-ttu-id="1e5df-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1e5df-134">ValidationStates</span></span>|<span data-ttu-id="1e5df-135">Le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propriété jointe est `true` a le contrôle a le focus.</span><span class="sxs-lookup"><span data-stu-id="1e5df-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="1e5df-136">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="1e5df-136">InvalidUnfocused</span></span>|<span data-ttu-id="1e5df-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1e5df-137">ValidationStates</span></span>|<span data-ttu-id="1e5df-138">Le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propriété jointe est `true` a le contrôle n’a pas le focus.</span><span class="sxs-lookup"><span data-stu-id="1e5df-138">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="datepickertextbox-parts"></a><span data-ttu-id="1e5df-139">Parties DatePickerTextBox</span><span class="sxs-lookup"><span data-stu-id="1e5df-139">DatePickerTextBox Parts</span></span>  
 <span data-ttu-id="1e5df-140">Le tableau suivant répertorie les composants nommés pour le <xref:System.Windows.Controls.Primitives.DatePickerTextBox> contrôle.</span><span class="sxs-lookup"><span data-stu-id="1e5df-140">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.DatePickerTextBox> control.</span></span>  
  
|<span data-ttu-id="1e5df-141">Élément</span><span class="sxs-lookup"><span data-stu-id="1e5df-141">Part</span></span>|<span data-ttu-id="1e5df-142">Type</span><span class="sxs-lookup"><span data-stu-id="1e5df-142">Type</span></span>|<span data-ttu-id="1e5df-143">Description</span><span class="sxs-lookup"><span data-stu-id="1e5df-143">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1e5df-144">PART_Watermark</span><span class="sxs-lookup"><span data-stu-id="1e5df-144">PART_Watermark</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="1e5df-145">L’élément qui contient le texte initial dans le <xref:System.Windows.Controls.DatePicker>.</span><span class="sxs-lookup"><span data-stu-id="1e5df-145">The element that contains the initial text in the <xref:System.Windows.Controls.DatePicker>.</span></span>|  
|<span data-ttu-id="1e5df-146">PART_ContentElement</span><span class="sxs-lookup"><span data-stu-id="1e5df-146">PART_ContentElement</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="1e5df-147">Un élément visuel qui peut contenir un <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="1e5df-147">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="1e5df-148">Le texte de la <xref:System.Windows.Controls.TextBox> s’affiche dans cet élément.</span><span class="sxs-lookup"><span data-stu-id="1e5df-148">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="datepickertextbox-states"></a><span data-ttu-id="1e5df-149">États de DatePickerTextBox</span><span class="sxs-lookup"><span data-stu-id="1e5df-149">DatePickerTextBox States</span></span>  
 <span data-ttu-id="1e5df-150">Le tableau suivant répertorie les états visuels pour le <xref:System.Windows.Controls.Primitives.DatePickerTextBox> contrôle.</span><span class="sxs-lookup"><span data-stu-id="1e5df-150">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.DatePickerTextBox> control.</span></span>  
  
|<span data-ttu-id="1e5df-151">Nom VisualState</span><span class="sxs-lookup"><span data-stu-id="1e5df-151">VisualState Name</span></span>|<span data-ttu-id="1e5df-152">Nom VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="1e5df-152">VisualStateGroup Name</span></span>|<span data-ttu-id="1e5df-153">Description</span><span class="sxs-lookup"><span data-stu-id="1e5df-153">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1e5df-154">Normale</span><span class="sxs-lookup"><span data-stu-id="1e5df-154">Normal</span></span>|<span data-ttu-id="1e5df-155">CommonStates</span><span class="sxs-lookup"><span data-stu-id="1e5df-155">CommonStates</span></span>|<span data-ttu-id="1e5df-156">État par défaut.</span><span class="sxs-lookup"><span data-stu-id="1e5df-156">The default state.</span></span>|  
|<span data-ttu-id="1e5df-157">Désactivé</span><span class="sxs-lookup"><span data-stu-id="1e5df-157">Disabled</span></span>|<span data-ttu-id="1e5df-158">CommonStates</span><span class="sxs-lookup"><span data-stu-id="1e5df-158">CommonStates</span></span>|<span data-ttu-id="1e5df-159">Le <xref:System.Windows.Controls.Primitives.DatePickerTextBox> est désactivé.</span><span class="sxs-lookup"><span data-stu-id="1e5df-159">The <xref:System.Windows.Controls.Primitives.DatePickerTextBox> is disabled.</span></span>|  
|<span data-ttu-id="1e5df-160">MouseOver</span><span class="sxs-lookup"><span data-stu-id="1e5df-160">MouseOver</span></span>|<span data-ttu-id="1e5df-161">CommonStates</span><span class="sxs-lookup"><span data-stu-id="1e5df-161">CommonStates</span></span>|<span data-ttu-id="1e5df-162">Le pointeur de la souris est positionné sur le <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.</span><span class="sxs-lookup"><span data-stu-id="1e5df-162">The mouse pointer is positioned over the <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.</span></span>|  
|<span data-ttu-id="1e5df-163">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="1e5df-163">ReadOnly</span></span>|<span data-ttu-id="1e5df-164">CommonStates</span><span class="sxs-lookup"><span data-stu-id="1e5df-164">CommonStates</span></span>|<span data-ttu-id="1e5df-165">L’utilisateur ne peut pas modifier le texte dans le <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.</span><span class="sxs-lookup"><span data-stu-id="1e5df-165">The user cannot change the text in the <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.</span></span>|  
|<span data-ttu-id="1e5df-166">Avec focus</span><span class="sxs-lookup"><span data-stu-id="1e5df-166">Focused</span></span>|<span data-ttu-id="1e5df-167">FocusStates</span><span class="sxs-lookup"><span data-stu-id="1e5df-167">FocusStates</span></span>|<span data-ttu-id="1e5df-168">Le contrôle a le focus.</span><span class="sxs-lookup"><span data-stu-id="1e5df-168">The control has focus.</span></span>|  
|<span data-ttu-id="1e5df-169">Sans focus</span><span class="sxs-lookup"><span data-stu-id="1e5df-169">Unfocused</span></span>|<span data-ttu-id="1e5df-170">FocusStates</span><span class="sxs-lookup"><span data-stu-id="1e5df-170">FocusStates</span></span>|<span data-ttu-id="1e5df-171">Le contrôle n’a pas le focus.</span><span class="sxs-lookup"><span data-stu-id="1e5df-171">The control does not have focus.</span></span>|  
|<span data-ttu-id="1e5df-172">Limite supérieure</span><span class="sxs-lookup"><span data-stu-id="1e5df-172">Watermarked</span></span>|<span data-ttu-id="1e5df-173">WatermarkStates</span><span class="sxs-lookup"><span data-stu-id="1e5df-173">WatermarkStates</span></span>|<span data-ttu-id="1e5df-174">Le contrôle affiche son texte d’origine.</span><span class="sxs-lookup"><span data-stu-id="1e5df-174">The control displays its initial text.</span></span>  <span data-ttu-id="1e5df-175">Le <xref:System.Windows.Controls.Primitives.DatePickerTextBox> est dans l’état lorsque l’utilisateur n’a pas entré du texte ou de la date sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1e5df-175">The <xref:System.Windows.Controls.Primitives.DatePickerTextBox> is in the state when the user has not entered text or selected a date.</span></span>|  
|<span data-ttu-id="1e5df-176">Unwatermarked</span><span class="sxs-lookup"><span data-stu-id="1e5df-176">Unwatermarked</span></span>|<span data-ttu-id="1e5df-177">WatermarkStates</span><span class="sxs-lookup"><span data-stu-id="1e5df-177">WatermarkStates</span></span>|<span data-ttu-id="1e5df-178">L’utilisateur a entré du texte dans le <xref:System.Windows.Controls.Primitives.DatePickerTextBox> ou sélectionné une date dans le <xref:System.Windows.Controls.DatePicker>.</span><span class="sxs-lookup"><span data-stu-id="1e5df-178">The user has entered text into the <xref:System.Windows.Controls.Primitives.DatePickerTextBox> or selected a date in the <xref:System.Windows.Controls.DatePicker>.</span></span>|  
|<span data-ttu-id="1e5df-179">Valide</span><span class="sxs-lookup"><span data-stu-id="1e5df-179">Valid</span></span>|<span data-ttu-id="1e5df-180">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1e5df-180">ValidationStates</span></span>|<span data-ttu-id="1e5df-181">Le contrôle utilise le <xref:System.Windows.Controls.Validation> classe et le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propriété jointe est `false`.</span><span class="sxs-lookup"><span data-stu-id="1e5df-181">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="1e5df-182">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="1e5df-182">InvalidFocused</span></span>|<span data-ttu-id="1e5df-183">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1e5df-183">ValidationStates</span></span>|<span data-ttu-id="1e5df-184">Le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propriété jointe est `true` a le contrôle a le focus.</span><span class="sxs-lookup"><span data-stu-id="1e5df-184">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="1e5df-185">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="1e5df-185">InvalidUnfocused</span></span>|<span data-ttu-id="1e5df-186">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1e5df-186">ValidationStates</span></span>|<span data-ttu-id="1e5df-187">Le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propriété jointe est `true` a le contrôle n’a pas le focus.</span><span class="sxs-lookup"><span data-stu-id="1e5df-187">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="datepicker-controltemplate-example"></a><span data-ttu-id="1e5df-188">DatePicker ControlTemplate, exemple</span><span class="sxs-lookup"><span data-stu-id="1e5df-188">DatePicker ControlTemplate Example</span></span>  
 <span data-ttu-id="1e5df-189">L’exemple suivant montre comment définir un <xref:System.Windows.Controls.ControlTemplate> pour la <xref:System.Windows.Controls.DatePicker> contrôle.</span><span class="sxs-lookup"><span data-stu-id="1e5df-189">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DatePicker> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DatePicker](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
 <span data-ttu-id="1e5df-190">L’exemple précédent utilise une ou plusieurs des ressources suivantes.</span><span class="sxs-lookup"><span data-stu-id="1e5df-190">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="1e5df-191">Pour voir l’exemple complet, consultez [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041) (Exemple de style avec ControlTemplates).</span><span class="sxs-lookup"><span data-stu-id="1e5df-191">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e5df-192">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1e5df-192">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="1e5df-193">Styles et modèles Control</span><span class="sxs-lookup"><span data-stu-id="1e5df-193">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="1e5df-194">Personnalisation des contrôles</span><span class="sxs-lookup"><span data-stu-id="1e5df-194">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="1e5df-195">Application d’un style et création de modèles</span><span class="sxs-lookup"><span data-stu-id="1e5df-195">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="1e5df-196">Personnalisation de l’apparence d’un contrôle existant en créant un ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="1e5df-196">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)