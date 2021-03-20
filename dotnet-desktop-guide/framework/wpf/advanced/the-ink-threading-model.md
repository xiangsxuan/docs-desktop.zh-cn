---
title: 墨迹线程处理模型
ms.date: 03/30/2017
helpviewer_keywords:
- application user interface thread [WPF]
- stylus plug-in
- ink threading model [WPF]
- ink [WPF], rendering
- pen thread [WPF]
- threading model [WPF]
- rendering ink [WPF]
- dynamic rendering thread [WPF]
- ink collection plug-in
- plug-ins [WPF], for ink
ms.assetid: c85fcad1-cb50-4431-847c-ac4145a35c89
ms.openlocfilehash: 397013eba82ac2d1a3918456b9b492272dfa4272
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664771"
---
# <a name="the-ink-threading-model"></a><span data-ttu-id="1e923-102">墨迹线程处理模型</span><span class="sxs-lookup"><span data-stu-id="1e923-102">The Ink Threading Model</span></span>
<span data-ttu-id="1e923-103">在 Tablet PC 上，墨迹的优点之一就是，它很喜欢用常规笔和纸张书写。</span><span class="sxs-lookup"><span data-stu-id="1e923-103">One of the benefits of ink on a Tablet PC is that it feels a lot like writing with a regular pen and paper.</span></span>  <span data-ttu-id="1e923-104">为实现此目的，tablet 笔以比鼠标更高的速率收集输入数据，并在用户写入时呈现墨迹。</span><span class="sxs-lookup"><span data-stu-id="1e923-104">To accomplish this, the tablet pen collects input data at a much higher rate than a mouse does and renders the ink as the user writes.</span></span>  <span data-ttu-id="1e923-105">应用程序的用户界面 (UI) 线程不足以收集笔数据和呈现墨迹，因为它可能会被阻止。</span><span class="sxs-lookup"><span data-stu-id="1e923-105">The application's user interface (UI) thread is not sufficient for collecting pen data and rendering ink, because it can become blocked.</span></span>  <span data-ttu-id="1e923-106">若要解决此 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 情况，应用程序会在用户写入墨迹时使用另外两个线程。</span><span class="sxs-lookup"><span data-stu-id="1e923-106">To solve this, a [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] application uses two additional threads when a user writes ink.</span></span>  
  
 <span data-ttu-id="1e923-107">下面的列表介绍了收集和呈现数字墨迹的线程：</span><span class="sxs-lookup"><span data-stu-id="1e923-107">The following list describes the threads that take part in collecting and rendering digital ink:</span></span>  
  
- <span data-ttu-id="1e923-108">"笔线程"-采用触笔输入的线程。</span><span class="sxs-lookup"><span data-stu-id="1e923-108">Pen thread - the thread that takes input from the stylus.</span></span>  <span data-ttu-id="1e923-109"> (事实上，这是一个线程池，但本主题将其称为笔线程。 ) </span><span class="sxs-lookup"><span data-stu-id="1e923-109">(In reality, this is a thread pool, but this topic refers to it as a pen thread.)</span></span>  
  
- <span data-ttu-id="1e923-110">应用程序用户界面线程-控制应用程序的用户界面的线程。</span><span class="sxs-lookup"><span data-stu-id="1e923-110">Application user interface thread - the thread that controls the user interface of the application.</span></span>  
  
