---
title: PasswordBox 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
ms.openlocfilehash: aecd625a052f097aeb2b8cb73743fd4b47df89e1
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970465"
---
# <a name="passwordbox-styles-and-templates"></a><span data-ttu-id="fbf59-102">PasswordBox 样式和模板</span><span class="sxs-lookup"><span data-stu-id="fbf59-102">PasswordBox Styles and Templates</span></span>

<span data-ttu-id="fbf59-103">本主题描述控件的样式和模板 <xref:System.Windows.Controls.PasswordBox> 。</span><span class="sxs-lookup"><span data-stu-id="fbf59-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="fbf59-104">您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。</span><span class="sxs-lookup"><span data-stu-id="fbf59-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="fbf59-105">有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。</span><span class="sxs-lookup"><span data-stu-id="fbf59-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>

## <a name="passwordbox-parts"></a><span data-ttu-id="fbf59-106">PasswordBox 部件</span><span class="sxs-lookup"><span data-stu-id="fbf59-106">PasswordBox Parts</span></span>

<span data-ttu-id="fbf59-107">下表列出了控件的已命名部件 <xref:System.Windows.Controls.PasswordBox> 。</span><span class="sxs-lookup"><span data-stu-id="fbf59-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="fbf59-108">组成部分</span><span class="sxs-lookup"><span data-stu-id="fbf59-108">Part</span></span>|<span data-ttu-id="fbf59-109">类型</span><span class="sxs-lookup"><span data-stu-id="fbf59-109">Type</span></span>|<span data-ttu-id="fbf59-110">说明</span><span class="sxs-lookup"><span data-stu-id="fbf59-110">Description</span></span>|
|-|-|-|
|<span data-ttu-id="fbf59-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="fbf59-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="fbf59-112">一个可包含的可视元素 <xref:System.Windows.FrameworkElement> 。</span><span class="sxs-lookup"><span data-stu-id="fbf59-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="fbf59-113">的文本 <xref:System.Windows.Controls.PasswordBox> 显示在此元素中。</span><span class="sxs-lookup"><span data-stu-id="fbf59-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|

## <a name="passwordbox-states"></a><span data-ttu-id="fbf59-114">PasswordBox 状态</span><span class="sxs-lookup"><span data-stu-id="fbf59-114">PasswordBox States</span></span>

<span data-ttu-id="fbf59-115">下表列出了控件的可视状态 <xref:System.Windows.Controls.PasswordBox> 。</span><span class="sxs-lookup"><span data-stu-id="fbf59-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="fbf59-116">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="fbf59-116">VisualState Name</span></span>|<span data-ttu-id="fbf59-117">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="fbf59-117">VisualStateGroup Name</span></span>|<span data-ttu-id="fbf59-118">描述</span><span class="sxs-lookup"><span data-stu-id="fbf59-118">Description</span></span>|
|-|-|-|
|<span data-ttu-id="fbf59-119">普通</span><span class="sxs-lookup"><span data-stu-id="fbf59-119">Normal</span></span>|<span data-ttu-id="fbf59-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fbf59-120">CommonStates</span></span>|<span data-ttu-id="fbf59-121">默认状态。</span><span class="sxs-lookup"><span data-stu-id="fbf59-121">The default state.</span></span>|
|<span data-ttu-id="fbf59-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="fbf59-122">MouseOver</span></span>|<span data-ttu-id="fbf59-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fbf59-123">CommonStates</span></span>|<span data-ttu-id="fbf59-124">鼠标指针悬停在控件上方。</span><span class="sxs-lookup"><span data-stu-id="fbf59-124">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="fbf59-125">已禁用</span><span class="sxs-lookup"><span data-stu-id="fbf59-125">Disabled</span></span>|<span data-ttu-id="fbf59-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fbf59-126">CommonStates</span></span>|<span data-ttu-id="fbf59-127">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="fbf59-127">The control is disabled.</span></span>|
|<span data-ttu-id="fbf59-128">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="fbf59-128">Focused</span></span>|<span data-ttu-id="fbf59-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="fbf59-129">FocusStates</span></span>|<span data-ttu-id="fbf59-130">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="fbf59-130">The control has focus.</span></span>|
|<span data-ttu-id="fbf59-131">失去焦点</span><span class="sxs-lookup"><span data-stu-id="fbf59-131">Unfocused</span></span>|<span data-ttu-id="fbf59-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="fbf59-132">FocusStates</span></span>|<span data-ttu-id="fbf59-133">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="fbf59-133">The control does not have focus.</span></span>|
|<span data-ttu-id="fbf59-134">有效</span><span class="sxs-lookup"><span data-stu-id="fbf59-134">Valid</span></span>|<span data-ttu-id="fbf59-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fbf59-135">ValidationStates</span></span>|<span data-ttu-id="fbf59-136">控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="fbf59-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="fbf59-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="fbf59-137">InvalidFocused</span></span>|<span data-ttu-id="fbf59-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fbf59-138">ValidationStates</span></span>|<span data-ttu-id="fbf59-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="fbf59-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="fbf59-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="fbf59-140">InvalidUnfocused</span></span>|<span data-ttu-id="fbf59-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fbf59-141">ValidationStates</span></span>|<span data-ttu-id="fbf59-142"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="fbf59-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="fbf59-143">PasswordBox System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="fbf59-143">PasswordBox ControlTemplate Example</span></span>

<span data-ttu-id="fbf59-144">下面的示例演示如何为控件定义 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.PasswordBox> 。</span><span class="sxs-lookup"><span data-stu-id="fbf59-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

<span data-ttu-id="fbf59-145">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="fbf59-145">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="fbf59-146">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="fbf59-146">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="fbf59-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbf59-147">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="fbf59-148">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="fbf59-148">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="fbf59-149">控件自定义</span><span class="sxs-lookup"><span data-stu-id="fbf59-149">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="fbf59-150">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="fbf59-150">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="fbf59-151">创建控件模板</span><span class="sxs-lookup"><span data-stu-id="fbf59-151">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
