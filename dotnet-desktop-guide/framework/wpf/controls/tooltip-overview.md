---
title: ToolTip 概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], about ToolTip control
- controls [WPF], ToolTip
ms.assetid: f06c1603-e9cb-4809-8a62-234607fc52f7
ms.openlocfilehash: bbeeb4d1de2c94604f7340ea931b4610169d3722
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104668170"
---
# <a name="tooltip-overview"></a><span data-ttu-id="58fc2-102">ToolTip 概述</span><span class="sxs-lookup"><span data-stu-id="58fc2-102">ToolTip Overview</span></span>

<span data-ttu-id="58fc2-103">工具提示是一个小的弹出窗口，当用户将鼠标指针悬停在某个元素上（如上的）时，将显示该窗口 <xref:System.Windows.Controls.Button> 。</span><span class="sxs-lookup"><span data-stu-id="58fc2-103">A tooltip is a small pop-up window that appears when a user pauses the mouse pointer over an element, such as over a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="58fc2-104">本主题介绍工具提示，并讨论如何创建和自定义工具提示内容。</span><span class="sxs-lookup"><span data-stu-id="58fc2-104">This topic introduces the tooltip and discusses how to create and customize tooltip content.</span></span>  

<a name="what_is_a_tooltip"></a>

## <a name="what-is-a-tooltip"></a><span data-ttu-id="58fc2-105">什么是工具提示</span><span class="sxs-lookup"><span data-stu-id="58fc2-105">What Is a Tooltip</span></span>  

 <span data-ttu-id="58fc2-106">当用户将鼠标指针移动到具有工具提示的元素上时，将在一段指定的时间内显示一个包含工具提示内容（例如，介绍控件功能的文本内容）的窗口。</span><span class="sxs-lookup"><span data-stu-id="58fc2-106">When a user moves the mouse pointer over an element that has a tooltip, a window that contains tooltip content (for example, text content that describes the function of a control) appears for a specified amount of time.</span></span> <span data-ttu-id="58fc2-107">如果用户将鼠标指针从控件上移开，该窗口将消失，因为工具提示内容无法接收焦点。</span><span class="sxs-lookup"><span data-stu-id="58fc2-107">If the user moves the mouse pointer away from the control, the window disappears because the tooltip content cannot receive focus.</span></span>  
  
 <span data-ttu-id="58fc2-108">工具提示的内容可以包含一行或多行文本、图像、形状或其他可视内容。</span><span class="sxs-lookup"><span data-stu-id="58fc2-108">The content of a tooltip can contain one or more lines of text, images, shapes, or other visual content.</span></span> <span data-ttu-id="58fc2-109">通过将以下属性之一设置为工具提示内容来定义控件的工具提示。</span><span class="sxs-lookup"><span data-stu-id="58fc2-109">You define a tooltip for a control by setting one of the following properties to the tooltip content.</span></span>  
  
- <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="58fc2-110">使用哪个属性取决于定义工具提示的控件是否继承自 <xref:System.Windows.FrameworkContentElement> 或 <xref:System.Windows.FrameworkElement> 类。</span><span class="sxs-lookup"><span data-stu-id="58fc2-110">Which property you use depends on whether the control that defines the tooltip inherits from the <xref:System.Windows.FrameworkContentElement> or <xref:System.Windows.FrameworkElement> class.</span></span>  
  
<a name="create_tooltip"></a>

