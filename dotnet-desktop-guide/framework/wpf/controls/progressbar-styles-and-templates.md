---
title: ProgressBar 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
ms.openlocfilehash: 781c185e01621767a82ebee054c578ed291c9b79
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972931"
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="18eed-102">ProgressBar 样式和模板</span><span class="sxs-lookup"><span data-stu-id="18eed-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="18eed-103">本主题描述控件的样式和模板 <xref:System.Windows.Controls.ProgressBar> 。</span><span class="sxs-lookup"><span data-stu-id="18eed-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="18eed-104">您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。</span><span class="sxs-lookup"><span data-stu-id="18eed-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="18eed-105">有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。</span><span class="sxs-lookup"><span data-stu-id="18eed-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="18eed-106">ProgressBar 部件</span><span class="sxs-lookup"><span data-stu-id="18eed-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="18eed-107">下表列出了控件的已命名部件 <xref:System.Windows.Controls.ProgressBar> 。</span><span class="sxs-lookup"><span data-stu-id="18eed-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="18eed-108">组成部分</span><span class="sxs-lookup"><span data-stu-id="18eed-108">Part</span></span>|<span data-ttu-id="18eed-109">类型</span><span class="sxs-lookup"><span data-stu-id="18eed-109">Type</span></span>|<span data-ttu-id="18eed-110">说明</span><span class="sxs-lookup"><span data-stu-id="18eed-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="18eed-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="18eed-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="18eed-112">指示进度的对象。</span><span class="sxs-lookup"><span data-stu-id="18eed-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="18eed-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="18eed-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="18eed-114">定义进度指示器的路径的对象。</span><span class="sxs-lookup"><span data-stu-id="18eed-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="18eed-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="18eed-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="18eed-116">Embellishes 进度栏的对象。</span><span class="sxs-lookup"><span data-stu-id="18eed-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="18eed-117">ProgressBar 状态</span><span class="sxs-lookup"><span data-stu-id="18eed-117">ProgressBar States</span></span>  
 <span data-ttu-id="18eed-118">下表列出了控件的可视状态 <xref:System.Windows.Controls.ProgressBar> 。</span><span class="sxs-lookup"><span data-stu-id="18eed-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="18eed-119">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="18eed-119">VisualState Name</span></span>|<span data-ttu-id="18eed-120">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="18eed-120">VisualStateGroup Name</span></span>|<span data-ttu-id="18eed-121">描述</span><span class="sxs-lookup"><span data-stu-id="18eed-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="18eed-122">确定性</span><span class="sxs-lookup"><span data-stu-id="18eed-122">Determinate</span></span>|<span data-ttu-id="18eed-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="18eed-123">CommonStates</span></span>|<span data-ttu-id="18eed-124"><xref:System.Windows.Controls.ProgressBar> 基于属性报告进度 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 。</span><span class="sxs-lookup"><span data-stu-id="18eed-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="18eed-125">尚</span><span class="sxs-lookup"><span data-stu-id="18eed-125">Indeterminate</span></span>|<span data-ttu-id="18eed-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="18eed-126">CommonStates</span></span>|<span data-ttu-id="18eed-127"><xref:System.Windows.Controls.ProgressBar> 使用重复模式报告一般进度。</span><span class="sxs-lookup"><span data-stu-id="18eed-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="18eed-128">有效</span><span class="sxs-lookup"><span data-stu-id="18eed-128">Valid</span></span>|<span data-ttu-id="18eed-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="18eed-129">ValidationStates</span></span>|<span data-ttu-id="18eed-130">控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="18eed-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="18eed-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="18eed-131">InvalidFocused</span></span>|<span data-ttu-id="18eed-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="18eed-132">ValidationStates</span></span>|<span data-ttu-id="18eed-133"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="18eed-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="18eed-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="18eed-134">InvalidUnfocused</span></span>|<span data-ttu-id="18eed-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="18eed-135">ValidationStates</span></span>|<span data-ttu-id="18eed-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="18eed-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="18eed-137">ProgressBar System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="18eed-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="18eed-138">下面的示例演示如何为控件定义 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.ProgressBar> 。</span><span class="sxs-lookup"><span data-stu-id="18eed-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="18eed-139">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="18eed-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="18eed-140">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="18eed-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18eed-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18eed-141">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="18eed-142">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="18eed-142">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="18eed-143">控件自定义</span><span class="sxs-lookup"><span data-stu-id="18eed-143">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="18eed-144">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="18eed-144">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="18eed-145">创建控件模板</span><span class="sxs-lookup"><span data-stu-id="18eed-145">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
