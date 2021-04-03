---
title: DocumentViewer 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], DocumentViewer
- DocumentViewer [WPF], styles and templates
- states [WPF], DocumentViewer
- ControlTemplate [WPF], DocumentViewer
- parts [WPF], DocumentViewer
- styles [WPF], DocumentViewer
ms.assetid: 6bd4ff8f-ea6a-4084-ac58-e7a67446ce1c
ms.openlocfilehash: 8a5d000dd67c1f5699c411db6ad1d7244ef0ad03
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973687"
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="0bfd5-102">DocumentViewer 样式和模板</span><span class="sxs-lookup"><span data-stu-id="0bfd5-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="0bfd5-103">本主题描述控件的样式和模板 <xref:System.Windows.Controls.DocumentViewer> 。</span><span class="sxs-lookup"><span data-stu-id="0bfd5-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="0bfd5-104">您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。</span><span class="sxs-lookup"><span data-stu-id="0bfd5-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0bfd5-105">有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。</span><span class="sxs-lookup"><span data-stu-id="0bfd5-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="0bfd5-106">DocumentViewer 部件</span><span class="sxs-lookup"><span data-stu-id="0bfd5-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="0bfd5-107">下表列出了控件的已命名部件 <xref:System.Windows.Controls.DocumentViewer> 。</span><span class="sxs-lookup"><span data-stu-id="0bfd5-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="0bfd5-108">组成部分</span><span class="sxs-lookup"><span data-stu-id="0bfd5-108">Part</span></span>|<span data-ttu-id="0bfd5-109">类型</span><span class="sxs-lookup"><span data-stu-id="0bfd5-109">Type</span></span>|<span data-ttu-id="0bfd5-110">说明</span><span class="sxs-lookup"><span data-stu-id="0bfd5-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0bfd5-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="0bfd5-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="0bfd5-112">内容和滚动区域。</span><span class="sxs-lookup"><span data-stu-id="0bfd5-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="0bfd5-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="0bfd5-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="0bfd5-114">默认情况下的搜索框。</span><span class="sxs-lookup"><span data-stu-id="0bfd5-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="0bfd5-115">DocumentViewer 状态</span><span class="sxs-lookup"><span data-stu-id="0bfd5-115">DocumentViewer States</span></span>  
 <span data-ttu-id="0bfd5-116">下表列出了控件的可视状态 <xref:System.Windows.Controls.DocumentViewer> 。</span><span class="sxs-lookup"><span data-stu-id="0bfd5-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="0bfd5-117">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="0bfd5-117">VisualState Name</span></span>|<span data-ttu-id="0bfd5-118">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="0bfd5-118">VisualStateGroup Name</span></span>|<span data-ttu-id="0bfd5-119">描述</span><span class="sxs-lookup"><span data-stu-id="0bfd5-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0bfd5-120">有效</span><span class="sxs-lookup"><span data-stu-id="0bfd5-120">Valid</span></span>|<span data-ttu-id="0bfd5-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0bfd5-121">ValidationStates</span></span>|<span data-ttu-id="0bfd5-122">控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="0bfd5-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="0bfd5-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0bfd5-123">InvalidFocused</span></span>|<span data-ttu-id="0bfd5-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0bfd5-124">ValidationStates</span></span>|<span data-ttu-id="0bfd5-125"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="0bfd5-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="0bfd5-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0bfd5-126">InvalidUnfocused</span></span>|<span data-ttu-id="0bfd5-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0bfd5-127">ValidationStates</span></span>|<span data-ttu-id="0bfd5-128"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="0bfd5-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="0bfd5-129">DocumentViewer System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="0bfd5-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="0bfd5-130">下面的示例演示如何为控件定义 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.DocumentViewer> 。</span><span class="sxs-lookup"><span data-stu-id="0bfd5-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="0bfd5-131">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="0bfd5-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="0bfd5-132">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="0bfd5-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bfd5-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bfd5-133">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="0bfd5-134">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="0bfd5-134">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="0bfd5-135">控件自定义</span><span class="sxs-lookup"><span data-stu-id="0bfd5-135">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="0bfd5-136">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="0bfd5-136">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="0bfd5-137">创建控件模板</span><span class="sxs-lookup"><span data-stu-id="0bfd5-137">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
