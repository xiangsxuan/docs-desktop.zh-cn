---
title: Button 样式和模板
description: 了解 Windows Presentation Foundation 按钮控件的样式和模板。 修改 System.windows.controls.controltemplate>，为控件指定独特的外观。
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: 957c0663a8c444de71d2710bcff04cb73aaf3e27
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973273"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="b54d4-104">Button 样式和模板</span><span class="sxs-lookup"><span data-stu-id="b54d4-104">Button Styles and Templates</span></span>
<span data-ttu-id="b54d4-105">本主题描述控件的样式和模板 <xref:System.Windows.Controls.Button> 。</span><span class="sxs-lookup"><span data-stu-id="b54d4-105">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="b54d4-106">您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。</span><span class="sxs-lookup"><span data-stu-id="b54d4-106">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b54d4-107">有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。</span><span class="sxs-lookup"><span data-stu-id="b54d4-107">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="b54d4-108">Button 部分</span><span class="sxs-lookup"><span data-stu-id="b54d4-108">Button Parts</span></span>  
 <span data-ttu-id="b54d4-109"><xref:System.Windows.Controls.Button>控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="b54d4-109">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="b54d4-110">按钮状态</span><span class="sxs-lookup"><span data-stu-id="b54d4-110">Button States</span></span>  
 <span data-ttu-id="b54d4-111">下表列出了控件的可视状态 <xref:System.Windows.Controls.Button> 。</span><span class="sxs-lookup"><span data-stu-id="b54d4-111">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="b54d4-112">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="b54d4-112">VisualState Name</span></span>|<span data-ttu-id="b54d4-113">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="b54d4-113">VisualStateGroup Name</span></span>|<span data-ttu-id="b54d4-114">描述</span><span class="sxs-lookup"><span data-stu-id="b54d4-114">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b54d4-115">普通</span><span class="sxs-lookup"><span data-stu-id="b54d4-115">Normal</span></span>|<span data-ttu-id="b54d4-116">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b54d4-116">CommonStates</span></span>|<span data-ttu-id="b54d4-117">默认状态。</span><span class="sxs-lookup"><span data-stu-id="b54d4-117">The default state.</span></span>|  
|<span data-ttu-id="b54d4-118">MouseOver</span><span class="sxs-lookup"><span data-stu-id="b54d4-118">MouseOver</span></span>|<span data-ttu-id="b54d4-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b54d4-119">CommonStates</span></span>|<span data-ttu-id="b54d4-120">鼠标指针悬停在控件上方。</span><span class="sxs-lookup"><span data-stu-id="b54d4-120">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="b54d4-121">已按下</span><span class="sxs-lookup"><span data-stu-id="b54d4-121">Pressed</span></span>|<span data-ttu-id="b54d4-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b54d4-122">CommonStates</span></span>|<span data-ttu-id="b54d4-123">已按下控件。</span><span class="sxs-lookup"><span data-stu-id="b54d4-123">The control is pressed.</span></span>|  
|<span data-ttu-id="b54d4-124">已禁用</span><span class="sxs-lookup"><span data-stu-id="b54d4-124">Disabled</span></span>|<span data-ttu-id="b54d4-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b54d4-125">CommonStates</span></span>|<span data-ttu-id="b54d4-126">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="b54d4-126">The control is disabled.</span></span>|  
|<span data-ttu-id="b54d4-127">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="b54d4-127">Focused</span></span>|<span data-ttu-id="b54d4-128">FocusStates</span><span class="sxs-lookup"><span data-stu-id="b54d4-128">FocusStates</span></span>|<span data-ttu-id="b54d4-129">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="b54d4-129">The control has focus.</span></span>|  
|<span data-ttu-id="b54d4-130">失去焦点</span><span class="sxs-lookup"><span data-stu-id="b54d4-130">Unfocused</span></span>|<span data-ttu-id="b54d4-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="b54d4-131">FocusStates</span></span>|<span data-ttu-id="b54d4-132">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="b54d4-132">The control does not have focus.</span></span>|  
|<span data-ttu-id="b54d4-133">有效</span><span class="sxs-lookup"><span data-stu-id="b54d4-133">Valid</span></span>|<span data-ttu-id="b54d4-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b54d4-134">ValidationStates</span></span>|<span data-ttu-id="b54d4-135">控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="b54d4-135">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b54d4-136">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b54d4-136">InvalidFocused</span></span>|<span data-ttu-id="b54d4-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b54d4-137">ValidationStates</span></span>|<span data-ttu-id="b54d4-138"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性为 `true` ，并且控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="b54d4-138">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="b54d4-139">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b54d4-139">InvalidUnfocused</span></span>|<span data-ttu-id="b54d4-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b54d4-140">ValidationStates</span></span>|<span data-ttu-id="b54d4-141"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性为 `true` ，并且该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="b54d4-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="b54d4-142">按钮 System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="b54d4-142">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="b54d4-143">下面的示例演示如何为控件定义 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Button> 。</span><span class="sxs-lookup"><span data-stu-id="b54d4-143">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="b54d4-144">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="b54d4-144">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b54d4-145">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="b54d4-145">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b54d4-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b54d4-146">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="b54d4-147">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="b54d4-147">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="b54d4-148">控件自定义</span><span class="sxs-lookup"><span data-stu-id="b54d4-148">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="b54d4-149">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="b54d4-149">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="b54d4-150">创建控件模板</span><span class="sxs-lookup"><span data-stu-id="b54d4-150">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)