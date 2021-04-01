---
title: Expander 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Expander
- ControlTemplate [WPF], Expander
- templates [WPF], Expander
- Expander [WPF], styles and templates
- states [WPF], Expander
- parts [WPF], Expander
ms.assetid: da2e5a1c-5230-4c21-98a5-59c7895facd7
ms.openlocfilehash: f659d6ca6218cc8e18bb4e28d77dcaa13ffbf2d2
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972465"
---
# <a name="expander-styles-and-templates"></a><span data-ttu-id="34f7b-102">Expander 样式和模板</span><span class="sxs-lookup"><span data-stu-id="34f7b-102">Expander Styles and Templates</span></span>
<span data-ttu-id="34f7b-103">本主题描述控件的样式和模板 <xref:System.Windows.Controls.Expander> 。</span><span class="sxs-lookup"><span data-stu-id="34f7b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Expander> control.</span></span> <span data-ttu-id="34f7b-104">您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。</span><span class="sxs-lookup"><span data-stu-id="34f7b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="34f7b-105">有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。</span><span class="sxs-lookup"><span data-stu-id="34f7b-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="expander-parts"></a><span data-ttu-id="34f7b-106">扩展器部分</span><span class="sxs-lookup"><span data-stu-id="34f7b-106">Expander Parts</span></span>  
 <span data-ttu-id="34f7b-107"><xref:System.Windows.Controls.Expander>控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="34f7b-107">The <xref:System.Windows.Controls.Expander> control does not have any named parts.</span></span>  
  
## <a name="expander-states"></a><span data-ttu-id="34f7b-108">扩展器状态</span><span class="sxs-lookup"><span data-stu-id="34f7b-108">Expander States</span></span>  
 <span data-ttu-id="34f7b-109">下表列出了控件的可视状态 <xref:System.Windows.Controls.Expander> 。</span><span class="sxs-lookup"><span data-stu-id="34f7b-109">The following table lists the visual states for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
