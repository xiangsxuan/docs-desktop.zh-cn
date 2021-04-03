---
title: ScrollViewer 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ScrollViewer
- states [WPF], ScrollViewer
- styles [WPF], ScrollViewer
- templates [WPF], ScrollViewer
- ControlTemplate [WPF], ScrollViewer
- ScrollViewer [WPF], styles and templates
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
ms.openlocfilehash: a33e99ed31b9154bcfacde988bc38c3852331722
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971798"
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="f9a38-102">ScrollViewer 样式和模板</span><span class="sxs-lookup"><span data-stu-id="f9a38-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="f9a38-103">本主题描述控件的样式和模板 <xref:System.Windows.Controls.ScrollViewer> 。</span><span class="sxs-lookup"><span data-stu-id="f9a38-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="f9a38-104">您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。</span><span class="sxs-lookup"><span data-stu-id="f9a38-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="f9a38-105">有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。</span><span class="sxs-lookup"><span data-stu-id="f9a38-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="f9a38-106">ScrollViewer 部件</span><span class="sxs-lookup"><span data-stu-id="f9a38-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="f9a38-107">下表列出了控件的已命名部件 <xref:System.Windows.Controls.ScrollViewer> 。</span><span class="sxs-lookup"><span data-stu-id="f9a38-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="f9a38-108">组成部分</span><span class="sxs-lookup"><span data-stu-id="f9a38-108">Part</span></span>|<span data-ttu-id="f9a38-109">类型</span><span class="sxs-lookup"><span data-stu-id="f9a38-109">Type</span></span>|<span data-ttu-id="f9a38-110">说明</span><span class="sxs-lookup"><span data-stu-id="f9a38-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="f9a38-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="f9a38-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="f9a38-112">中的内容的占位符 <xref:System.Windows.Controls.ScrollViewer> 。</span><span class="sxs-lookup"><span data-stu-id="f9a38-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="f9a38-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="f9a38-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="f9a38-114"><xref:System.Windows.Controls.Primitives.ScrollBar>用于水平滚动内容的。</span><span class="sxs-lookup"><span data-stu-id="f9a38-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="f9a38-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="f9a38-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="f9a38-116"><xref:System.Windows.Controls.Primitives.ScrollBar>用于垂直滚动内容的。</span><span class="sxs-lookup"><span data-stu-id="f9a38-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="f9a38-117">ScrollViewer 状态</span><span class="sxs-lookup"><span data-stu-id="f9a38-117">ScrollViewer States</span></span>  
 <span data-ttu-id="f9a38-118">下表列出了控件的可视状态 <xref:System.Windows.Controls.ScrollViewer> 。</span><span class="sxs-lookup"><span data-stu-id="f9a38-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="f9a38-119">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="f9a38-119">VisualState Name</span></span>|<span data-ttu-id="f9a38-120">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="f9a38-120">VisualStateGroup Name</span></span>|<span data-ttu-id="f9a38-121">描述</span><span class="sxs-lookup"><span data-stu-id="f9a38-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="f9a38-122">有效</span><span class="sxs-lookup"><span data-stu-id="f9a38-122">Valid</span></span>|<span data-ttu-id="f9a38-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f9a38-123">ValidationStates</span></span>|<span data-ttu-id="f9a38-124">控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="f9a38-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="f9a38-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="f9a38-125">InvalidFocused</span></span>|<span data-ttu-id="f9a38-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f9a38-126">ValidationStates</span></span>|<span data-ttu-id="f9a38-127"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="f9a38-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="f9a38-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="f9a38-128">InvalidUnfocused</span></span>|<span data-ttu-id="f9a38-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f9a38-129">ValidationStates</span></span>|<span data-ttu-id="f9a38-130"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="f9a38-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="f9a38-131">ScrollViewer System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="f9a38-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="f9a38-132">下面的示例演示如何为控件定义 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.ScrollViewer> 。</span><span class="sxs-lookup"><span data-stu-id="f9a38-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="f9a38-133">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="f9a38-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="f9a38-134">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="f9a38-134">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9a38-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9a38-135">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="f9a38-136">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="f9a38-136">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="f9a38-137">控件自定义</span><span class="sxs-lookup"><span data-stu-id="f9a38-137">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="f9a38-138">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="f9a38-138">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="f9a38-139">创建控件模板</span><span class="sxs-lookup"><span data-stu-id="f9a38-139">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
