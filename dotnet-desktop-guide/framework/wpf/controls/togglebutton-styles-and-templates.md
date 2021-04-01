---
title: ToggleButton 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: 2c5aee58878ea6199c07ee201882fd3ded97bdee
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972884"
---
# <a name="togglebutton-styles-and-templates"></a><span data-ttu-id="7ea93-102">ToggleButton 样式和模板</span><span class="sxs-lookup"><span data-stu-id="7ea93-102">ToggleButton Styles and Templates</span></span>

<span data-ttu-id="7ea93-103">本主题描述控件的样式和模板 <xref:System.Windows.Controls.Primitives.ToggleButton> 。</span><span class="sxs-lookup"><span data-stu-id="7ea93-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="7ea93-104">您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。</span><span class="sxs-lookup"><span data-stu-id="7ea93-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="7ea93-105">有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。</span><span class="sxs-lookup"><span data-stu-id="7ea93-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>

## <a name="togglebutton-parts"></a><span data-ttu-id="7ea93-106">切换按钮部件</span><span class="sxs-lookup"><span data-stu-id="7ea93-106">ToggleButton Parts</span></span>

<span data-ttu-id="7ea93-107"><xref:System.Windows.Controls.Primitives.ToggleButton>控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="7ea93-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>

## <a name="togglebutton-states"></a><span data-ttu-id="7ea93-108">切换按钮状态</span><span class="sxs-lookup"><span data-stu-id="7ea93-108">ToggleButton States</span></span>

<span data-ttu-id="7ea93-109">下表列出了控件的可视状态 <xref:System.Windows.Controls.Primitives.ToggleButton> 。</span><span class="sxs-lookup"><span data-stu-id="7ea93-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

|<span data-ttu-id="7ea93-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="7ea93-110">VisualState Name</span></span>|<span data-ttu-id="7ea93-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="7ea93-111">VisualStateGroup Name</span></span>|<span data-ttu-id="7ea93-112">描述</span><span class="sxs-lookup"><span data-stu-id="7ea93-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="7ea93-113">普通</span><span class="sxs-lookup"><span data-stu-id="7ea93-113">Normal</span></span>|<span data-ttu-id="7ea93-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7ea93-114">CommonStates</span></span>|<span data-ttu-id="7ea93-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="7ea93-115">The default state.</span></span>|
|<span data-ttu-id="7ea93-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="7ea93-116">MouseOver</span></span>|<span data-ttu-id="7ea93-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7ea93-117">CommonStates</span></span>|<span data-ttu-id="7ea93-118">鼠标指针悬停在控件上方。</span><span class="sxs-lookup"><span data-stu-id="7ea93-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="7ea93-119">已按下</span><span class="sxs-lookup"><span data-stu-id="7ea93-119">Pressed</span></span>|<span data-ttu-id="7ea93-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7ea93-120">CommonStates</span></span>|<span data-ttu-id="7ea93-121">已按下控件。</span><span class="sxs-lookup"><span data-stu-id="7ea93-121">The control is pressed.</span></span>|
|<span data-ttu-id="7ea93-122">已禁用</span><span class="sxs-lookup"><span data-stu-id="7ea93-122">Disabled</span></span>|<span data-ttu-id="7ea93-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7ea93-123">CommonStates</span></span>|<span data-ttu-id="7ea93-124">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="7ea93-124">The control is disabled.</span></span>|
|<span data-ttu-id="7ea93-125">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="7ea93-125">Focused</span></span>|<span data-ttu-id="7ea93-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="7ea93-126">FocusStates</span></span>|<span data-ttu-id="7ea93-127">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="7ea93-127">The control has focus.</span></span>|
|<span data-ttu-id="7ea93-128">失去焦点</span><span class="sxs-lookup"><span data-stu-id="7ea93-128">Unfocused</span></span>|<span data-ttu-id="7ea93-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="7ea93-129">FocusStates</span></span>|<span data-ttu-id="7ea93-130">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="7ea93-130">The control does not have focus.</span></span>|
|<span data-ttu-id="7ea93-131">已选中</span><span class="sxs-lookup"><span data-stu-id="7ea93-131">Checked</span></span>|<span data-ttu-id="7ea93-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="7ea93-132">CheckStates</span></span>|<span data-ttu-id="7ea93-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `true`。</span><span class="sxs-lookup"><span data-stu-id="7ea93-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|
|<span data-ttu-id="7ea93-134">未选中</span><span class="sxs-lookup"><span data-stu-id="7ea93-134">Unchecked</span></span>|<span data-ttu-id="7ea93-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="7ea93-135">CheckStates</span></span>|<span data-ttu-id="7ea93-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `false`。</span><span class="sxs-lookup"><span data-stu-id="7ea93-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|
|<span data-ttu-id="7ea93-137">尚</span><span class="sxs-lookup"><span data-stu-id="7ea93-137">Indeterminate</span></span>|<span data-ttu-id="7ea93-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="7ea93-138">CheckStates</span></span>|<span data-ttu-id="7ea93-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> 为 `true` 且 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="7ea93-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|
|<span data-ttu-id="7ea93-140">有效</span><span class="sxs-lookup"><span data-stu-id="7ea93-140">Valid</span></span>|<span data-ttu-id="7ea93-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7ea93-141">ValidationStates</span></span>|<span data-ttu-id="7ea93-142">控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="7ea93-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="7ea93-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="7ea93-143">InvalidFocused</span></span>|<span data-ttu-id="7ea93-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7ea93-144">ValidationStates</span></span>|<span data-ttu-id="7ea93-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性为 `true` ，并且控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="7ea93-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|
|<span data-ttu-id="7ea93-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="7ea93-146">InvalidUnfocused</span></span>|<span data-ttu-id="7ea93-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7ea93-147">ValidationStates</span></span>|<span data-ttu-id="7ea93-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性为 `true` ，并且该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="7ea93-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|

> [!NOTE]
> <span data-ttu-id="7ea93-149">如果控件模板中不存在不确定的视觉对象状态，则将使用未选中的视觉对象状态作为默认视觉对象状态。</span><span class="sxs-lookup"><span data-stu-id="7ea93-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>

## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="7ea93-150">切换按钮 System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="7ea93-150">ToggleButton ControlTemplate Example</span></span>

<span data-ttu-id="7ea93-151">下面的示例演示如何为控件定义 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Primitives.ToggleButton> 。</span><span class="sxs-lookup"><span data-stu-id="7ea93-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

<span data-ttu-id="7ea93-152">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="7ea93-152">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="7ea93-153">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="7ea93-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="7ea93-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ea93-154">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="7ea93-155">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="7ea93-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="7ea93-156">控件自定义</span><span class="sxs-lookup"><span data-stu-id="7ea93-156">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="7ea93-157">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="7ea93-157">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="7ea93-158">创建控件模板</span><span class="sxs-lookup"><span data-stu-id="7ea93-158">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