## <a name="creating-a-tooltip"></a><span data-ttu-id="58fc2-111">创建工具提示</span><span class="sxs-lookup"><span data-stu-id="58fc2-111">Creating a ToolTip</span></span>  

 <span data-ttu-id="58fc2-112">下面的示例演示如何通过将 <xref:System.Windows.FrameworkElement.ToolTip%2A> 控件的属性设置为文本字符串来创建简单的工具提示 <xref:System.Windows.Controls.Button> 。</span><span class="sxs-lookup"><span data-stu-id="58fc2-112">The following example shows how to create a simple tooltip by setting the <xref:System.Windows.FrameworkElement.ToolTip%2A> property for a <xref:System.Windows.Controls.Button> control to a text string.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#ToolTipString](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 <span data-ttu-id="58fc2-113">您还可以将工具提示定义为 <xref:System.Windows.Controls.ToolTip> 对象。</span><span class="sxs-lookup"><span data-stu-id="58fc2-113">You can also define a tooltip as a <xref:System.Windows.Controls.ToolTip> object.</span></span> <span data-ttu-id="58fc2-114">下面的示例使用 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 将对象指定 <xref:System.Windows.Controls.ToolTip> 为元素的工具提示 <xref:System.Windows.Controls.TextBox> 。</span><span class="sxs-lookup"><span data-stu-id="58fc2-114">The following example uses [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] to specify a <xref:System.Windows.Controls.ToolTip> object as the tooltip of a <xref:System.Windows.Controls.TextBox> element.</span></span> <span data-ttu-id="58fc2-115">请注意，该示例 <xref:System.Windows.Controls.ToolTip> 通过设置属性来指定 <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="58fc2-115">Note that the example specifies the <xref:System.Windows.Controls.ToolTip> by setting the <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType> property.</span></span>  
  
 [!code-xaml[ToolTipSimple#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 <span data-ttu-id="58fc2-116">下面的示例使用代码生成一个 <xref:System.Windows.Controls.ToolTip> 对象。</span><span class="sxs-lookup"><span data-stu-id="58fc2-116">The following example uses code to generate a <xref:System.Windows.Controls.ToolTip> object.</span></span> <span data-ttu-id="58fc2-117">该示例创建一个 <xref:System.Windows.Controls.ToolTip> (`tt`) 并将其与关联 <xref:System.Windows.Controls.Button> 。</span><span class="sxs-lookup"><span data-stu-id="58fc2-117">The example creates a <xref:System.Windows.Controls.ToolTip> (`tt`) and associates it with a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-csharp[ToolTipSimple#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 <span data-ttu-id="58fc2-118">你还可以 <xref:System.Windows.Controls.ToolTip> 通过在布局元素（例如）中包含工具提示内容来创建未定义为对象的工具提示内容 <xref:System.Windows.Controls.DockPanel> 。</span><span class="sxs-lookup"><span data-stu-id="58fc2-118">You can also create tooltip content that is not defined as a <xref:System.Windows.Controls.ToolTip> object by enclosing the tooltip content in a layout element, such as a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="58fc2-119">下面的示例演示如何将的 <xref:System.Windows.FrameworkElement.ToolTip%2A> 属性设置 <xref:System.Windows.Controls.TextBox> 为包含在控件中的内容 <xref:System.Windows.Controls.DockPanel> 。</span><span class="sxs-lookup"><span data-stu-id="58fc2-119">The following example shows how to set the <xref:System.Windows.FrameworkElement.ToolTip%2A> property of a <xref:System.Windows.Controls.TextBox> to content that is enclosed in a <xref:System.Windows.Controls.DockPanel> control.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#ToolTipDockPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>

## <a name="using-the-properties-of-the-tooltip-and-tooltipservice-classes"></a><span data-ttu-id="58fc2-120">使用 ToolTipd 和 ToolTipService 类的属性</span><span class="sxs-lookup"><span data-stu-id="58fc2-120">Using the Properties of the ToolTip and ToolTipService Classes</span></span>  

 <span data-ttu-id="58fc2-121">可以通过设置视觉属性和应用样式来自定义工具提示内容。</span><span class="sxs-lookup"><span data-stu-id="58fc2-121">You can customize tooltip content by setting visual properties and applying styles.</span></span> <span data-ttu-id="58fc2-122">如果将工具提示内容定义为 <xref:System.Windows.Controls.ToolTip> 对象，则可以设置对象的视觉 <xref:System.Windows.Controls.ToolTip> 对象属性。</span><span class="sxs-lookup"><span data-stu-id="58fc2-122">If you define the tooltip content as a <xref:System.Windows.Controls.ToolTip> object, you can set the visual properties of the <xref:System.Windows.Controls.ToolTip> object.</span></span> <span data-ttu-id="58fc2-123">否则，你必须在类上设置等效的附加属性 <xref:System.Windows.Controls.ToolTipService> 。</span><span class="sxs-lookup"><span data-stu-id="58fc2-123">Otherwise, you must set equivalent attached properties on the <xref:System.Windows.Controls.ToolTipService> class.</span></span>  
  
 <span data-ttu-id="58fc2-124">有关如何设置属性以便使用和属性指定工具提示内容的位置的示例 <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> ，请参阅 [定位工具提示](how-to-position-a-tooltip.md)。</span><span class="sxs-lookup"><span data-stu-id="58fc2-124">For an example of how to set properties in order to specify the position of tooltip content by using the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> properties, see [Position a ToolTip](how-to-position-a-tooltip.md).</span></span>  
  
<a name="StylingToolTip"></a>

## <a name="styling-a-tooltip"></a><span data-ttu-id="58fc2-125">设置工具提示样式</span><span class="sxs-lookup"><span data-stu-id="58fc2-125">Styling a ToolTip</span></span>  

 <span data-ttu-id="58fc2-126">可以 <xref:System.Windows.Controls.ToolTip> 通过定义自定义来样式 <xref:System.Windows.Style> 。</span><span class="sxs-lookup"><span data-stu-id="58fc2-126">You can style a <xref:System.Windows.Controls.ToolTip> by defining a custom <xref:System.Windows.Style>.</span></span> <span data-ttu-id="58fc2-127">下面的示例定义一个 <xref:System.Windows.Style> 名 `Simple` 为的，该示例演示如何 <xref:System.Windows.Controls.ToolTip> 通过设置 <xref:System.Windows.Controls.Control.Background%2A> 、、和来偏移的位置并更改其外观 <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Controls.Control.FontSize%2A> <xref:System.Windows.Controls.Control.FontWeight%2A> 。</span><span class="sxs-lookup"><span data-stu-id="58fc2-127">The following example defines a <xref:System.Windows.Style> called `Simple` that shows how to offset the placement of the <xref:System.Windows.Controls.ToolTip> and change its appearance by setting the <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, and <xref:System.Windows.Controls.Control.FontWeight%2A>.</span></span>  
  
 [!code-xaml[ToolTipSimple#Style](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>

## <a name="using-the-time-interval-properties-of-tooltipservice"></a><span data-ttu-id="58fc2-128">使用 ToolTipService 的 Time Interval 属性</span><span class="sxs-lookup"><span data-stu-id="58fc2-128">Using the Time Interval Properties of ToolTipService</span></span>  

 <span data-ttu-id="58fc2-129"><xref:System.Windows.Controls.ToolTipService>类提供以下属性，用于设置工具提示显示时间： <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> 、 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> 和 <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> 。</span><span class="sxs-lookup"><span data-stu-id="58fc2-129">The <xref:System.Windows.Controls.ToolTipService> class provides the following properties for you to set tooltip display times: <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>, <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>, and <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>.</span></span>  
  
 <span data-ttu-id="58fc2-130">使用 <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> 和 <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> 属性可以指定在出现前的延迟（通常为 brief）， <xref:System.Windows.Controls.ToolTip> 还可以指定保持可见的时间长度 <xref:System.Windows.Controls.ToolTip> 。</span><span class="sxs-lookup"><span data-stu-id="58fc2-130">Use the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> and <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> properties to specify a delay, typically brief, before a <xref:System.Windows.Controls.ToolTip> appears and also to specify how long a <xref:System.Windows.Controls.ToolTip> remains visible.</span></span> <span data-ttu-id="58fc2-131">有关详细信息，请参阅[如何：延迟 ToolTip 的显示](/previous-versions/dotnet/netframework-3.5/ms747264(v=vs.90))。</span><span class="sxs-lookup"><span data-stu-id="58fc2-131">For more information, see [How to: Delay the Display of a ToolTip](/previous-versions/dotnet/netframework-3.5/ms747264(v=vs.90)).</span></span>  
  
 <span data-ttu-id="58fc2-132"><xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>属性确定不同控件的工具提示在其之间快速移动鼠标指针时是否出现初始延迟。</span><span class="sxs-lookup"><span data-stu-id="58fc2-132">The <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> property determines if tooltips for different controls appear without an initial delay when you move the mouse pointer quickly between them.</span></span> <span data-ttu-id="58fc2-133">有关属性的详细信息 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> ，请参阅 [使用 BetweenShowDelay 属性](how-to-use-the-betweenshowdelay-property.md)。</span><span class="sxs-lookup"><span data-stu-id="58fc2-133">For more information about the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> property, see [Use the BetweenShowDelay Property](how-to-use-the-betweenshowdelay-property.md).</span></span>  
  
 <span data-ttu-id="58fc2-134">以下示例演示如何为工具提示设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="58fc2-134">The following example shows how to set these properties for a tooltip.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## <a name="see-also"></a><span data-ttu-id="58fc2-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="58fc2-135">See also</span></span>

- <xref:System.Windows.Controls.ToolTipService>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipEventArgs>
- <xref:System.Windows.Controls.ToolTipEventHandler>
- [<span data-ttu-id="58fc2-136">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="58fc2-136">How-to Topics</span></span>](tooltip-how-to-topics.md)
