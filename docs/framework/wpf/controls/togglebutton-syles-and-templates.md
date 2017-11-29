---
title: "ToggleButton Stilleri ve Şablonları"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ecd6696ff9d62b4aa3397ac8567edc3fb387ba96
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="togglebutton-syles-and-templates"></a><span data-ttu-id="ab372-102">ToggleButton Stilleri ve Şablonları</span><span class="sxs-lookup"><span data-stu-id="ab372-102">ToggleButton Syles and Templates</span></span>
<span data-ttu-id="ab372-103">Stilleri ve şablonları için bu konuda açıklanmaktadır <xref:System.Windows.Controls.Primitives.ToggleButton> denetim.</span><span class="sxs-lookup"><span data-stu-id="ab372-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="ab372-104">Varsayılan değiştirebileceğiniz <xref:System.Windows.Controls.ControlTemplate> denetimi benzersiz bir görünüm vermek için.</span><span class="sxs-lookup"><span data-stu-id="ab372-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ab372-105">Daha fazla bilgi için bkz: [ControlTemplate oluşturarak varolan denetiminin görünümünü özelleştirme](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="ab372-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="togglebutton-parts"></a><span data-ttu-id="ab372-106">ToggleButton bölümleri</span><span class="sxs-lookup"><span data-stu-id="ab372-106">ToggleButton Parts</span></span>  
 <span data-ttu-id="ab372-107"><xref:System.Windows.Controls.Primitives.ToggleButton> Denetim adlandırılmış tüm bölümler sahip değil.</span><span class="sxs-lookup"><span data-stu-id="ab372-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>  
  
## <a name="togglebutton-states"></a><span data-ttu-id="ab372-108">ToggleButton durumları</span><span class="sxs-lookup"><span data-stu-id="ab372-108">ToggleButton States</span></span>  
 <span data-ttu-id="ab372-109">Aşağıdaki tablo için görsel durumlarını listeler <xref:System.Windows.Controls.Primitives.ToggleButton> denetim.</span><span class="sxs-lookup"><span data-stu-id="ab372-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>  
  
