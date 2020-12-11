---
title: ContextMenu 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], ContextMenu
- parts [WPF], ContextMenu
- ContextMenu [WPF], styles and templates
- styles [WPF], ContextMenu
- ControlTemplate [WPF], ContextMenu
- states [WPF], ContextMenu
ms.assetid: 342d1f17-c406-4f94-8f55-867c5f3ea511
ms.openlocfilehash: 0f168c440c804c543ee9923d0021677ac529d5e1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973242"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="1c279-102">ContextMenu 样式和模板</span><span class="sxs-lookup"><span data-stu-id="1c279-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="1c279-103">本主题描述控件的样式和模板 <xref:System.Windows.Controls.ContextMenu> 。</span><span class="sxs-lookup"><span data-stu-id="1c279-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="1c279-104">您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。</span><span class="sxs-lookup"><span data-stu-id="1c279-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="1c279-105">有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。</span><span class="sxs-lookup"><span data-stu-id="1c279-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="1c279-106">ContextMenu 部件</span><span class="sxs-lookup"><span data-stu-id="1c279-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="1c279-107"><xref:System.Windows.Controls.ContextMenu>控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="1c279-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="1c279-108">为创建时 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.ContextMenu> ，模板可能包含 <xref:System.Windows.Controls.ItemsPresenter> 内的 <xref:System.Windows.Controls.ScrollViewer> 。</span><span class="sxs-lookup"><span data-stu-id="1c279-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="1c279-109"> (<xref:System.Windows.Controls.ItemsPresenter> 显示中的每一项，则在 <xref:System.Windows.Controls.ContextMenu> <xref:System.Windows.Controls.ScrollViewer> 控件内启用滚动) 。</span><span class="sxs-lookup"><span data-stu-id="1c279-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="1c279-110">如果不 <xref:System.Windows.Controls.ItemsPresenter> 是的直接子级 <xref:System.Windows.Controls.ScrollViewer> ，则必须指定 <xref:System.Windows.Controls.ItemsPresenter> 名称 `ItemsPresenter` 。</span><span class="sxs-lookup"><span data-stu-id="1c279-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="1c279-111">ContextMenu 状态</span><span class="sxs-lookup"><span data-stu-id="1c279-111">ContextMenu States</span></span>  
 <span data-ttu-id="1c279-112">下表列出了控件的可视状态 <xref:System.Windows.Controls.ContextMenu> 。</span><span class="sxs-lookup"><span data-stu-id="1c279-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="1c279-113">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="1c279-113">VisualState Name</span></span>|<span data-ttu-id="1c279-114">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="1c279-114">VisualStateGroup Name</span></span>|<span data-ttu-id="1c279-115">描述</span><span class="sxs-lookup"><span data-stu-id="1c279-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1c279-116">有效</span><span class="sxs-lookup"><span data-stu-id="1c279-116">Valid</span></span>|<span data-ttu-id="1c279-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1c279-117">ValidationStates</span></span>|<span data-ttu-id="1c279-118">控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="1c279-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="1c279-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="1c279-119">InvalidFocused</span></span>|<span data-ttu-id="1c279-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1c279-120">ValidationStates</span></span>|<span data-ttu-id="1c279-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="1c279-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="1c279-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="1c279-122">InvalidUnfocused</span></span>|<span data-ttu-id="1c279-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1c279-123">ValidationStates</span></span>|<span data-ttu-id="1c279-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="1c279-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="1c279-125">ContextMenu System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="1c279-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="1c279-126">下面的示例演示如何为控件定义 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.ContextMenu> 。</span><span class="sxs-lookup"><span data-stu-id="1c279-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="1c279-127"><xref:System.Windows.Controls.ControlTemplate>使用以下资源。</span><span class="sxs-lookup"><span data-stu-id="1c279-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="1c279-128">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="1c279-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c279-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c279-129">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="1c279-130">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="1c279-130">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="1c279-131">控件自定义</span><span class="sxs-lookup"><span data-stu-id="1c279-131">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="1c279-132">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="1c279-132">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="1c279-133">创建控件模板</span><span class="sxs-lookup"><span data-stu-id="1c279-133">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
