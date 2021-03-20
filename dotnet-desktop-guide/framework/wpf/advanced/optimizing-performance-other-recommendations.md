---
title: 优化性能：其他建议
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Terminal Services rendering [WPF]
- opacity [WPF]
- hit-test objects [WPF]
- ScrollBarVisibility enumeration [WPF]
- brushes [WPF], performance
ms.assetid: d028cc65-7e97-4a4f-9859-929734eaf40d
ms.openlocfilehash: 678e5726688d8abe92d3e982c0dbff5335f05ba8
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665323"
---
# <a name="optimizing-performance-other-recommendations"></a><span data-ttu-id="6a89c-102">优化性能：其他建议</span><span class="sxs-lookup"><span data-stu-id="6a89c-102">Optimizing Performance: Other Recommendations</span></span>
<a name="introduction"></a><span data-ttu-id="6a89c-103">本主题提供[优化 WPF 应用程序性能](optimizing-wpf-application-performance.md)这一节中各主题内容之外的性能改进建议。</span><span class="sxs-lookup"><span data-stu-id="6a89c-103">This topic provides performance recommendations in addition to the ones covered by the topics in the [Optimizing WPF Application Performance](optimizing-wpf-application-performance.md) section.</span></span>  
  
 <span data-ttu-id="6a89c-104">本主题包含以下各节：</span><span class="sxs-lookup"><span data-stu-id="6a89c-104">This topic contains the following sections:</span></span>  
  
