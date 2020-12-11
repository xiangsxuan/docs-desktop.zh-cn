---
title: CheckBox 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], CheckBox
- templates [WPF], CheckBox
- parts [WPF], CheckBox
- ControlTemplate [WPF], CheckBox
- CheckBox [WPF], styles and templates
- styles [WPF], CheckBox
ms.assetid: bfdaec96-d101-4d3d-864d-c27e6b621d03
ms.openlocfilehash: 7c8ece19cb2db95a7e6dabb1e3f3844f185136bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973258"
---
# <a name="checkbox-styles-and-templates"></a><span data-ttu-id="4e93f-102">CheckBox 样式和模板</span><span class="sxs-lookup"><span data-stu-id="4e93f-102">CheckBox Styles and Templates</span></span>
<span data-ttu-id="4e93f-103">本主题描述控件的样式和模板 <xref:System.Windows.Controls.CheckBox> 。</span><span class="sxs-lookup"><span data-stu-id="4e93f-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.CheckBox> control.</span></span> <span data-ttu-id="4e93f-104">您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。</span><span class="sxs-lookup"><span data-stu-id="4e93f-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4e93f-105">有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。</span><span class="sxs-lookup"><span data-stu-id="4e93f-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="checkbox-parts"></a><span data-ttu-id="4e93f-106">CheckBox 部分</span><span class="sxs-lookup"><span data-stu-id="4e93f-106">CheckBox Parts</span></span>  
 <span data-ttu-id="4e93f-107"><xref:System.Windows.Controls.CheckBox>控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="4e93f-107">The <xref:System.Windows.Controls.CheckBox> control does not have any named parts.</span></span>  
  
## <a name="checkbox-states"></a><span data-ttu-id="4e93f-108">复选框状态</span><span class="sxs-lookup"><span data-stu-id="4e93f-108">CheckBox States</span></span>  
 <span data-ttu-id="4e93f-109">下表列出了控件的可视状态 <xref:System.Windows.Controls.CheckBox> 。</span><span class="sxs-lookup"><span data-stu-id="4e93f-109">The following table lists the visual states for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
|<span data-ttu-id="4e93f-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="4e93f-110">VisualState Name</span></span>|<span data-ttu-id="4e93f-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="4e93f-111">VisualStateGroup Name</span></span>|<span data-ttu-id="4e93f-112">描述</span><span class="sxs-lookup"><span data-stu-id="4e93f-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="4e93f-113">普通</span><span class="sxs-lookup"><span data-stu-id="4e93f-113">Normal</span></span>|<span data-ttu-id="4e93f-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4e93f-114">CommonStates</span></span>|<span data-ttu-id="4e93f-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="4e93f-115">The default state.</span></span>|  
|<span data-ttu-id="4e93f-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="4e93f-116">MouseOver</span></span>|<span data-ttu-id="4e93f-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4e93f-117">CommonStates</span></span>|<span data-ttu-id="4e93f-118">鼠标指针悬停在控件上方。</span><span class="sxs-lookup"><span data-stu-id="4e93f-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="4e93f-119">已按下</span><span class="sxs-lookup"><span data-stu-id="4e93f-119">Pressed</span></span>|<span data-ttu-id="4e93f-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4e93f-120">CommonStates</span></span>|<span data-ttu-id="4e93f-121">已按下控件。</span><span class="sxs-lookup"><span data-stu-id="4e93f-121">The control is pressed.</span></span>|  
|<span data-ttu-id="4e93f-122">已禁用</span><span class="sxs-lookup"><span data-stu-id="4e93f-122">Disabled</span></span>|<span data-ttu-id="4e93f-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4e93f-123">CommonStates</span></span>|<span data-ttu-id="4e93f-124">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="4e93f-124">The control is disabled.</span></span>|  
|<span data-ttu-id="4e93f-125">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="4e93f-125">Focused</span></span>|<span data-ttu-id="4e93f-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="4e93f-126">FocusStates</span></span>|<span data-ttu-id="4e93f-127">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="4e93f-127">The control has focus.</span></span>|  
|<span data-ttu-id="4e93f-128">失去焦点</span><span class="sxs-lookup"><span data-stu-id="4e93f-128">Unfocused</span></span>|<span data-ttu-id="4e93f-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="4e93f-129">FocusStates</span></span>|<span data-ttu-id="4e93f-130">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="4e93f-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="4e93f-131">已选中</span><span class="sxs-lookup"><span data-stu-id="4e93f-131">Checked</span></span>|<span data-ttu-id="4e93f-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="4e93f-132">CheckStates</span></span>|<span data-ttu-id="4e93f-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `true`。</span><span class="sxs-lookup"><span data-stu-id="4e93f-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="4e93f-134">未选中</span><span class="sxs-lookup"><span data-stu-id="4e93f-134">Unchecked</span></span>|<span data-ttu-id="4e93f-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="4e93f-135">CheckStates</span></span>|<span data-ttu-id="4e93f-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `false`。</span><span class="sxs-lookup"><span data-stu-id="4e93f-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="4e93f-137">尚</span><span class="sxs-lookup"><span data-stu-id="4e93f-137">Indeterminate</span></span>|<span data-ttu-id="4e93f-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="4e93f-138">CheckStates</span></span>|<span data-ttu-id="4e93f-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> 为 `true` 且 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="4e93f-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="4e93f-140">有效</span><span class="sxs-lookup"><span data-stu-id="4e93f-140">Valid</span></span>|<span data-ttu-id="4e93f-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4e93f-141">ValidationStates</span></span>|<span data-ttu-id="4e93f-142">控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="4e93f-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="4e93f-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4e93f-143">InvalidUnfocused</span></span>|<span data-ttu-id="4e93f-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4e93f-144">ValidationStates</span></span>|<span data-ttu-id="4e93f-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="4e93f-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="4e93f-146">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4e93f-146">InvalidFocused</span></span>|<span data-ttu-id="4e93f-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4e93f-147">ValidationStates</span></span>|<span data-ttu-id="4e93f-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="4e93f-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="checkbox-controltemplate-example"></a><span data-ttu-id="4e93f-149">CheckBox System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="4e93f-149">CheckBox ControlTemplate Example</span></span>  
 <span data-ttu-id="4e93f-150">下面的示例演示如何为控件定义 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.CheckBox> 。</span><span class="sxs-lookup"><span data-stu-id="4e93f-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#CheckBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/checkbox.xaml#checkbox)]  
  
 <span data-ttu-id="4e93f-151">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="4e93f-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="4e93f-152">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="4e93f-152">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e93f-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e93f-153">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="4e93f-154">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="4e93f-154">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="4e93f-155">控件自定义</span><span class="sxs-lookup"><span data-stu-id="4e93f-155">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="4e93f-156">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="4e93f-156">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="4e93f-157">创建控件模板</span><span class="sxs-lookup"><span data-stu-id="4e93f-157">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)