---
title: 优化性能：布局和设计
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- layout [WPF], optimizing performance
- design considerations [WPF]
- layout pass [WPF]
ms.assetid: 005f4cda-a849-448b-916b-38d14d9a96fe
ms.openlocfilehash: 2f3c1212746de54664d3a9ad5e11af3790d1e269
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666831"
---
# <a name="optimizing-performance-layout-and-design"></a><span data-ttu-id="2cd81-102">优化性能：布局和设计</span><span class="sxs-lookup"><span data-stu-id="2cd81-102">Optimizing Performance: Layout and Design</span></span>
<span data-ttu-id="2cd81-103">[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 应用程序的设计在计算布局和验证对象引用时会产生不必要的开销，从而影响性能。</span><span class="sxs-lookup"><span data-stu-id="2cd81-103">The design of your [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] application can impact its performance by creating unnecessary overhead in calculating layout and validating object references.</span></span> <span data-ttu-id="2cd81-104">对象的构造会影响应用程序的性能特征，在运行时更是如此。</span><span class="sxs-lookup"><span data-stu-id="2cd81-104">The construction of objects, particularly at run time, can affect the performance characteristics of your application.</span></span>  
  
 <span data-ttu-id="2cd81-105">本主题提供这些方面的性能改进建议。</span><span class="sxs-lookup"><span data-stu-id="2cd81-105">This topic provides performance recommendations in these areas.</span></span>  
  
## <a name="layout"></a><span data-ttu-id="2cd81-106">Layout</span><span class="sxs-lookup"><span data-stu-id="2cd81-106">Layout</span></span>  
 <span data-ttu-id="2cd81-107">术语 "布局传递" 描述了测量和排列 <xref:System.Windows.Controls.Panel> 派生对象的子集合成员的过程，然后在屏幕上绘制它们。</span><span class="sxs-lookup"><span data-stu-id="2cd81-107">The term "layout pass" describes the process of measuring and arranging the members of a <xref:System.Windows.Controls.Panel>-derived object's collection of children, and then drawing them onscreen.</span></span> <span data-ttu-id="2cd81-108">布局处理过程是一个数学密集型过程，即：集合中的子级数目越多，所需的计算量就越大。</span><span class="sxs-lookup"><span data-stu-id="2cd81-108">The layout pass is a mathematically-intensive process—the larger the number of children in the collection, the greater the number of calculations required.</span></span> <span data-ttu-id="2cd81-109">例如，当集合中的某个子 <xref:System.Windows.UIElement> 对象改变其位置时，布局系统就有可能触发一个新的传递。</span><span class="sxs-lookup"><span data-stu-id="2cd81-109">For example, each time a child <xref:System.Windows.UIElement> object in the collection changes its position, it has the potential to trigger a new pass by the layout system.</span></span> <span data-ttu-id="2cd81-110">由于对象特征与布局行为之间的关系非常紧密，因此有必要了解可以调用布局系统的事件类型。</span><span class="sxs-lookup"><span data-stu-id="2cd81-110">Because of the close relationship between object characteristics and layout behavior, it's important to understand the type of events that can invoke the layout system.</span></span> <span data-ttu-id="2cd81-111">应用程序将尽可能减少不必要的布局处理过程调用，从而改善性能。</span><span class="sxs-lookup"><span data-stu-id="2cd81-111">Your application will perform better by reducing as much as possible any unnecessary invocations of the layout pass.</span></span>  
  
 <span data-ttu-id="2cd81-112">布局系统对集合中的每个子成员都完成两个处理过程：测量处理过程和排列处理过程。</span><span class="sxs-lookup"><span data-stu-id="2cd81-112">The layout system completes two passes for each child member in a collection: a measure pass, and an arrange pass.</span></span> <span data-ttu-id="2cd81-113">每个子对象都提供其自己的和方法的重写实现 <xref:System.Windows.UIElement.Measure%2A> ，以便 <xref:System.Windows.UIElement.Arrange%2A> 提供自己的特定布局行为。</span><span class="sxs-lookup"><span data-stu-id="2cd81-113">Each child object provides its own overridden implementation of the <xref:System.Windows.UIElement.Measure%2A> and <xref:System.Windows.UIElement.Arrange%2A> methods in order to provide its own specific layout behavior.</span></span> <span data-ttu-id="2cd81-114">简单地说，布局是一个递归系统，实现在屏幕上对元素进行大小调整、定位和绘制。</span><span class="sxs-lookup"><span data-stu-id="2cd81-114">At its simplest, layout is a recursive system that leads to an element being sized, positioned, and drawn onscreen.</span></span>  
  
- <span data-ttu-id="2cd81-115">子 <xref:System.Windows.UIElement> 对象通过首先测量其核心属性来开始布局过程。</span><span class="sxs-lookup"><span data-stu-id="2cd81-115">A child <xref:System.Windows.UIElement> object begins the layout process by first having its core properties measured.</span></span>  
  
- <span data-ttu-id="2cd81-116"><xref:System.Windows.FrameworkElement>计算与 size 相关的对象的属性，如、 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> 和 <xref:System.Windows.FrameworkElement.Margin%2A> 。</span><span class="sxs-lookup"><span data-stu-id="2cd81-116">The object's <xref:System.Windows.FrameworkElement> properties that are related to size, such as <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, and <xref:System.Windows.FrameworkElement.Margin%2A>, are evaluated.</span></span>  
  
- <span data-ttu-id="2cd81-117"><xref:System.Windows.Controls.Panel>应用特定的逻辑，例如的 <xref:System.Windows.Controls.DockPanel.Dock%2A> 属性 <xref:System.Windows.Controls.DockPanel> 或的 <xref:System.Windows.Controls.StackPanel.Orientation%2A> 属性 <xref:System.Windows.Controls.StackPanel> 。</span><span class="sxs-lookup"><span data-stu-id="2cd81-117"><xref:System.Windows.Controls.Panel>-specific logic is applied, such as the <xref:System.Windows.Controls.DockPanel.Dock%2A> property of the <xref:System.Windows.Controls.DockPanel>, or the <xref:System.Windows.Controls.StackPanel.Orientation%2A> property of the <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
- <span data-ttu-id="2cd81-118">在测量所有的子对象后，将排列或定位内容。</span><span class="sxs-lookup"><span data-stu-id="2cd81-118">Content is arranged, or positioned, after all child objects have been measured.</span></span>  
  
- <span data-ttu-id="2cd81-119">将子对象集合绘制到屏幕上。</span><span class="sxs-lookup"><span data-stu-id="2cd81-119">The collection of child objects is drawn to the screen.</span></span>  
  
 <span data-ttu-id="2cd81-120">如果发生下列任一操作，将再次调用布局处理过程：</span><span class="sxs-lookup"><span data-stu-id="2cd81-120">The layout pass process is invoked again if any of the following actions occur:</span></span>  
  
- <span data-ttu-id="2cd81-121">向集合中添加了一个子对象。</span><span class="sxs-lookup"><span data-stu-id="2cd81-121">A child object is added to the collection.</span></span>  
  
- <span data-ttu-id="2cd81-122">将 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 应用于子对象。</span><span class="sxs-lookup"><span data-stu-id="2cd81-122">A <xref:System.Windows.FrameworkElement.LayoutTransform%2A> is applied to the child object.</span></span>  
  
- <span data-ttu-id="2cd81-123">为 <xref:System.Windows.UIElement.UpdateLayout%2A> 子对象调用方法。</span><span class="sxs-lookup"><span data-stu-id="2cd81-123">The <xref:System.Windows.UIElement.UpdateLayout%2A> method is called for the child object.</span></span>  
  
- <span data-ttu-id="2cd81-124">使用影响测量或排列过程的元数据进行标记的依赖属性的值发生更改时。</span><span class="sxs-lookup"><span data-stu-id="2cd81-124">When a change occurs to the value of a dependency property that is marked with metadata affecting the measure or arrange passes.</span></span>  
  
### <a name="use-the-most-efficient-panel-where-possible"></a><span data-ttu-id="2cd81-125">尽可能使用最高效的面板</span><span class="sxs-lookup"><span data-stu-id="2cd81-125">Use the Most Efficient Panel where Possible</span></span>  
 <span data-ttu-id="2cd81-126">布局过程的复杂程度直接取决于所使用的派生元素的布局行为 <xref:System.Windows.Controls.Panel> 。</span><span class="sxs-lookup"><span data-stu-id="2cd81-126">The complexity of the layout process is directly based on the layout behavior of the <xref:System.Windows.Controls.Panel>-derived elements you use.</span></span> <span data-ttu-id="2cd81-127">例如， <xref:System.Windows.Controls.Grid> 或 <xref:System.Windows.Controls.StackPanel> 控件提供比控件更多的功能 <xref:System.Windows.Controls.Canvas> 。</span><span class="sxs-lookup"><span data-stu-id="2cd81-127">For example, a <xref:System.Windows.Controls.Grid> or <xref:System.Windows.Controls.StackPanel> control provides much more functionality than a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="2cd81-128">功能大幅度改进的代价是性能成本的大幅度提高。</span><span class="sxs-lookup"><span data-stu-id="2cd81-128">The price for this greater increase in functionality is a greater increase in performance costs.</span></span> <span data-ttu-id="2cd81-129">但是，如果不需要 <xref:System.Windows.Controls.Grid> 控件提供的功能，则应使用成本较低的替代项，例如 <xref:System.Windows.Controls.Canvas> 或自定义面板。</span><span class="sxs-lookup"><span data-stu-id="2cd81-129">However, if you do not require the functionality that a <xref:System.Windows.Controls.Grid> control provides, you should use the less costly alternatives, such as a <xref:System.Windows.Controls.Canvas> or a custom panel.</span></span>  
  
 <span data-ttu-id="2cd81-130">有关详细信息，请参阅[面板概述](../controls/panels-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2cd81-130">For more information, see [Panels Overview](../controls/panels-overview.md).</span></span>  
  
### <a name="update-rather-than-replace-a-rendertransform"></a><span data-ttu-id="2cd81-131">更新而不替换 RenderTransform</span><span class="sxs-lookup"><span data-stu-id="2cd81-131">Update Rather than Replace a RenderTransform</span></span>  
 <span data-ttu-id="2cd81-132">您可以更新， <xref:System.Windows.Media.Transform> 而不是将其替换为属性的值 <xref:System.Windows.UIElement.RenderTransform%2A> 。</span><span class="sxs-lookup"><span data-stu-id="2cd81-132">You may be able to update a <xref:System.Windows.Media.Transform> rather than replacing it as the value of a <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span> <span data-ttu-id="2cd81-133">在涉及动画的方案中，尤其是这样。</span><span class="sxs-lookup"><span data-stu-id="2cd81-133">This is particularly true in scenarios that involve animation.</span></span> <span data-ttu-id="2cd81-134">通过更新现有的 <xref:System.Windows.Media.Transform> ，可避免启动不必要的布局计算。</span><span class="sxs-lookup"><span data-stu-id="2cd81-134">By updating an existing <xref:System.Windows.Media.Transform>, you avoid initiating an unnecessary layout calculation.</span></span>  
  
### <a name="build-your-tree-top-down"></a><span data-ttu-id="2cd81-135">从上到下生成树</span><span class="sxs-lookup"><span data-stu-id="2cd81-135">Build Your Tree Top-Down</span></span>  
 <span data-ttu-id="2cd81-136">在逻辑树中添加或删除节点时，会在该节点的父级及其所有子级上引起属性失效。</span><span class="sxs-lookup"><span data-stu-id="2cd81-136">When a node is added or removed from the logical tree, property invalidations are raised on the node's parent and all its children.</span></span> <span data-ttu-id="2cd81-137">因此，应始终遵循从上到下的构造模式，以避免由于在经过验证的节点中出现不必要的失效而付出代价。</span><span class="sxs-lookup"><span data-stu-id="2cd81-137">As a result, a top-down construction pattern should always be followed to avoid the cost of unnecessary invalidations on nodes that have already been validated.</span></span> <span data-ttu-id="2cd81-138">下表显示了从上到下构建树与从下到下的深度之间的执行速度之间的差异，其中，树的深度为150级别， <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.DockPanel> 每个级别有一个。</span><span class="sxs-lookup"><span data-stu-id="2cd81-138">The following table shows the difference in execution speed between building a tree top-down versus bottom-up, where the tree is 150 levels deep with a single <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Controls.DockPanel> at each level.</span></span>  
  
|<span data-ttu-id="2cd81-139">**操作**</span><span class="sxs-lookup"><span data-stu-id="2cd81-139">**Action**</span></span>|<span data-ttu-id="2cd81-140">**构建树（以毫秒为单位）**</span><span class="sxs-lookup"><span data-stu-id="2cd81-140">**Tree building (in ms)**</span></span>|<span data-ttu-id="2cd81-141">**呈现 - 包括生成树（以毫秒为单位）**</span><span class="sxs-lookup"><span data-stu-id="2cd81-141">**Render—includes tree building (in ms)**</span></span>|  
|----------------|---------------------------------|-------------------------------------------------|  
|<span data-ttu-id="2cd81-142">从下到上</span><span class="sxs-lookup"><span data-stu-id="2cd81-142">Bottom-up</span></span>|<span data-ttu-id="2cd81-143">366</span><span class="sxs-lookup"><span data-stu-id="2cd81-143">366</span></span>|<span data-ttu-id="2cd81-144">454</span><span class="sxs-lookup"><span data-stu-id="2cd81-144">454</span></span>|  
|<span data-ttu-id="2cd81-145">从上到下</span><span class="sxs-lookup"><span data-stu-id="2cd81-145">Top-down</span></span>|<span data-ttu-id="2cd81-146">11</span><span class="sxs-lookup"><span data-stu-id="2cd81-146">11</span></span>|<span data-ttu-id="2cd81-147">96</span><span class="sxs-lookup"><span data-stu-id="2cd81-147">96</span></span>|  
  
 <span data-ttu-id="2cd81-148">以下代码示例演示如何从上到下创建树。</span><span class="sxs-lookup"><span data-stu-id="2cd81-148">The following code example demonstrates how to create a tree top down.</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet1)]
 [!code-vb[Performance#PerformanceSnippet1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet1)]  
  
 <span data-ttu-id="2cd81-149">有关逻辑树的详细信息，请参阅 [WPF 中的树](trees-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="2cd81-149">For more information on the logical tree, see [Trees in WPF](trees-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cd81-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="2cd81-150">See also</span></span>

- [<span data-ttu-id="2cd81-151">优化 WPF 应用程序性能</span><span class="sxs-lookup"><span data-stu-id="2cd81-151">Optimizing WPF Application Performance</span></span>](optimizing-wpf-application-performance.md)
- [<span data-ttu-id="2cd81-152">规划应用程序性能</span><span class="sxs-lookup"><span data-stu-id="2cd81-152">Planning for Application Performance</span></span>](planning-for-application-performance.md)
- [<span data-ttu-id="2cd81-153">利用硬件</span><span class="sxs-lookup"><span data-stu-id="2cd81-153">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)
- [<span data-ttu-id="2cd81-154">二维图形和图像处理</span><span class="sxs-lookup"><span data-stu-id="2cd81-154">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="2cd81-155">对象行为</span><span class="sxs-lookup"><span data-stu-id="2cd81-155">Object Behavior</span></span>](optimizing-performance-object-behavior.md)
- [<span data-ttu-id="2cd81-156">应用程序资源</span><span class="sxs-lookup"><span data-stu-id="2cd81-156">Application Resources</span></span>](optimizing-performance-application-resources.md)
- [<span data-ttu-id="2cd81-157">文本</span><span class="sxs-lookup"><span data-stu-id="2cd81-157">Text</span></span>](optimizing-performance-text.md)
- [<span data-ttu-id="2cd81-158">数据绑定</span><span class="sxs-lookup"><span data-stu-id="2cd81-158">Data Binding</span></span>](optimizing-performance-data-binding.md)
- [<span data-ttu-id="2cd81-159">其他性能建议</span><span class="sxs-lookup"><span data-stu-id="2cd81-159">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)
- [<span data-ttu-id="2cd81-160">布局</span><span class="sxs-lookup"><span data-stu-id="2cd81-160">Layout</span></span>](layout.md)