- [<span data-ttu-id="6a89c-105">画笔的不透明度与元素的不透明度</span><span class="sxs-lookup"><span data-stu-id="6a89c-105">Opacity on Brushes Versus Opacity on Elements</span></span>](#Opacity)  
  
- [<span data-ttu-id="6a89c-106">导航到对象</span><span class="sxs-lookup"><span data-stu-id="6a89c-106">Navigation to Object</span></span>](#Navigation_Objects)  
  
- [<span data-ttu-id="6a89c-107">对大型 3D 图面进行命中测试</span><span class="sxs-lookup"><span data-stu-id="6a89c-107">Hit Testing on Large 3D Surfaces</span></span>](#Hit_Testing)  
  
- [<span data-ttu-id="6a89c-108">CompositionTarget.Rendering 事件</span><span class="sxs-lookup"><span data-stu-id="6a89c-108">CompositionTarget.Rendering Event</span></span>](#CompositionTarget_Rendering_Event)  
  
- [<span data-ttu-id="6a89c-109">避免使用 ScrollBarVisibility=Auto</span><span class="sxs-lookup"><span data-stu-id="6a89c-109">Avoid Using ScrollBarVisibility=Auto</span></span>](#Avoid_Using_ScrollBarVisibility)  
  
- [<span data-ttu-id="6a89c-110">配置字体缓存服务以缩短启动时间</span><span class="sxs-lookup"><span data-stu-id="6a89c-110">Configure Font Cache Service to Reduce Start-up Time</span></span>](#FontCache)  
  
<a name="Opacity"></a>
## <a name="opacity-on-brushes-versus-opacity-on-elements"></a><span data-ttu-id="6a89c-111">画笔的不透明度与元素的不透明度</span><span class="sxs-lookup"><span data-stu-id="6a89c-111">Opacity on Brushes Versus Opacity on Elements</span></span>  
 <span data-ttu-id="6a89c-112">当你使用 <xref:System.Windows.Media.Brush> 设置 <xref:System.Windows.Shapes.Shape.Fill%2A> 元素的或时 <xref:System.Windows.Shapes.Shape.Stroke%2A> ，最好设置 <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType> 值，而不是设置元素的 <xref:System.Windows.UIElement.Opacity%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="6a89c-112">When you use a <xref:System.Windows.Media.Brush> to set the <xref:System.Windows.Shapes.Shape.Fill%2A> or <xref:System.Windows.Shapes.Shape.Stroke%2A> of an element, it is better to set the <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType> value rather than the setting the element's <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="6a89c-113">修改元素的 <xref:System.Windows.UIElement.Opacity%2A> 属性可能会导致 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 创建一个临时表面。</span><span class="sxs-lookup"><span data-stu-id="6a89c-113">Modifying an element's <xref:System.Windows.UIElement.Opacity%2A> property can cause [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] to create a temporary surface.</span></span>  
  
<a name="Navigation_Objects"></a>
## <a name="navigation-to-object"></a><span data-ttu-id="6a89c-114">导航到对象</span><span class="sxs-lookup"><span data-stu-id="6a89c-114">Navigation to Object</span></span>  
 <span data-ttu-id="6a89c-115"><xref:System.Windows.Navigation.NavigationWindow>对象派生自 <xref:System.Windows.Window> ，并通过内容导航支持对其进行扩展，主要通过聚合 <xref:System.Windows.Navigation.NavigationService> 和日记进行扩展。</span><span class="sxs-lookup"><span data-stu-id="6a89c-115">The <xref:System.Windows.Navigation.NavigationWindow> object derives from <xref:System.Windows.Window> and extends it with content navigation support, primarily by aggregating <xref:System.Windows.Navigation.NavigationService> and the journal.</span></span> <span data-ttu-id="6a89c-116"><xref:System.Windows.Navigation.NavigationWindow>通过指定 (URI) 或对象的统一资源标识符，可以更新的工作区。</span><span class="sxs-lookup"><span data-stu-id="6a89c-116">You can update the client area of <xref:System.Windows.Navigation.NavigationWindow> by specifying either a uniform resource identifier (URI) or an object.</span></span> <span data-ttu-id="6a89c-117">以下示例演示了这两种方法：</span><span class="sxs-lookup"><span data-stu-id="6a89c-117">The following sample shows both methods:</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet14](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 <span data-ttu-id="6a89c-118">每个 <xref:System.Windows.Navigation.NavigationWindow> 对象都有一个日志，该日志记录用户在该窗口中的导航历史记录。</span><span class="sxs-lookup"><span data-stu-id="6a89c-118">Each <xref:System.Windows.Navigation.NavigationWindow> object has a journal that records the user's navigation history in that window.</span></span> <span data-ttu-id="6a89c-119">日志的作用之一是允许用户回溯他们执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="6a89c-119">One of the purposes of the journal is to allow users to retrace their steps.</span></span>  
  
 <span data-ttu-id="6a89c-120">当您使用统一资源标识符 (URI) 进行导航时，日志仅存储统一资源标识符 (URI) 引用。</span><span class="sxs-lookup"><span data-stu-id="6a89c-120">When you navigate using a uniform resource identifier (URI), the journal stores only the uniform resource identifier (URI) reference.</span></span> <span data-ttu-id="6a89c-121">这意味着，每次重新访问该页时都会动态地重新构造该页，根据页面的复杂程度，此过程可能会非常耗时。</span><span class="sxs-lookup"><span data-stu-id="6a89c-121">This means that each time you revisit the page, it is dynamically reconstructed, which may be time consuming depending on the complexity of the page.</span></span> <span data-ttu-id="6a89c-122">在这种情况下，虽然占用的日志存储较少，但用于重建该页的时间可能会较长。</span><span class="sxs-lookup"><span data-stu-id="6a89c-122">In this case, the journal storage cost is low, but the time to reconstitute the page is potentially high.</span></span>  
  
 <span data-ttu-id="6a89c-123">使用对象进行导航时，日志会存储对象的整个可视化树。</span><span class="sxs-lookup"><span data-stu-id="6a89c-123">When you navigate using an object, the journal stores the entire visual tree of the object.</span></span> <span data-ttu-id="6a89c-124">这意味着，每次重新访问该页时，无需重新构造即可立即呈现该页。</span><span class="sxs-lookup"><span data-stu-id="6a89c-124">This means that each time you revisit the page, it renders immediately without having to be reconstructed.</span></span> <span data-ttu-id="6a89c-125">在这种情况下，虽然占用的日志存储较多，但重建页面所用的时间较短。</span><span class="sxs-lookup"><span data-stu-id="6a89c-125">In this case, the journal storage cost is high, but the time to reconstitute the page is low.</span></span>  
  
 <span data-ttu-id="6a89c-126">使用 <xref:System.Windows.Navigation.NavigationWindow> 对象时，需要记住日记支持如何影响应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="6a89c-126">When you use the <xref:System.Windows.Navigation.NavigationWindow> object, you will need to keep in mind how the journaling support impacts your application's performance.</span></span> <span data-ttu-id="6a89c-127">有关详细信息，请参阅 [导航概述](../app-development/navigation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="6a89c-127">For more information, see [Navigation Overview](../app-development/navigation-overview.md).</span></span>  
  
<a name="Hit_Testing"></a>
## <a name="hit-testing-on-large-3d-surfaces"></a><span data-ttu-id="6a89c-128">对大型 3D 图面进行命中测试</span><span class="sxs-lookup"><span data-stu-id="6a89c-128">Hit Testing on Large 3D Surfaces</span></span>  
 <span data-ttu-id="6a89c-129">就 CPU 消耗而言，对大型 3D 图面进行命中测试是一项非常占用资源的操作。</span><span class="sxs-lookup"><span data-stu-id="6a89c-129">Hit testing on large 3D surfaces is a very performance intensive operation in terms of CPU consumption.</span></span> <span data-ttu-id="6a89c-130">3D 图面显示动画效果时更是如此。</span><span class="sxs-lookup"><span data-stu-id="6a89c-130">This is especially true when the 3D surface is animating.</span></span> <span data-ttu-id="6a89c-131">如果不需要对这些图面进行命中测试，请禁用命中测试。</span><span class="sxs-lookup"><span data-stu-id="6a89c-131">If you do not require hit testing on these surfaces, then disable hit testing.</span></span> <span data-ttu-id="6a89c-132">派生自的对象 <xref:System.Windows.UIElement> 可通过将 <xref:System.Windows.UIElement.IsHitTestVisible%2A> 属性设置为来禁用命中测试 `false` 。</span><span class="sxs-lookup"><span data-stu-id="6a89c-132">Objects that are derived from <xref:System.Windows.UIElement> can disable hit testing by setting the <xref:System.Windows.UIElement.IsHitTestVisible%2A> property to `false`.</span></span>  
  
<a name="CompositionTarget_Rendering_Event"></a>
## <a name="compositiontargetrendering-event"></a><span data-ttu-id="6a89c-133">CompositionTarget.Rendering 事件</span><span class="sxs-lookup"><span data-stu-id="6a89c-133">CompositionTarget.Rendering Event</span></span>  
 <span data-ttu-id="6a89c-134"><xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType>事件会导致 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 持续产生动画效果。</span><span class="sxs-lookup"><span data-stu-id="6a89c-134">The <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType> event causes [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] to continuously animate.</span></span> <span data-ttu-id="6a89c-135">使用此事件时，应尽可能将其分离。</span><span class="sxs-lookup"><span data-stu-id="6a89c-135">If you use this event, detach it at every opportunity.</span></span>  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>
## <a name="avoid-using-scrollbarvisibilityauto"></a><span data-ttu-id="6a89c-136">避免使用 ScrollBarVisibility=Auto</span><span class="sxs-lookup"><span data-stu-id="6a89c-136">Avoid Using ScrollBarVisibility=Auto</span></span>  
 <span data-ttu-id="6a89c-137">请尽可能避免使用 <xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType> `HorizontalScrollBarVisibility` 和属性的值 `VerticalScrollBarVisibility` 。</span><span class="sxs-lookup"><span data-stu-id="6a89c-137">Whenever possible, avoid using the <xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType> value for the `HorizontalScrollBarVisibility` and `VerticalScrollBarVisibility` properties.</span></span> <span data-ttu-id="6a89c-138">为 <xref:System.Windows.Controls.RichTextBox> 、 <xref:System.Windows.Controls.ScrollViewer> 、和对象定义这些属性 <xref:System.Windows.Controls.TextBox> ，并将其用作对象的附加属性 <xref:System.Windows.Controls.ListBox> 。</span><span class="sxs-lookup"><span data-stu-id="6a89c-138">These properties are defined for <xref:System.Windows.Controls.RichTextBox>, <xref:System.Windows.Controls.ScrollViewer>, and <xref:System.Windows.Controls.TextBox> objects, and as an attached property for the <xref:System.Windows.Controls.ListBox> object.</span></span> <span data-ttu-id="6a89c-139">而是设置 <xref:System.Windows.Controls.ScrollBarVisibility> 为 <xref:System.Windows.Controls.ScrollBarVisibility.Disabled> 、 <xref:System.Windows.Controls.ScrollBarVisibility.Hidden> 或 <xref:System.Windows.Controls.ScrollBarVisibility.Visible> 。</span><span class="sxs-lookup"><span data-stu-id="6a89c-139">Instead, set <xref:System.Windows.Controls.ScrollBarVisibility> to <xref:System.Windows.Controls.ScrollBarVisibility.Disabled>, <xref:System.Windows.Controls.ScrollBarVisibility.Hidden>, or <xref:System.Windows.Controls.ScrollBarVisibility.Visible>.</span></span>  
  
 <span data-ttu-id="6a89c-140">此 <xref:System.Windows.Controls.ScrollBarVisibility.Auto> 值适用于空间受限时的情况，滚动条应仅在必要时显示滚动条。</span><span class="sxs-lookup"><span data-stu-id="6a89c-140">The <xref:System.Windows.Controls.ScrollBarVisibility.Auto> value is intended for cases when space is limited and scrollbars should only be displayed when necessary.</span></span> <span data-ttu-id="6a89c-141">例如，将此 <xref:System.Windows.Controls.ScrollBarVisibility> 值用于 <xref:System.Windows.Controls.ListBox> 30 项（而不是 <xref:System.Windows.Controls.TextBox> 包含数百行文本的）的情况下，可能会很有用。</span><span class="sxs-lookup"><span data-stu-id="6a89c-141">For example, it may be useful to use this <xref:System.Windows.Controls.ScrollBarVisibility> value with a <xref:System.Windows.Controls.ListBox> of 30 items as opposed to a <xref:System.Windows.Controls.TextBox> with hundreds of lines of text.</span></span>  
  
<a name="FontCache"></a>
## <a name="configure-font-cache-service-to-reduce-start-up-time"></a><span data-ttu-id="6a89c-142">配置字体缓存服务以缩短启动时间</span><span class="sxs-lookup"><span data-stu-id="6a89c-142">Configure Font Cache Service to Reduce Start-up Time</span></span>  
 <span data-ttu-id="6a89c-143">WPF 字体缓存服务在 WPF 应用程序之间共享字体数据。</span><span class="sxs-lookup"><span data-stu-id="6a89c-143">The WPF Font Cache service shares font data between WPF applications.</span></span> <span data-ttu-id="6a89c-144">如果该服务尚未运行，则第一个运行的 WPF 应用程序会启动此服务。</span><span class="sxs-lookup"><span data-stu-id="6a89c-144">The first WPF application you run starts this service if the service is not already running.</span></span> <span data-ttu-id="6a89c-145">如果使用的是 Windows Vista，则可以将 "Windows Presentation Foundation (WPF) Font Cache 3.0.0.0" 服务从 "手动 (" 设置为 "自动) 延迟启动 ("，以减少 WPF 应用程序的初始启动时间。</span><span class="sxs-lookup"><span data-stu-id="6a89c-145">If you are using Windows Vista, you can set the "Windows Presentation Foundation (WPF) Font Cache 3.0.0.0" service from "Manual" (the default) to "Automatic (Delayed Start)" to reduce the initial start-up time of WPF applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a89c-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a89c-146">See also</span></span>

- [<span data-ttu-id="6a89c-147">规划应用程序性能</span><span class="sxs-lookup"><span data-stu-id="6a89c-147">Planning for Application Performance</span></span>](planning-for-application-performance.md)
- [<span data-ttu-id="6a89c-148">利用硬件</span><span class="sxs-lookup"><span data-stu-id="6a89c-148">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)
- [<span data-ttu-id="6a89c-149">布局和示例</span><span class="sxs-lookup"><span data-stu-id="6a89c-149">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)
- [<span data-ttu-id="6a89c-150">二维图形和图像处理</span><span class="sxs-lookup"><span data-stu-id="6a89c-150">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="6a89c-151">对象行为</span><span class="sxs-lookup"><span data-stu-id="6a89c-151">Object Behavior</span></span>](optimizing-performance-object-behavior.md)
- [<span data-ttu-id="6a89c-152">应用程序资源</span><span class="sxs-lookup"><span data-stu-id="6a89c-152">Application Resources</span></span>](optimizing-performance-application-resources.md)
- [<span data-ttu-id="6a89c-153">文本</span><span class="sxs-lookup"><span data-stu-id="6a89c-153">Text</span></span>](optimizing-performance-text.md)
- [<span data-ttu-id="6a89c-154">数据绑定</span><span class="sxs-lookup"><span data-stu-id="6a89c-154">Data Binding</span></span>](optimizing-performance-data-binding.md)
- [<span data-ttu-id="6a89c-155">动画提示和技巧</span><span class="sxs-lookup"><span data-stu-id="6a89c-155">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
