---
title: NavigationWindow 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], NavigationWindow
- NavigationWindow [WPF], styles and templates
- ControlTemplate [WPF], NavigationWindow
- parts [WPF], NavigationWindow
- styles [WPF], NavigationWindow
- templates [WPF], NavigationWindow
ms.assetid: 3656055e-3222-43c8-b868-fd0c90cc31a3
ms.openlocfilehash: 1189a6709a77af0a777b908f6aacab90288d01e7
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973706"
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="35862-102">NavigationWindow 样式和模板</span><span class="sxs-lookup"><span data-stu-id="35862-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="35862-103">本主题描述控件的样式和模板 <xref:System.Windows.Navigation.NavigationWindow> 。</span><span class="sxs-lookup"><span data-stu-id="35862-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="35862-104">您可以修改默认值 <xref:System.Windows.Controls.ControlTemplate> ，为控件指定独特的外观。</span><span class="sxs-lookup"><span data-stu-id="35862-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="35862-105">有关详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。</span><span class="sxs-lookup"><span data-stu-id="35862-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="35862-106">System.windows.navigation.navigationwindow> 部件</span><span class="sxs-lookup"><span data-stu-id="35862-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="35862-107">下表列出了控件的已命名部件 <xref:System.Windows.Navigation.NavigationWindow> 。</span><span class="sxs-lookup"><span data-stu-id="35862-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="35862-108">组成部分</span><span class="sxs-lookup"><span data-stu-id="35862-108">Part</span></span>|<span data-ttu-id="35862-109">类型</span><span class="sxs-lookup"><span data-stu-id="35862-109">Type</span></span>|<span data-ttu-id="35862-110">说明</span><span class="sxs-lookup"><span data-stu-id="35862-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="35862-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="35862-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="35862-112">内容的区域。</span><span class="sxs-lookup"><span data-stu-id="35862-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="35862-113">System.windows.navigation.navigationwindow> 状态</span><span class="sxs-lookup"><span data-stu-id="35862-113">NavigationWindow States</span></span>  
 <span data-ttu-id="35862-114">下表列出了控件的可视状态 <xref:System.Windows.Navigation.NavigationWindow> 。</span><span class="sxs-lookup"><span data-stu-id="35862-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="35862-115">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="35862-115">VisualState Name</span></span>|<span data-ttu-id="35862-116">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="35862-116">VisualStateGroup Name</span></span>|<span data-ttu-id="35862-117">描述</span><span class="sxs-lookup"><span data-stu-id="35862-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="35862-118">有效</span><span class="sxs-lookup"><span data-stu-id="35862-118">Valid</span></span>|<span data-ttu-id="35862-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="35862-119">ValidationStates</span></span>|<span data-ttu-id="35862-120">控件使用 <xref:System.Windows.Controls.Validation> 类， <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="35862-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="35862-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="35862-121">InvalidFocused</span></span>|<span data-ttu-id="35862-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="35862-122">ValidationStates</span></span>|<span data-ttu-id="35862-123"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="35862-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="35862-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="35862-124">InvalidUnfocused</span></span>|<span data-ttu-id="35862-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="35862-125">ValidationStates</span></span>|<span data-ttu-id="35862-126"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="35862-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="35862-127">System.windows.navigation.navigationwindow> System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="35862-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="35862-128">尽管此示例包含默认情况下在的中定义的所有元素 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Navigation.NavigationWindow> ，但应将特定值视为示例。</span><span class="sxs-lookup"><span data-stu-id="35862-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="35862-129">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="35862-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="35862-130">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="35862-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35862-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35862-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="35862-132">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="35862-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="35862-133">控件自定义</span><span class="sxs-lookup"><span data-stu-id="35862-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="35862-134">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="35862-134">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="35862-135">创建控件模板</span><span class="sxs-lookup"><span data-stu-id="35862-135">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
