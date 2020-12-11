---
title: Thumb 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Thumb
- styles [WPF], Thumb
- templates [WPF], Thumb
- Thumb [WPF], styles and templates
- ControlTemplate [WPF], Thumb
- parts [WPF], Thumb
ms.assetid: 86a49235-62d9-414e-923e-53126e3f930a
ms.openlocfilehash: 6c14280f9514e3c9b1716b55410a46cf843f6b8c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970440"
---
# <a name="thumb-styles-and-templates"></a><span data-ttu-id="faa35-102">Thumb 样式和模板</span><span class="sxs-lookup"><span data-stu-id="faa35-102">Thumb Styles and Templates</span></span>

<span data-ttu-id="faa35-103">本主题描述控件的样式和模板 <xref:System.Windows.Controls.Primitives.Thumb> 。</span><span class="sxs-lookup"><span data-stu-id="faa35-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="faa35-104">您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。</span><span class="sxs-lookup"><span data-stu-id="faa35-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="faa35-105">有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。</span><span class="sxs-lookup"><span data-stu-id="faa35-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>

## <a name="thumb-parts"></a><span data-ttu-id="faa35-106">拇指部分</span><span class="sxs-lookup"><span data-stu-id="faa35-106">Thumb Parts</span></span>

<span data-ttu-id="faa35-107"><xref:System.Windows.Controls.Primitives.Thumb>控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="faa35-107">The <xref:System.Windows.Controls.Primitives.Thumb> control does not have any named parts.</span></span>

## <a name="thumb-states"></a><span data-ttu-id="faa35-108">缩略图状态</span><span class="sxs-lookup"><span data-stu-id="faa35-108">Thumb States</span></span>

<span data-ttu-id="faa35-109">下表列出了控件的可视状态 <xref:System.Windows.Controls.Primitives.Thumb> 。</span><span class="sxs-lookup"><span data-stu-id="faa35-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

|<span data-ttu-id="faa35-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="faa35-110">VisualState Name</span></span>|<span data-ttu-id="faa35-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="faa35-111">VisualStateGroup Name</span></span>|<span data-ttu-id="faa35-112">描述</span><span class="sxs-lookup"><span data-stu-id="faa35-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="faa35-113">普通</span><span class="sxs-lookup"><span data-stu-id="faa35-113">Normal</span></span>|<span data-ttu-id="faa35-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="faa35-114">CommonStates</span></span>|<span data-ttu-id="faa35-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="faa35-115">The default state.</span></span>|
|<span data-ttu-id="faa35-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="faa35-116">MouseOver</span></span>|<span data-ttu-id="faa35-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="faa35-117">CommonStates</span></span>|<span data-ttu-id="faa35-118">鼠标指针悬停在控件上方。</span><span class="sxs-lookup"><span data-stu-id="faa35-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="faa35-119">已按下</span><span class="sxs-lookup"><span data-stu-id="faa35-119">Pressed</span></span>|<span data-ttu-id="faa35-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="faa35-120">CommonStates</span></span>|<span data-ttu-id="faa35-121">已按下控件。</span><span class="sxs-lookup"><span data-stu-id="faa35-121">The control is pressed.</span></span>|
|<span data-ttu-id="faa35-122">已禁用</span><span class="sxs-lookup"><span data-stu-id="faa35-122">Disabled</span></span>|<span data-ttu-id="faa35-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="faa35-123">CommonStates</span></span>|<span data-ttu-id="faa35-124">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="faa35-124">The control is disabled.</span></span>|
|<span data-ttu-id="faa35-125">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="faa35-125">Focused</span></span>|<span data-ttu-id="faa35-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="faa35-126">FocusStates</span></span>|<span data-ttu-id="faa35-127">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="faa35-127">The control has focus.</span></span>|
|<span data-ttu-id="faa35-128">失去焦点</span><span class="sxs-lookup"><span data-stu-id="faa35-128">Unfocused</span></span>|<span data-ttu-id="faa35-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="faa35-129">FocusStates</span></span>|<span data-ttu-id="faa35-130">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="faa35-130">The control does not have focus.</span></span>|
|<span data-ttu-id="faa35-131">有效</span><span class="sxs-lookup"><span data-stu-id="faa35-131">Valid</span></span>|<span data-ttu-id="faa35-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="faa35-132">ValidationStates</span></span>|<span data-ttu-id="faa35-133">控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="faa35-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="faa35-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="faa35-134">InvalidFocused</span></span>|<span data-ttu-id="faa35-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="faa35-135">ValidationStates</span></span>|<span data-ttu-id="faa35-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="faa35-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="faa35-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="faa35-137">InvalidUnfocused</span></span>|<span data-ttu-id="faa35-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="faa35-138">ValidationStates</span></span>|<span data-ttu-id="faa35-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="faa35-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="thumb-controltemplate-example"></a><span data-ttu-id="faa35-140">Thumb System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="faa35-140">Thumb ControlTemplate Example</span></span>

<span data-ttu-id="faa35-141">下面的示例演示如何为控件定义 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Primitives.Thumb> 。</span><span class="sxs-lookup"><span data-stu-id="faa35-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

[!code-xaml[ControlTemplateExamples#Thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]

<span data-ttu-id="faa35-142">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="faa35-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="faa35-143">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="faa35-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="faa35-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="faa35-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="faa35-145">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="faa35-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="faa35-146">控件自定义</span><span class="sxs-lookup"><span data-stu-id="faa35-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="faa35-147">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="faa35-147">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="faa35-148">创建控件模板</span><span class="sxs-lookup"><span data-stu-id="faa35-148">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
