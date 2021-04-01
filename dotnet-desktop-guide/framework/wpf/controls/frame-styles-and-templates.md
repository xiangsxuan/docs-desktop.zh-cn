---
title: Frame 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Frame
- templates [WPF], Frame
- ControlTemplate [WPF], Frame
- Frame [WPF], styles and templates
- states [WPF], Frame
- styles [WPF], Frame
ms.assetid: a01c32e2-c951-46a0-a82f-2614ca241f0b
ms.openlocfilehash: 106a7a2a0138250261ce31b0cbd98173b14e749a
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970630"
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="33b30-102">Frame 样式和模板</span><span class="sxs-lookup"><span data-stu-id="33b30-102">Frame Styles and Templates</span></span>
<span data-ttu-id="33b30-103">本主题描述控件的样式和模板 <xref:System.Windows.Controls.Frame> 。</span><span class="sxs-lookup"><span data-stu-id="33b30-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="33b30-104">您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。</span><span class="sxs-lookup"><span data-stu-id="33b30-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="33b30-105">有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。</span><span class="sxs-lookup"><span data-stu-id="33b30-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="33b30-106">帧部分</span><span class="sxs-lookup"><span data-stu-id="33b30-106">Frame Parts</span></span>  
 <span data-ttu-id="33b30-107">下表列出了控件的已命名部件 <xref:System.Windows.Controls.Frame> 。</span><span class="sxs-lookup"><span data-stu-id="33b30-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="33b30-108">组成部分</span><span class="sxs-lookup"><span data-stu-id="33b30-108">Part</span></span>|<span data-ttu-id="33b30-109">类型</span><span class="sxs-lookup"><span data-stu-id="33b30-109">Type</span></span>|<span data-ttu-id="33b30-110">说明</span><span class="sxs-lookup"><span data-stu-id="33b30-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="33b30-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="33b30-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="33b30-112">内容区域。</span><span class="sxs-lookup"><span data-stu-id="33b30-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="33b30-113">帧状态</span><span class="sxs-lookup"><span data-stu-id="33b30-113">Frame States</span></span>  
 <span data-ttu-id="33b30-114">下表列出了控件的可视状态 <xref:System.Windows.Controls.Frame> 。</span><span class="sxs-lookup"><span data-stu-id="33b30-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="33b30-115">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="33b30-115">VisualState Name</span></span>|<span data-ttu-id="33b30-116">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="33b30-116">VisualStateGroup Name</span></span>|<span data-ttu-id="33b30-117">描述</span><span class="sxs-lookup"><span data-stu-id="33b30-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="33b30-118">有效</span><span class="sxs-lookup"><span data-stu-id="33b30-118">Valid</span></span>|<span data-ttu-id="33b30-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="33b30-119">ValidationStates</span></span>|<span data-ttu-id="33b30-120">控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="33b30-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="33b30-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="33b30-121">InvalidFocused</span></span>|<span data-ttu-id="33b30-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="33b30-122">ValidationStates</span></span>|<span data-ttu-id="33b30-123"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="33b30-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="33b30-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="33b30-124">InvalidUnfocused</span></span>|<span data-ttu-id="33b30-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="33b30-125">ValidationStates</span></span>|<span data-ttu-id="33b30-126"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="33b30-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="33b30-127">Frame System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="33b30-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="33b30-128">下面的示例演示如何为控件定义 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Frame> 。</span><span class="sxs-lookup"><span data-stu-id="33b30-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="33b30-129">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="33b30-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="33b30-130">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="33b30-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b30-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33b30-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="33b30-132">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="33b30-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="33b30-133">控件自定义</span><span class="sxs-lookup"><span data-stu-id="33b30-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="33b30-134">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="33b30-134">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="33b30-135">创建控件模板</span><span class="sxs-lookup"><span data-stu-id="33b30-135">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
