---
title: ToolBar 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToolBar
- styles [WPF], ToolBar
- ControlTemplate [WPF], ToolBar
- parts [WPF], ToolBar
- ToolBar [WPF], styles and templates
- templates [WPF], ToolBar
ms.assetid: bd875f46-4690-46f5-81e0-f11a9822484f
ms.openlocfilehash: 1ece74e1c4aa1be9845bd812b29f2ad7f580d4e2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972928"
---
# <a name="toolbar-styles-and-templates"></a><span data-ttu-id="3a8ea-102">ToolBar 样式和模板</span><span class="sxs-lookup"><span data-stu-id="3a8ea-102">ToolBar Styles and Templates</span></span>
<span data-ttu-id="3a8ea-103">本主题描述控件的样式和模板 <xref:System.Windows.Controls.ToolBar> 。</span><span class="sxs-lookup"><span data-stu-id="3a8ea-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolBar> control.</span></span> <span data-ttu-id="3a8ea-104">您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。</span><span class="sxs-lookup"><span data-stu-id="3a8ea-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="3a8ea-105">有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。</span><span class="sxs-lookup"><span data-stu-id="3a8ea-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="toolbar-parts"></a><span data-ttu-id="3a8ea-106">工具栏部件</span><span class="sxs-lookup"><span data-stu-id="3a8ea-106">ToolBar Parts</span></span>  
 <span data-ttu-id="3a8ea-107">下表列出了控件的已命名部件 <xref:System.Windows.Controls.ToolBar> 。</span><span class="sxs-lookup"><span data-stu-id="3a8ea-107">The following table lists the named parts for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="3a8ea-108">组成部分</span><span class="sxs-lookup"><span data-stu-id="3a8ea-108">Part</span></span>|<span data-ttu-id="3a8ea-109">类型</span><span class="sxs-lookup"><span data-stu-id="3a8ea-109">Type</span></span>|<span data-ttu-id="3a8ea-110">描述</span><span class="sxs-lookup"><span data-stu-id="3a8ea-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="3a8ea-111">PART_ToolBarPanel</span><span class="sxs-lookup"><span data-stu-id="3a8ea-111">PART_ToolBarPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|<span data-ttu-id="3a8ea-112">包含上的控件的对象 <xref:System.Windows.Controls.ToolBar> 。</span><span class="sxs-lookup"><span data-stu-id="3a8ea-112">The object that contains the controls on the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
|<span data-ttu-id="3a8ea-113">PART_ToolBarOverflowPanel</span><span class="sxs-lookup"><span data-stu-id="3a8ea-113">PART_ToolBarOverflowPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|<span data-ttu-id="3a8ea-114">对象，包含位于的溢出区中的控件 <xref:System.Windows.Controls.ToolBar> 。</span><span class="sxs-lookup"><span data-stu-id="3a8ea-114">The object that contains the controls that are in the overflow area of the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
  
 <span data-ttu-id="3a8ea-115">为创建时 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.ToolBar> ，模板可能包含 <xref:System.Windows.Controls.ItemsPresenter> 内的 <xref:System.Windows.Controls.ScrollViewer> 。</span><span class="sxs-lookup"><span data-stu-id="3a8ea-115">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ToolBar>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="3a8ea-116"> (<xref:System.Windows.Controls.ItemsPresenter> 显示中的每一项，则在 <xref:System.Windows.Controls.ToolBar> <xref:System.Windows.Controls.ScrollViewer> 控件内启用滚动) 。</span><span class="sxs-lookup"><span data-stu-id="3a8ea-116">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ToolBar>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="3a8ea-117">如果不 <xref:System.Windows.Controls.ItemsPresenter> 是的直接子级 <xref:System.Windows.Controls.ScrollViewer> ，则必须指定 <xref:System.Windows.Controls.ItemsPresenter> 名称 `ItemsPresenter` 。</span><span class="sxs-lookup"><span data-stu-id="3a8ea-117">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="toolbar-states"></a><span data-ttu-id="3a8ea-118">工具栏状态</span><span class="sxs-lookup"><span data-stu-id="3a8ea-118">ToolBar States</span></span>  
 <span data-ttu-id="3a8ea-119">下表列出了控件的可视状态 <xref:System.Windows.Controls.ToolBar> 。</span><span class="sxs-lookup"><span data-stu-id="3a8ea-119">The following table lists the visual states for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="3a8ea-120">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="3a8ea-120">VisualState Name</span></span>|<span data-ttu-id="3a8ea-121">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="3a8ea-121">VisualStateGroup Name</span></span>|<span data-ttu-id="3a8ea-122">描述</span><span class="sxs-lookup"><span data-stu-id="3a8ea-122">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="3a8ea-123">有效</span><span class="sxs-lookup"><span data-stu-id="3a8ea-123">Valid</span></span>|<span data-ttu-id="3a8ea-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3a8ea-124">ValidationStates</span></span>|<span data-ttu-id="3a8ea-125">控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="3a8ea-125">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="3a8ea-126">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="3a8ea-126">InvalidFocused</span></span>|<span data-ttu-id="3a8ea-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3a8ea-127">ValidationStates</span></span>|<span data-ttu-id="3a8ea-128"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="3a8ea-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="3a8ea-129">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="3a8ea-129">InvalidUnfocused</span></span>|<span data-ttu-id="3a8ea-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3a8ea-130">ValidationStates</span></span>|<span data-ttu-id="3a8ea-131"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="3a8ea-131">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="toolbar-controltemplate-example"></a><span data-ttu-id="3a8ea-132">工具栏 System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="3a8ea-132">ToolBar ControlTemplate Example</span></span>  
 <span data-ttu-id="3a8ea-133">下面的示例演示如何为控件定义 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.ToolBar> 。</span><span class="sxs-lookup"><span data-stu-id="3a8ea-133">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 <span data-ttu-id="3a8ea-134">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="3a8ea-134">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="3a8ea-135">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="3a8ea-135">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a8ea-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a8ea-136">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="3a8ea-137">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="3a8ea-137">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="3a8ea-138">控件自定义</span><span class="sxs-lookup"><span data-stu-id="3a8ea-138">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="3a8ea-139">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="3a8ea-139">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="3a8ea-140">创建控件模板</span><span class="sxs-lookup"><span data-stu-id="3a8ea-140">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
