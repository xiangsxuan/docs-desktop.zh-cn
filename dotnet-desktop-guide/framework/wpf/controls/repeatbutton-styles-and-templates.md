---
title: RepeatButton 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatButton [WPF], styles and templates
- styles [WPF], RepeatButton
- templates [WPF], RepeatButton
- parts [WPF], RepeatButton
- ControlTemplate [WPF], RepeatButton
- states [WPF], RepeatButton
ms.assetid: fd340743-f44f-4990-9077-085301469670
ms.openlocfilehash: cff73c4c7ff06ad6d7b602ff1c6b9b38a4396509
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973804"
---
# <a name="repeatbutton-styles-and-templates"></a><span data-ttu-id="6fdb7-102">RepeatButton 样式和模板</span><span class="sxs-lookup"><span data-stu-id="6fdb7-102">RepeatButton Styles and Templates</span></span>

<span data-ttu-id="6fdb7-103">本主题描述控件的样式和模板 <xref:System.Windows.Controls.Primitives.RepeatButton> 。</span><span class="sxs-lookup"><span data-stu-id="6fdb7-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="6fdb7-104">您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。</span><span class="sxs-lookup"><span data-stu-id="6fdb7-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="6fdb7-105">有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。</span><span class="sxs-lookup"><span data-stu-id="6fdb7-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>

## <a name="repeatbutton-parts"></a><span data-ttu-id="6fdb7-106">RepeatButton 部件</span><span class="sxs-lookup"><span data-stu-id="6fdb7-106">RepeatButton Parts</span></span>

<span data-ttu-id="6fdb7-107"><xref:System.Windows.Controls.Primitives.RepeatButton>控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="6fdb7-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>

## <a name="repeatbutton-states"></a><span data-ttu-id="6fdb7-108">RepeatButton 状态</span><span class="sxs-lookup"><span data-stu-id="6fdb7-108">RepeatButton States</span></span>

<span data-ttu-id="6fdb7-109">下表列出了控件的可视状态 <xref:System.Windows.Controls.Primitives.RepeatButton> 。</span><span class="sxs-lookup"><span data-stu-id="6fdb7-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

|<span data-ttu-id="6fdb7-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="6fdb7-110">VisualState Name</span></span>|<span data-ttu-id="6fdb7-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="6fdb7-111">VisualStateGroup Name</span></span>|<span data-ttu-id="6fdb7-112">描述</span><span class="sxs-lookup"><span data-stu-id="6fdb7-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="6fdb7-113">普通</span><span class="sxs-lookup"><span data-stu-id="6fdb7-113">Normal</span></span>|<span data-ttu-id="6fdb7-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6fdb7-114">CommonStates</span></span>|<span data-ttu-id="6fdb7-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="6fdb7-115">The default state.</span></span>|
|<span data-ttu-id="6fdb7-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="6fdb7-116">MouseOver</span></span>|<span data-ttu-id="6fdb7-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6fdb7-117">CommonStates</span></span>|<span data-ttu-id="6fdb7-118">鼠标指针悬停在控件上方。</span><span class="sxs-lookup"><span data-stu-id="6fdb7-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="6fdb7-119">已按下</span><span class="sxs-lookup"><span data-stu-id="6fdb7-119">Pressed</span></span>|<span data-ttu-id="6fdb7-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6fdb7-120">CommonStates</span></span>|<span data-ttu-id="6fdb7-121">已按下控件。</span><span class="sxs-lookup"><span data-stu-id="6fdb7-121">The control is pressed.</span></span>|
|<span data-ttu-id="6fdb7-122">已禁用</span><span class="sxs-lookup"><span data-stu-id="6fdb7-122">Disabled</span></span>|<span data-ttu-id="6fdb7-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6fdb7-123">CommonStates</span></span>|<span data-ttu-id="6fdb7-124">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="6fdb7-124">The control is disabled.</span></span>|
|<span data-ttu-id="6fdb7-125">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="6fdb7-125">Focused</span></span>|<span data-ttu-id="6fdb7-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="6fdb7-126">FocusStates</span></span>|<span data-ttu-id="6fdb7-127">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="6fdb7-127">The control has focus.</span></span>|
|<span data-ttu-id="6fdb7-128">失去焦点</span><span class="sxs-lookup"><span data-stu-id="6fdb7-128">Unfocused</span></span>|<span data-ttu-id="6fdb7-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="6fdb7-129">FocusStates</span></span>|<span data-ttu-id="6fdb7-130">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="6fdb7-130">The control does not have focus.</span></span>|
|<span data-ttu-id="6fdb7-131">有效</span><span class="sxs-lookup"><span data-stu-id="6fdb7-131">Valid</span></span>|<span data-ttu-id="6fdb7-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6fdb7-132">ValidationStates</span></span>|<span data-ttu-id="6fdb7-133">控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="6fdb7-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="6fdb7-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="6fdb7-134">InvalidFocused</span></span>|<span data-ttu-id="6fdb7-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6fdb7-135">ValidationStates</span></span>|<span data-ttu-id="6fdb7-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="6fdb7-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="6fdb7-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="6fdb7-137">InvalidUnfocused</span></span>|<span data-ttu-id="6fdb7-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6fdb7-138">ValidationStates</span></span>|<span data-ttu-id="6fdb7-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="6fdb7-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="6fdb7-140">RepeatButton System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="6fdb7-140">RepeatButton ControlTemplate Example</span></span>

<span data-ttu-id="6fdb7-141">下面的示例演示如何为控件定义 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Primitives.RepeatButton> 。</span><span class="sxs-lookup"><span data-stu-id="6fdb7-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#RepeatButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]

<span data-ttu-id="6fdb7-142">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="6fdb7-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="6fdb7-143">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="6fdb7-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="6fdb7-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="6fdb7-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="6fdb7-145">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="6fdb7-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="6fdb7-146">控件自定义</span><span class="sxs-lookup"><span data-stu-id="6fdb7-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="6fdb7-147">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="6fdb7-147">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="6fdb7-148">创建控件模板</span><span class="sxs-lookup"><span data-stu-id="6fdb7-148">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
