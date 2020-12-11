---
title: ScrollBar 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ScrollBar
- ControlTemplate [WPF], ScrollBar
- states [WPF], ScrollBar
- ScrollBar [WPF], styles and templates
- templates [WPF], ScrollBar
- parts [WPF], ScrollBar
ms.assetid: 066ea45a-e27d-43b0-adfe-cce6934c22f5
ms.openlocfilehash: 4c4a0e4eeb6d9d58470973dc8ae1877b8fef9bde
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972983"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="fd5ca-102">ScrollBar 样式和模板</span><span class="sxs-lookup"><span data-stu-id="fd5ca-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="fd5ca-103">本主题描述控件的样式和模板 <xref:System.Windows.Controls.Primitives.ScrollBar> 。</span><span class="sxs-lookup"><span data-stu-id="fd5ca-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="fd5ca-104">您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。</span><span class="sxs-lookup"><span data-stu-id="fd5ca-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="fd5ca-105">有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。</span><span class="sxs-lookup"><span data-stu-id="fd5ca-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="fd5ca-106">滚动条部件</span><span class="sxs-lookup"><span data-stu-id="fd5ca-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="fd5ca-107">下表列出了控件的已命名部件 <xref:System.Windows.Controls.Primitives.ScrollBar> 。</span><span class="sxs-lookup"><span data-stu-id="fd5ca-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="fd5ca-108">组成部分</span><span class="sxs-lookup"><span data-stu-id="fd5ca-108">Part</span></span>|<span data-ttu-id="fd5ca-109">类型</span><span class="sxs-lookup"><span data-stu-id="fd5ca-109">Type</span></span>|<span data-ttu-id="fd5ca-110">描述</span><span class="sxs-lookup"><span data-stu-id="fd5ca-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="fd5ca-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="fd5ca-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="fd5ca-112">指示的位置的元素的容器 <xref:System.Windows.Controls.Primitives.ScrollBar> 。</span><span class="sxs-lookup"><span data-stu-id="fd5ca-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="fd5ca-113">滚动条状态</span><span class="sxs-lookup"><span data-stu-id="fd5ca-113">ScrollBar States</span></span>  
 <span data-ttu-id="fd5ca-114">下表列出了控件的可视状态 <xref:System.Windows.Controls.Primitives.ScrollBar> 。</span><span class="sxs-lookup"><span data-stu-id="fd5ca-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="fd5ca-115">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="fd5ca-115">VisualState Name</span></span>|<span data-ttu-id="fd5ca-116">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="fd5ca-116">VisualStateGroup Name</span></span>|<span data-ttu-id="fd5ca-117">描述</span><span class="sxs-lookup"><span data-stu-id="fd5ca-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="fd5ca-118">普通</span><span class="sxs-lookup"><span data-stu-id="fd5ca-118">Normal</span></span>|<span data-ttu-id="fd5ca-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fd5ca-119">CommonStates</span></span>|<span data-ttu-id="fd5ca-120">默认状态。</span><span class="sxs-lookup"><span data-stu-id="fd5ca-120">The default state.</span></span>|  
|<span data-ttu-id="fd5ca-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="fd5ca-121">MouseOver</span></span>|<span data-ttu-id="fd5ca-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fd5ca-122">CommonStates</span></span>|<span data-ttu-id="fd5ca-123">鼠标指针悬停在控件上方。</span><span class="sxs-lookup"><span data-stu-id="fd5ca-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="fd5ca-124">已禁用</span><span class="sxs-lookup"><span data-stu-id="fd5ca-124">Disabled</span></span>|<span data-ttu-id="fd5ca-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fd5ca-125">CommonStates</span></span>|<span data-ttu-id="fd5ca-126">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="fd5ca-126">The control is disabled.</span></span>|  
|<span data-ttu-id="fd5ca-127">有效</span><span class="sxs-lookup"><span data-stu-id="fd5ca-127">Valid</span></span>|<span data-ttu-id="fd5ca-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fd5ca-128">ValidationStates</span></span>|<span data-ttu-id="fd5ca-129">控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="fd5ca-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="fd5ca-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="fd5ca-130">InvalidFocused</span></span>|<span data-ttu-id="fd5ca-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fd5ca-131">ValidationStates</span></span>|<span data-ttu-id="fd5ca-132"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性为 `true` ，并且控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="fd5ca-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="fd5ca-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="fd5ca-133">InvalidUnfocused</span></span>|<span data-ttu-id="fd5ca-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fd5ca-134">ValidationStates</span></span>|<span data-ttu-id="fd5ca-135"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性为 `true` ，并且该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="fd5ca-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="fd5ca-136">滚动条 System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="fd5ca-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="fd5ca-137">下面的示例演示如何为控件定义 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Primitives.ScrollBar> 。</span><span class="sxs-lookup"><span data-stu-id="fd5ca-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="fd5ca-138">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="fd5ca-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="fd5ca-139">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="fd5ca-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd5ca-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd5ca-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="fd5ca-141">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="fd5ca-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="fd5ca-142">控件自定义</span><span class="sxs-lookup"><span data-stu-id="fd5ca-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="fd5ca-143">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="fd5ca-143">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="fd5ca-144">创建控件模板</span><span class="sxs-lookup"><span data-stu-id="fd5ca-144">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)