|<span data-ttu-id="34f7b-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="34f7b-110">VisualState Name</span></span>|<span data-ttu-id="34f7b-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="34f7b-111">VisualStateGroup Name</span></span>|<span data-ttu-id="34f7b-112">描述</span><span class="sxs-lookup"><span data-stu-id="34f7b-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="34f7b-113">普通</span><span class="sxs-lookup"><span data-stu-id="34f7b-113">Normal</span></span>|<span data-ttu-id="34f7b-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="34f7b-114">CommonStates</span></span>|<span data-ttu-id="34f7b-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="34f7b-115">The default state.</span></span>|  
|<span data-ttu-id="34f7b-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="34f7b-116">MouseOver</span></span>|<span data-ttu-id="34f7b-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="34f7b-117">CommonStates</span></span>|<span data-ttu-id="34f7b-118">鼠标指针悬停在控件上方。</span><span class="sxs-lookup"><span data-stu-id="34f7b-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="34f7b-119">已禁用</span><span class="sxs-lookup"><span data-stu-id="34f7b-119">Disabled</span></span>|<span data-ttu-id="34f7b-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="34f7b-120">CommonStates</span></span>|<span data-ttu-id="34f7b-121">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="34f7b-121">The control is disabled.</span></span>|  
|<span data-ttu-id="34f7b-122">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="34f7b-122">Focused</span></span>|<span data-ttu-id="34f7b-123">FocusStates</span><span class="sxs-lookup"><span data-stu-id="34f7b-123">FocusStates</span></span>|<span data-ttu-id="34f7b-124">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="34f7b-124">The control has focus.</span></span>|  
|<span data-ttu-id="34f7b-125">失去焦点</span><span class="sxs-lookup"><span data-stu-id="34f7b-125">Unfocused</span></span>|<span data-ttu-id="34f7b-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="34f7b-126">FocusStates</span></span>|<span data-ttu-id="34f7b-127">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="34f7b-127">The control does not have focus.</span></span>|  
|<span data-ttu-id="34f7b-128">展开</span><span class="sxs-lookup"><span data-stu-id="34f7b-128">Expanded</span></span>|<span data-ttu-id="34f7b-129">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="34f7b-129">ExpansionStates</span></span>|<span data-ttu-id="34f7b-130">控件已展开。</span><span class="sxs-lookup"><span data-stu-id="34f7b-130">The control is expanded.</span></span>|  
|<span data-ttu-id="34f7b-131">Collapsed</span><span class="sxs-lookup"><span data-stu-id="34f7b-131">Collapsed</span></span>|<span data-ttu-id="34f7b-132">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="34f7b-132">ExpansionStates</span></span>|<span data-ttu-id="34f7b-133">控件未展开。</span><span class="sxs-lookup"><span data-stu-id="34f7b-133">The control is not expanded.</span></span>|  
|<span data-ttu-id="34f7b-134">ExpandDown</span><span class="sxs-lookup"><span data-stu-id="34f7b-134">ExpandDown</span></span>|<span data-ttu-id="34f7b-135">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="34f7b-135">ExpandDirectionStates</span></span>|<span data-ttu-id="34f7b-136">控件向下扩展。</span><span class="sxs-lookup"><span data-stu-id="34f7b-136">The control expands down.</span></span>|  
|<span data-ttu-id="34f7b-137">ExpandUp</span><span class="sxs-lookup"><span data-stu-id="34f7b-137">ExpandUp</span></span>|<span data-ttu-id="34f7b-138">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="34f7b-138">ExpandDirectionStates</span></span>|<span data-ttu-id="34f7b-139">控件展开。</span><span class="sxs-lookup"><span data-stu-id="34f7b-139">The control expands up.</span></span>|  
|<span data-ttu-id="34f7b-140">ExpandLeft</span><span class="sxs-lookup"><span data-stu-id="34f7b-140">ExpandLeft</span></span>|<span data-ttu-id="34f7b-141">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="34f7b-141">ExpandDirectionStates</span></span>|<span data-ttu-id="34f7b-142">控件向左扩展。</span><span class="sxs-lookup"><span data-stu-id="34f7b-142">The control expands left.</span></span>|  
|<span data-ttu-id="34f7b-143">ExpandRight</span><span class="sxs-lookup"><span data-stu-id="34f7b-143">ExpandRight</span></span>|<span data-ttu-id="34f7b-144">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="34f7b-144">ExpandDirectionStates</span></span>|<span data-ttu-id="34f7b-145">控件向右展开。</span><span class="sxs-lookup"><span data-stu-id="34f7b-145">The control expands right.</span></span>|  
|<span data-ttu-id="34f7b-146">有效</span><span class="sxs-lookup"><span data-stu-id="34f7b-146">Valid</span></span>|<span data-ttu-id="34f7b-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="34f7b-147">ValidationStates</span></span>|<span data-ttu-id="34f7b-148">控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="34f7b-148">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="34f7b-149">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="34f7b-149">InvalidFocused</span></span>|<span data-ttu-id="34f7b-150">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="34f7b-150">ValidationStates</span></span>|<span data-ttu-id="34f7b-151"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="34f7b-151">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="34f7b-152">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="34f7b-152">InvalidUnfocused</span></span>|<span data-ttu-id="34f7b-153">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="34f7b-153">ValidationStates</span></span>|<span data-ttu-id="34f7b-154"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="34f7b-154">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="expander-controltemplate-example"></a><span data-ttu-id="34f7b-155">扩展器 System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="34f7b-155">Expander ControlTemplate Example</span></span>  
 <span data-ttu-id="34f7b-156">下面的示例演示如何为控件定义 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Expander> 。</span><span class="sxs-lookup"><span data-stu-id="34f7b-156">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Expander](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/expander.xaml#expander)]  
  
 <span data-ttu-id="34f7b-157">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="34f7b-157">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="34f7b-158">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="34f7b-158">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34f7b-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="34f7b-159">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="34f7b-160">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="34f7b-160">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="34f7b-161">控件自定义</span><span class="sxs-lookup"><span data-stu-id="34f7b-161">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="34f7b-162">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="34f7b-162">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="34f7b-163">创建控件模板</span><span class="sxs-lookup"><span data-stu-id="34f7b-163">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
