---
title: GroupBox 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: 8648c284a1da3e7d629bec91210c8dd5ecdb8484
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972953"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="95cb7-102">GroupBox 样式和模板</span><span class="sxs-lookup"><span data-stu-id="95cb7-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a> <span data-ttu-id="95cb7-103">本主题描述控件的样式和模板 <xref:System.Windows.Controls.GroupBox> 。</span><span class="sxs-lookup"><span data-stu-id="95cb7-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="95cb7-104">您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。</span><span class="sxs-lookup"><span data-stu-id="95cb7-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="95cb7-105">有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。</span><span class="sxs-lookup"><span data-stu-id="95cb7-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
<a name="groupbox_parts"></a>
## <a name="groupbox-parts"></a><span data-ttu-id="95cb7-106">分组框部分</span><span class="sxs-lookup"><span data-stu-id="95cb7-106">GroupBox Parts</span></span>  
 <span data-ttu-id="95cb7-107"><xref:System.Windows.Controls.GroupBox>控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="95cb7-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>
## <a name="groupbox-states"></a><span data-ttu-id="95cb7-108">分组框状态</span><span class="sxs-lookup"><span data-stu-id="95cb7-108">GroupBox States</span></span>  
 <span data-ttu-id="95cb7-109">下表列出了控件的可视状态 <xref:System.Windows.Controls.GroupBox> 。</span><span class="sxs-lookup"><span data-stu-id="95cb7-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="95cb7-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="95cb7-110">VisualState Name</span></span>|<span data-ttu-id="95cb7-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="95cb7-111">VisualStateGroup Name</span></span>|<span data-ttu-id="95cb7-112">描述</span><span class="sxs-lookup"><span data-stu-id="95cb7-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="95cb7-113">有效</span><span class="sxs-lookup"><span data-stu-id="95cb7-113">Valid</span></span>|<span data-ttu-id="95cb7-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="95cb7-114">ValidationStates</span></span>|<span data-ttu-id="95cb7-115">控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="95cb7-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="95cb7-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="95cb7-116">InvalidFocused</span></span>|<span data-ttu-id="95cb7-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="95cb7-117">ValidationStates</span></span>|<span data-ttu-id="95cb7-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="95cb7-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="95cb7-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="95cb7-119">InvalidUnfocused</span></span>|<span data-ttu-id="95cb7-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="95cb7-120">ValidationStates</span></span>|<span data-ttu-id="95cb7-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="95cb7-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="95cb7-122">分组 System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="95cb7-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="95cb7-123">下面的示例演示如何为控件定义 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.GroupBox> 。</span><span class="sxs-lookup"><span data-stu-id="95cb7-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="95cb7-124"><xref:System.Windows.Controls.ControlTemplate>使用以下一个或多个资源。</span><span class="sxs-lookup"><span data-stu-id="95cb7-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="95cb7-125">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="95cb7-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95cb7-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="95cb7-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="95cb7-127">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="95cb7-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="95cb7-128">控件自定义</span><span class="sxs-lookup"><span data-stu-id="95cb7-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="95cb7-129">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="95cb7-129">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="95cb7-130">创建控件模板</span><span class="sxs-lookup"><span data-stu-id="95cb7-130">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