- <span data-ttu-id="1e923-111">动态呈现线程-用户绘制笔划时呈现墨迹的线程。</span><span class="sxs-lookup"><span data-stu-id="1e923-111">Dynamic rendering thread - the thread that renders the ink while the user draws a stroke.</span></span> <span data-ttu-id="1e923-112">动态呈现线程不同于呈现应用程序的其他 UI 元素的线程，如 Window Presentation Foundation [线程模型](threading-model.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="1e923-112">The dynamic rendering thread is different than the thread that renders other UI elements for the application, as mentioned in Window Presentation Foundation [Threading Model](threading-model.md).</span></span>  
  
 <span data-ttu-id="1e923-113">无论应用程序使用的是 <xref:System.Windows.Controls.InkCanvas> 还是与 [创建墨迹输入控件](creating-an-ink-input-control.md)中的控件类似的自定义控件，墨迹模型都是相同的。</span><span class="sxs-lookup"><span data-stu-id="1e923-113">The inking model is the same whether the application uses the <xref:System.Windows.Controls.InkCanvas> or a custom control similar to the one in [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  <span data-ttu-id="1e923-114">尽管本主题讨论了中的线程处理 <xref:System.Windows.Controls.InkCanvas> ，但在创建自定义控件时，相同的概念也同样适用。</span><span class="sxs-lookup"><span data-stu-id="1e923-114">Although this topic discusses threading in terms of the <xref:System.Windows.Controls.InkCanvas>, the same concepts apply when you create a custom control.</span></span>  
  
## <a name="threading-overview"></a><span data-ttu-id="1e923-115">线程处理概述</span><span class="sxs-lookup"><span data-stu-id="1e923-115">Threading Overview</span></span>  
 <span data-ttu-id="1e923-116">下图演示了用户绘制笔画时的线程处理模型：</span><span class="sxs-lookup"><span data-stu-id="1e923-116">The following diagram illustrates the threading model when a user draws a stroke:</span></span>  
  
 <span data-ttu-id="1e923-117">![绘制笔画时的线程处理模型。](./media/inkthreading-drawingink.png "InkThreading_DrawingInk")</span><span class="sxs-lookup"><span data-stu-id="1e923-117">![Threading model while drawing a stroke.](./media/inkthreading-drawingink.png "InkThreading_DrawingInk")</span></span>  
  
1. <span data-ttu-id="1e923-118">用户绘制笔划时发生的操作</span><span class="sxs-lookup"><span data-stu-id="1e923-118">Actions occurring while the user draws the stroke</span></span>  
  
    1. <span data-ttu-id="1e923-119">当用户绘制笔画时，触笔接触点将进入笔线程。</span><span class="sxs-lookup"><span data-stu-id="1e923-119">When the user draws a stroke, the stylus points come in on the pen thread.</span></span>  <span data-ttu-id="1e923-120">触笔插件（包括 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> ）接受触笔线程上的触笔接触点，并且有机会在接收它们之前修改它们 <xref:System.Windows.Controls.InkCanvas> 。</span><span class="sxs-lookup"><span data-stu-id="1e923-120">Stylus plug-ins, including the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, accept the stylus points on the pen thread and have the chance to modify them before the <xref:System.Windows.Controls.InkCanvas> receives them.</span></span>  
  
    2. <span data-ttu-id="1e923-121"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>呈现动态呈现线程上的触笔接触点。</span><span class="sxs-lookup"><span data-stu-id="1e923-121">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> renders the stylus points on the dynamic rendering thread.</span></span> <span data-ttu-id="1e923-122">这与上一步相同。</span><span class="sxs-lookup"><span data-stu-id="1e923-122">This happens at the same time as the previous step.</span></span>  
  
    3. <span data-ttu-id="1e923-123"><xref:System.Windows.Controls.InkCanvas>接收 UI 线程上的触笔接触点。</span><span class="sxs-lookup"><span data-stu-id="1e923-123">The <xref:System.Windows.Controls.InkCanvas> receives the stylus points on the UI thread.</span></span>  
  
2. <span data-ttu-id="1e923-124">用户结束笔画后发生的操作</span><span class="sxs-lookup"><span data-stu-id="1e923-124">Actions occurring after the user ends the stroke</span></span>  
  
    1. <span data-ttu-id="1e923-125">当用户完成绘制笔划后，将 <xref:System.Windows.Controls.InkCanvas> 创建一个 <xref:System.Windows.Ink.Stroke> 对象，并将其添加到 <xref:System.Windows.Controls.InkPresenter> 中以静态方式呈现该对象。</span><span class="sxs-lookup"><span data-stu-id="1e923-125">When the user finishes drawing the stroke, the <xref:System.Windows.Controls.InkCanvas> creates a <xref:System.Windows.Ink.Stroke> object and adds it to the <xref:System.Windows.Controls.InkPresenter>, which statically renders it.</span></span>  
  
    2. <span data-ttu-id="1e923-126">UI 线程会发出通知， <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 指示笔划是以静态方式呈现的，因此删除了笔划的 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 视觉表示形式。</span><span class="sxs-lookup"><span data-stu-id="1e923-126">The UI thread alerts the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> that the stroke is statically rendered, so the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> removes its visual representation of the stroke.</span></span>  
  
## <a name="ink-collection-and-stylus-plug-ins"></a><span data-ttu-id="1e923-127">墨迹收集和触笔插件</span><span class="sxs-lookup"><span data-stu-id="1e923-127">Ink collection and Stylus Plug-ins</span></span>  
 <span data-ttu-id="1e923-128">每个 <xref:System.Windows.UIElement> 都有一个 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 。</span><span class="sxs-lookup"><span data-stu-id="1e923-128">Each <xref:System.Windows.UIElement> has a <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.</span></span>  <span data-ttu-id="1e923-129"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>接收和中的对象 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 可以修改笔线程上的触笔接触点。</span><span class="sxs-lookup"><span data-stu-id="1e923-129">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> receive and can modify the stylus points on the pen thread.</span></span> <span data-ttu-id="1e923-130"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>对象根据其在中的顺序接收触笔接触点 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 。</span><span class="sxs-lookup"><span data-stu-id="1e923-130">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects receive the stylus points according to their order in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.</span></span>  
  
 <span data-ttu-id="1e923-131">下图说明了的 <xref:System.Windows.UIElement.StylusPlugIns%2A> 集合的集合 <xref:System.Windows.UIElement> ，其中包含 `stylusPlugin1` 、 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 和 `stylusPlugin2` 的假设情况。</span><span class="sxs-lookup"><span data-stu-id="1e923-131">The following diagram illustrates the hypothetical situation where the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection of a <xref:System.Windows.UIElement> contains `stylusPlugin1`, a <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, and `stylusPlugin2`, in that order.</span></span>  
  
 <span data-ttu-id="1e923-132">![触笔插件影响输出的顺序。](./media/inkthreading-pluginorder.png "InkThreading_PluginOrder")</span><span class="sxs-lookup"><span data-stu-id="1e923-132">![Order of Stylus Plugins affect output.](./media/inkthreading-pluginorder.png "InkThreading_PluginOrder")</span></span>  
  
 <span data-ttu-id="1e923-133">在上图中，将发生以下行为：</span><span class="sxs-lookup"><span data-stu-id="1e923-133">In the previous diagram, the following behavior takes place:</span></span>  
  
1. <span data-ttu-id="1e923-134">`StylusPlugin1` 修改 x 和 y 的值。</span><span class="sxs-lookup"><span data-stu-id="1e923-134">`StylusPlugin1` modifies the values for x and y.</span></span>  
  
2. <span data-ttu-id="1e923-135"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 接收经过修改的触笔接触点，并将其呈现在动态呈现线程上。</span><span class="sxs-lookup"><span data-stu-id="1e923-135"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> receives the modified stylus points and renders them on the dynamic rendering thread.</span></span>  
  
3. <span data-ttu-id="1e923-136">`StylusPlugin2` 接收经过修改的触笔接触点，并进一步修改 x 和 y 的值。</span><span class="sxs-lookup"><span data-stu-id="1e923-136">`StylusPlugin2` receives the modified stylus points and further modifies the values for x and y.</span></span>  
  
4. <span data-ttu-id="1e923-137">应用程序收集触笔接触点，当用户完成笔划时，静态呈现笔画。</span><span class="sxs-lookup"><span data-stu-id="1e923-137">The application collects the stylus points, and, when the user finishes the stroke, statically renders the stroke.</span></span>  
  
 <span data-ttu-id="1e923-138">假设 `stylusPlugin1` 将触笔指向矩形，并将 `stylusPlugin2` 触笔点向右平移。</span><span class="sxs-lookup"><span data-stu-id="1e923-138">Suppose that `stylusPlugin1` restricts the stylus points to a rectangle and `stylusPlugin2` translates the stylus points to the right.</span></span>  <span data-ttu-id="1e923-139">在前面的方案中， <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 会接收受限制的触笔接触点，但不接收已平移的触笔接触点。</span><span class="sxs-lookup"><span data-stu-id="1e923-139">In the previous scenario, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> receives the restricted stylus points, but not the translated stylus points.</span></span>  <span data-ttu-id="1e923-140">当用户绘制笔划时，笔划将呈现在矩形的边界内，但在用户将笔提起之前，笔划不会转换。</span><span class="sxs-lookup"><span data-stu-id="1e923-140">When the user draws the stroke, the stroke is rendered within the bounds of the rectangle, but the stroke doesn't appear to be translated until the user lifts the pen.</span></span>  
  
### <a name="performing-operations-with-a-stylus-plug-in-on-the-ui-thread"></a><span data-ttu-id="1e923-141">在 UI 线程上使用触笔插件执行操作</span><span class="sxs-lookup"><span data-stu-id="1e923-141">Performing operations with a Stylus Plug-in on the UI thread</span></span>  
 <span data-ttu-id="1e923-142">由于无法对笔线程执行准确的命中测试，某些元素可能偶尔接收到用于其他元素的触笔输入。</span><span class="sxs-lookup"><span data-stu-id="1e923-142">Because accurate hit-testing cannot be performed on the pen thread, some elements might occasionally receive stylus input intended for other elements.</span></span> <span data-ttu-id="1e923-143">如果在执行操作之前需要确保正确路由输入，请在 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A> 、或方法中订阅并执行该操作 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A> <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A> 。</span><span class="sxs-lookup"><span data-stu-id="1e923-143">If you need to make sure the input was routed correctly before performing an operation, subscribe to and perform the operation in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A>, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A>, or <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A> method.</span></span> <span data-ttu-id="1e923-144">执行准确的命中测试后，应用程序线程会调用这些方法。</span><span class="sxs-lookup"><span data-stu-id="1e923-144">These methods are invoked by the application thread after accurate hit-testing has been performed.</span></span> <span data-ttu-id="1e923-145">若要订阅这些方法，请 <xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A> 在笔线程上出现的方法中调用方法。</span><span class="sxs-lookup"><span data-stu-id="1e923-145">To subscribe to these methods, call the <xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A> method in the method that occurs on the pen thread.</span></span>  
  
 <span data-ttu-id="1e923-146">下图演示了与的触笔事件相关的笔线程和 UI 线程之间的关系 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 。</span><span class="sxs-lookup"><span data-stu-id="1e923-146">The following diagram illustrates the relationship between the pen thread and UI thread with respect to the stylus events of a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.</span></span>  
  
 <span data-ttu-id="1e923-147">![&#40;UI 和笔&#41;的墨迹线程模型 ](./media/inkthreading-plugincallbacks.png "InkThreading_PluginCallbacks")</span><span class="sxs-lookup"><span data-stu-id="1e923-147">![Ink Threading Models &#40;UI and Pen&#41;](./media/inkthreading-plugincallbacks.png "InkThreading_PluginCallbacks")</span></span>  
  
## <a name="rendering-ink"></a><span data-ttu-id="1e923-148">呈现墨迹</span><span class="sxs-lookup"><span data-stu-id="1e923-148">Rendering Ink</span></span>  
 <span data-ttu-id="1e923-149">当用户绘制笔画时，将 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 在单独的线程上呈现墨迹，以便即使在 UI 线程繁忙的情况下，墨迹仍会显示为 "流"。</span><span class="sxs-lookup"><span data-stu-id="1e923-149">As the user draws a stroke, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> renders the ink on a separate thread so the ink appears to "flow" from the pen even when the UI thread is busy.</span></span>  <span data-ttu-id="1e923-150"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>当收集触笔接触点时，会在动态呈现线程上生成一个可视化树。</span><span class="sxs-lookup"><span data-stu-id="1e923-150">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> builds a visual tree on the dynamic rendering thread as it collects stylus points.</span></span>  <span data-ttu-id="1e923-151">当用户完成笔划时，将在 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 应用程序执行下一次呈现时通知请求。</span><span class="sxs-lookup"><span data-stu-id="1e923-151">When the user finishes the stroke, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> asks to be notified when the application does the next rendering pass.</span></span>  <span data-ttu-id="1e923-152">在应用程序完成下一次呈现过程后，将 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 清理其可视化树。</span><span class="sxs-lookup"><span data-stu-id="1e923-152">After the application completes the next rendering pass, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> cleans up its visual tree.</span></span>  <span data-ttu-id="1e923-153">下图演示了此过程。</span><span class="sxs-lookup"><span data-stu-id="1e923-153">The following diagram illustrates this process.</span></span>  
  
 <span data-ttu-id="1e923-154">![墨迹线程处理示意图](./media/inkthreading-visualtree.png "InkThreading_VisualTree")</span><span class="sxs-lookup"><span data-stu-id="1e923-154">![Ink threading diagram](./media/inkthreading-visualtree.png "InkThreading_VisualTree")</span></span>  
  
1. <span data-ttu-id="1e923-155">用户开始描边。</span><span class="sxs-lookup"><span data-stu-id="1e923-155">The user begins the stroke.</span></span>  
  
    1. <span data-ttu-id="1e923-156"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>创建可视化树。</span><span class="sxs-lookup"><span data-stu-id="1e923-156">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> creates the visual tree.</span></span>  
  
2. <span data-ttu-id="1e923-157">用户正在绘制笔划。</span><span class="sxs-lookup"><span data-stu-id="1e923-157">The user is drawing the stroke.</span></span>  
  
    1. <span data-ttu-id="1e923-158"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>生成可视化树。</span><span class="sxs-lookup"><span data-stu-id="1e923-158">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> builds the visual tree.</span></span>  
  
3. <span data-ttu-id="1e923-159">用户结束笔画。</span><span class="sxs-lookup"><span data-stu-id="1e923-159">The user ends the stroke.</span></span>  
  
    1. <span data-ttu-id="1e923-160">将 <xref:System.Windows.Controls.InkPresenter> 笔画添加到其可视化树中。</span><span class="sxs-lookup"><span data-stu-id="1e923-160">The <xref:System.Windows.Controls.InkPresenter> adds the stroke to its visual tree.</span></span>  
  
    2. <span data-ttu-id="1e923-161">媒体集成层 (MIL) 静态呈现笔画。</span><span class="sxs-lookup"><span data-stu-id="1e923-161">The Media Integration Layer (MIL) statically renders the strokes.</span></span>  
  
    3. <span data-ttu-id="1e923-162"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>清除视觉对象。</span><span class="sxs-lookup"><span data-stu-id="1e923-162">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> cleans up the visuals.</span></span>
