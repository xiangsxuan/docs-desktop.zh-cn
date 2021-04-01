---
title: Label 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], Label
- parts [WPF], Label
- ControlTemplate [WPF], Label
- styles [WPF], Label
- Label [WPF], styles and templates
- states [WPF], Label
ms.assetid: c1d5359a-8e4a-4925-ab3e-e92bf6694859
ms.openlocfilehash: 476f10a11c497633e2650403068576633d517937
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973239"
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="a53e8-102">Label 样式和模板</span><span class="sxs-lookup"><span data-stu-id="a53e8-102">Label Styles and Templates</span></span>
<span data-ttu-id="a53e8-103">本主题描述控件的样式和模板 <xref:System.Windows.Controls.Label> 。</span><span class="sxs-lookup"><span data-stu-id="a53e8-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="a53e8-104">您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。</span><span class="sxs-lookup"><span data-stu-id="a53e8-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a53e8-105">有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。</span><span class="sxs-lookup"><span data-stu-id="a53e8-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="a53e8-106">标签部件</span><span class="sxs-lookup"><span data-stu-id="a53e8-106">Label Parts</span></span>  
 <span data-ttu-id="a53e8-107"><xref:System.Windows.Controls.Label>控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="a53e8-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="a53e8-108">标签状态</span><span class="sxs-lookup"><span data-stu-id="a53e8-108">Label States</span></span>  
 <span data-ttu-id="a53e8-109">下表列出了控件的可视状态 <xref:System.Windows.Controls.Label> 。</span><span class="sxs-lookup"><span data-stu-id="a53e8-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="a53e8-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="a53e8-110">VisualState Name</span></span>|<span data-ttu-id="a53e8-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="a53e8-111">VisualStateGroup Name</span></span>|<span data-ttu-id="a53e8-112">描述</span><span class="sxs-lookup"><span data-stu-id="a53e8-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a53e8-113">有效</span><span class="sxs-lookup"><span data-stu-id="a53e8-113">Valid</span></span>|<span data-ttu-id="a53e8-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a53e8-114">ValidationStates</span></span>|<span data-ttu-id="a53e8-115">控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="a53e8-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a53e8-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a53e8-116">InvalidFocused</span></span>|<span data-ttu-id="a53e8-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a53e8-117">ValidationStates</span></span>|<span data-ttu-id="a53e8-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="a53e8-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a53e8-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a53e8-119">InvalidUnfocused</span></span>|<span data-ttu-id="a53e8-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a53e8-120">ValidationStates</span></span>|<span data-ttu-id="a53e8-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="a53e8-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="a53e8-122">标签 System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="a53e8-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="a53e8-123">下面的示例演示如何为控件定义 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Label> 。</span><span class="sxs-lookup"><span data-stu-id="a53e8-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="a53e8-124"><xref:System.Windows.Controls.ControlTemplate>使用以下一个或多个资源。</span><span class="sxs-lookup"><span data-stu-id="a53e8-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a53e8-125">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="a53e8-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a53e8-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="a53e8-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a53e8-127">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="a53e8-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="a53e8-128">控件自定义</span><span class="sxs-lookup"><span data-stu-id="a53e8-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="a53e8-129">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="a53e8-129">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="a53e8-130">创建控件模板</span><span class="sxs-lookup"><span data-stu-id="a53e8-130">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