|<span data-ttu-id="ab372-110">VisualState adı</span><span class="sxs-lookup"><span data-stu-id="ab372-110">VisualState Name</span></span>|<span data-ttu-id="ab372-111">VisualStateGroup adı</span><span class="sxs-lookup"><span data-stu-id="ab372-111">VisualStateGroup Name</span></span>|<span data-ttu-id="ab372-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ab372-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ab372-113">Normal</span><span class="sxs-lookup"><span data-stu-id="ab372-113">Normal</span></span>|<span data-ttu-id="ab372-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ab372-114">CommonStates</span></span>|<span data-ttu-id="ab372-115">Varsayılan durumu.</span><span class="sxs-lookup"><span data-stu-id="ab372-115">The default state.</span></span>|  
|<span data-ttu-id="ab372-116">Fare üzerinde</span><span class="sxs-lookup"><span data-stu-id="ab372-116">MouseOver</span></span>|<span data-ttu-id="ab372-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ab372-117">CommonStates</span></span>|<span data-ttu-id="ab372-118">Fare işaretçisini üzerinde denetim konumlandırıldı.</span><span class="sxs-lookup"><span data-stu-id="ab372-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="ab372-119">Basılı</span><span class="sxs-lookup"><span data-stu-id="ab372-119">Pressed</span></span>|<span data-ttu-id="ab372-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ab372-120">CommonStates</span></span>|<span data-ttu-id="ab372-121">Denetim basıldığında.</span><span class="sxs-lookup"><span data-stu-id="ab372-121">The control is pressed.</span></span>|  
|<span data-ttu-id="ab372-122">Devre dışı</span><span class="sxs-lookup"><span data-stu-id="ab372-122">Disabled</span></span>|<span data-ttu-id="ab372-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ab372-123">CommonStates</span></span>|<span data-ttu-id="ab372-124">Denetim devre dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="ab372-124">The control is disabled.</span></span>|  
|<span data-ttu-id="ab372-125">Odaklanmış</span><span class="sxs-lookup"><span data-stu-id="ab372-125">Focused</span></span>|<span data-ttu-id="ab372-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ab372-126">FocusStates</span></span>|<span data-ttu-id="ab372-127">Denetimi odağa sahip.</span><span class="sxs-lookup"><span data-stu-id="ab372-127">The control has focus.</span></span>|  
|<span data-ttu-id="ab372-128">Odaksız</span><span class="sxs-lookup"><span data-stu-id="ab372-128">Unfocused</span></span>|<span data-ttu-id="ab372-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ab372-129">FocusStates</span></span>|<span data-ttu-id="ab372-130">Denetim odağı yok.</span><span class="sxs-lookup"><span data-stu-id="ab372-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="ab372-131">İşaretli</span><span class="sxs-lookup"><span data-stu-id="ab372-131">Checked</span></span>|<span data-ttu-id="ab372-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="ab372-132">CheckStates</span></span>|<span data-ttu-id="ab372-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>olan `true`.</span><span class="sxs-lookup"><span data-stu-id="ab372-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="ab372-134">İşaretli</span><span class="sxs-lookup"><span data-stu-id="ab372-134">Unchecked</span></span>|<span data-ttu-id="ab372-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="ab372-135">CheckStates</span></span>|<span data-ttu-id="ab372-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>olan `false`.</span><span class="sxs-lookup"><span data-stu-id="ab372-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="ab372-137">Belirsiz</span><span class="sxs-lookup"><span data-stu-id="ab372-137">Indeterminate</span></span>|<span data-ttu-id="ab372-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="ab372-138">CheckStates</span></span>|<span data-ttu-id="ab372-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>olan `true`, ve <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> olan `null`.</span><span class="sxs-lookup"><span data-stu-id="ab372-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="ab372-140">Geçerli</span><span class="sxs-lookup"><span data-stu-id="ab372-140">Valid</span></span>|<span data-ttu-id="ab372-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ab372-141">ValidationStates</span></span>|<span data-ttu-id="ab372-142">Denetim kullanan <xref:System.Windows.Controls.Validation> sınıfı ve <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> iliştirilmiş özelliği `false`.</span><span class="sxs-lookup"><span data-stu-id="ab372-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ab372-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ab372-143">InvalidFocused</span></span>|<span data-ttu-id="ab372-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ab372-144">ValidationStates</span></span>|<span data-ttu-id="ab372-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Ekli özellik `true` sahip denetimi odağa sahip.</span><span class="sxs-lookup"><span data-stu-id="ab372-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="ab372-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ab372-146">InvalidUnfocused</span></span>|<span data-ttu-id="ab372-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ab372-147">ValidationStates</span></span>|<span data-ttu-id="ab372-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Ekli özellik `true` sahip denetimi odağa sahip değil.</span><span class="sxs-lookup"><span data-stu-id="ab372-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="ab372-149">Görsel durumu belirsiz denetim şablonunuzda yoksa denetlenmeyen visual durumu visual durumu varsayılan olarak kullanılır.</span><span class="sxs-lookup"><span data-stu-id="ab372-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>  
  
## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="ab372-150">ToggleButton ControlTemplate Örneği</span><span class="sxs-lookup"><span data-stu-id="ab372-150">ToggleButton ControlTemplate Example</span></span>  
 <span data-ttu-id="ab372-151">Aşağıdaki örnekte nasıl tanımlanacağı gösterilmektedir bir <xref:System.Windows.Controls.ControlTemplate> için <xref:System.Windows.Controls.Primitives.ToggleButton> denetim.</span><span class="sxs-lookup"><span data-stu-id="ab372-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToggleButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]  
  
 <span data-ttu-id="ab372-152">Önceki örnekte, bir veya daha fazla aşağıdaki kaynakları kullanır.</span><span class="sxs-lookup"><span data-stu-id="ab372-152">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ab372-153">Tam bir örnek için bkz: [ControlTemplates örneği ile stil oluşturma](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="ab372-153">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab372-154">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ab372-154">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="ab372-155">Denetim stilleri ve şablonları</span><span class="sxs-lookup"><span data-stu-id="ab372-155">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="ab372-156">Denetim özelleştirme</span><span class="sxs-lookup"><span data-stu-id="ab372-156">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="ab372-157">Stil ve şablon oluşturma</span><span class="sxs-lookup"><span data-stu-id="ab372-157">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="ab372-158">ControlTemplate oluşturarak varolan denetiminin görünümünü özelleştirme</span><span class="sxs-lookup"><span data-stu-id="ab372-158">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)