---
title: ScrollViewer 概述
description: 了解 ScrollViewer 控件，该控件可用于在 Windows Presentation Foundation 的应用程序中滚动内容。 请参阅使用示例。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], ScrollViewer
- ScrollViewer control [WPF], about ScrollViewer control
ms.assetid: 94a13b94-cfdf-4b12-a1aa-90cb50c6e9b9
ms.openlocfilehash: a99fdd43bab7075aab3aa0193fe84ea4650566b7
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665232"
---
# <a name="scrollviewer-overview"></a><span data-ttu-id="4a93c-104">ScrollViewer 概述</span><span class="sxs-lookup"><span data-stu-id="4a93c-104">ScrollViewer Overview</span></span>

<span data-ttu-id="4a93c-105">用户界面中的内容通常比计算机屏幕的显示区域大。</span><span class="sxs-lookup"><span data-stu-id="4a93c-105">Content within a user interface is often larger than a computer screen's display area.</span></span> <span data-ttu-id="4a93c-106"><xref:System.Windows.Controls.ScrollViewer>控件提供了一种简便的方式来实现在应用程序中滚动内容 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="4a93c-106">The <xref:System.Windows.Controls.ScrollViewer> control provides a convenient way to enable scrolling of content in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="4a93c-107">本主题介绍 <xref:System.Windows.Controls.ScrollViewer> 元素并提供多个用法示例。</span><span class="sxs-lookup"><span data-stu-id="4a93c-107">This topic introduces the <xref:System.Windows.Controls.ScrollViewer> element and provides several usage examples.</span></span>  
  
<a name="what_is_a_scrollviewer_element"></a>

## <a name="the-scrollviewer-control"></a><span data-ttu-id="4a93c-108">ScrollViewer 控件</span><span class="sxs-lookup"><span data-stu-id="4a93c-108">The ScrollViewer Control</span></span>  

 <span data-ttu-id="4a93c-109">在应用程序中，有两个可用于滚动的预定义元素 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ： <xref:System.Windows.Controls.Primitives.ScrollBar> 和 <xref:System.Windows.Controls.ScrollViewer> 。</span><span class="sxs-lookup"><span data-stu-id="4a93c-109">There are two predefined elements that enable scrolling in [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] applications: <xref:System.Windows.Controls.Primitives.ScrollBar> and <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="4a93c-110"><xref:System.Windows.Controls.ScrollViewer>控件封装水平和垂直 <xref:System.Windows.Controls.Primitives.ScrollBar> 元素以及内容容器 (如 <xref:System.Windows.Controls.Panel> 元素) 以便显示可滚动区域中的其他可见元素。</span><span class="sxs-lookup"><span data-stu-id="4a93c-110">The <xref:System.Windows.Controls.ScrollViewer> control encapsulates horizontal and vertical <xref:System.Windows.Controls.Primitives.ScrollBar> elements and a content container (such as a <xref:System.Windows.Controls.Panel> element) in order to display other visible elements in a scrollable area.</span></span> <span data-ttu-id="4a93c-111">必须生成自定义对象，才能将 <xref:System.Windows.Controls.Primitives.ScrollBar> 元素用于内容滚动。</span><span class="sxs-lookup"><span data-stu-id="4a93c-111">You must build a custom object in order to use the <xref:System.Windows.Controls.Primitives.ScrollBar> element for content scrolling.</span></span> <span data-ttu-id="4a93c-112">但是，您可以单独使用该 <xref:System.Windows.Controls.ScrollViewer> 元素，因为它是一个封装功能的复合控件 <xref:System.Windows.Controls.Primitives.ScrollBar> 。</span><span class="sxs-lookup"><span data-stu-id="4a93c-112">However, you can use the <xref:System.Windows.Controls.ScrollViewer> element by itself because it is a composite control that encapsulates <xref:System.Windows.Controls.Primitives.ScrollBar> functionality.</span></span>  
  
 <span data-ttu-id="4a93c-113"><xref:System.Windows.Controls.ScrollViewer>控件对鼠标和键盘命令做出响应，并定义了许多方法，通过预先确定的增量来滚动内容。</span><span class="sxs-lookup"><span data-stu-id="4a93c-113">The <xref:System.Windows.Controls.ScrollViewer> control responds to both mouse and keyboard commands, and defines numerous methods with which to scroll content by predetermined increments.</span></span> <span data-ttu-id="4a93c-114">可以使用 <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> 事件检测 <xref:System.Windows.Controls.ScrollViewer> 状态更改。</span><span class="sxs-lookup"><span data-stu-id="4a93c-114">You can use the <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> event to detect a change in a <xref:System.Windows.Controls.ScrollViewer> state.</span></span>  
  
 <span data-ttu-id="4a93c-115"><xref:System.Windows.Controls.ScrollViewer>只能有一个子元素（通常是 <xref:System.Windows.Controls.Panel> 可承载元素集合的元素） <xref:System.Windows.Controls.Panel.Children%2A> 。</span><span class="sxs-lookup"><span data-stu-id="4a93c-115">A <xref:System.Windows.Controls.ScrollViewer> can only have one child, typically a <xref:System.Windows.Controls.Panel> element that can host a <xref:System.Windows.Controls.Panel.Children%2A> collection of elements.</span></span> <span data-ttu-id="4a93c-116"><xref:System.Windows.Controls.ContentPresenter.Content%2A>属性定义的唯一子级 <xref:System.Windows.Controls.ScrollViewer> 。</span><span class="sxs-lookup"><span data-stu-id="4a93c-116">The <xref:System.Windows.Controls.ContentPresenter.Content%2A> property defines the sole child of the <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
<a name="scrollviewer_physical_vs_logical"></a>

## <a name="physical-vs-logical-scrolling"></a><span data-ttu-id="4a93c-117">物理滚动与逻辑滚动</span><span class="sxs-lookup"><span data-stu-id="4a93c-117">Physical vs. Logical Scrolling</span></span>  

 <span data-ttu-id="4a93c-118">物理滚动用于按预设的物理增量（通常按以像素为单位声明的值）滚动内容。</span><span class="sxs-lookup"><span data-stu-id="4a93c-118">Physical scrolling is used to scroll content by a predetermined physical increment, typically by a value that is declared in pixels.</span></span> <span data-ttu-id="4a93c-119">逻辑滚动用于滚动到逻辑树中的下一项。</span><span class="sxs-lookup"><span data-stu-id="4a93c-119">Logical scrolling is used to scroll to the next item in the logical tree.</span></span> <span data-ttu-id="4a93c-120">物理滚动是大多数元素的默认滚动行为 <xref:System.Windows.Controls.Panel> 。</span><span class="sxs-lookup"><span data-stu-id="4a93c-120">Physical scrolling is the default scroll behavior for most <xref:System.Windows.Controls.Panel> elements.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="4a93c-121">同时支持这两种类型的滚动。</span><span class="sxs-lookup"><span data-stu-id="4a93c-121">supports both types of scrolling.</span></span>  
  
#### <a name="the-iscrollinfo-interface"></a><span data-ttu-id="4a93c-122">IScrollInfo 接口</span><span class="sxs-lookup"><span data-stu-id="4a93c-122">The IScrollInfo Interface</span></span>  

 <span data-ttu-id="4a93c-123"><xref:System.Windows.Controls.Primitives.IScrollInfo>接口表示或派生控件内的主滚动区域 <xref:System.Windows.Controls.ScrollViewer> 。</span><span class="sxs-lookup"><span data-stu-id="4a93c-123">The <xref:System.Windows.Controls.Primitives.IScrollInfo> interface represents the main scrolling region within a <xref:System.Windows.Controls.ScrollViewer> or derived control.</span></span> <span data-ttu-id="4a93c-124">接口定义滚动属性和方法，这些属性和方法可由 <xref:System.Windows.Controls.Panel> 需要按逻辑单元（而不是物理增量）滚动的元素实现。</span><span class="sxs-lookup"><span data-stu-id="4a93c-124">The interface defines scrolling properties and methods that can be implemented by <xref:System.Windows.Controls.Panel> elements that require scrolling by logical unit, rather than by a physical increment.</span></span> <span data-ttu-id="4a93c-125">将的实例强制转换 <xref:System.Windows.Controls.Primitives.IScrollInfo> 为派生的 <xref:System.Windows.Controls.Panel> ，然后使用其滚动方法，可提供一种方法来滚动到子集合中的下一个逻辑单元，而不是按像素增量滚动到下一个逻辑单元。</span><span class="sxs-lookup"><span data-stu-id="4a93c-125">Casting an instance of <xref:System.Windows.Controls.Primitives.IScrollInfo> to a derived <xref:System.Windows.Controls.Panel> and then using its scrolling methods provides a useful way to scroll to the next logical unit in a child collection, rather than by pixel increment.</span></span> <span data-ttu-id="4a93c-126">默认情况下， <xref:System.Windows.Controls.ScrollViewer> 控件支持按物理单位滚动。</span><span class="sxs-lookup"><span data-stu-id="4a93c-126">By default, the <xref:System.Windows.Controls.ScrollViewer> control supports scrolling by physical units.</span></span>  
  
 <span data-ttu-id="4a93c-127"><xref:System.Windows.Controls.StackPanel> 和 <xref:System.Windows.Controls.VirtualizingStackPanel> 都实现 <xref:System.Windows.Controls.Primitives.IScrollInfo> 并本机支持逻辑滚动。</span><span class="sxs-lookup"><span data-stu-id="4a93c-127"><xref:System.Windows.Controls.StackPanel> and <xref:System.Windows.Controls.VirtualizingStackPanel> both implement <xref:System.Windows.Controls.Primitives.IScrollInfo> and natively support logical scrolling.</span></span> <span data-ttu-id="4a93c-128">对于本机支持逻辑滚动的布局控件，你仍可以通过将中的主机元素包装 <xref:System.Windows.Controls.Panel> 在中 <xref:System.Windows.Controls.ScrollViewer> 并将属性设置 <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> 为来 `false` 实现物理滚动。</span><span class="sxs-lookup"><span data-stu-id="4a93c-128">For layout controls that natively support logical scrolling, you can still achieve physical scrolling by wrapping the host <xref:System.Windows.Controls.Panel> element in a <xref:System.Windows.Controls.ScrollViewer> and setting the <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> property to `false`.</span></span>  
  
 <span data-ttu-id="4a93c-129">下面的代码示例演示如何将的实例强制转换 <xref:System.Windows.Controls.Primitives.IScrollInfo> 为 <xref:System.Windows.Controls.StackPanel> ，并使用内容滚动方法 (<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> 和 <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>) 由接口定义。</span><span class="sxs-lookup"><span data-stu-id="4a93c-129">The following code example demonstrates how to cast an instance of <xref:System.Windows.Controls.Primitives.IScrollInfo> to a <xref:System.Windows.Controls.StackPanel> and use content scrolling methods (<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> and <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>) defined by the interface.</span></span>  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>

## <a name="defining-and-using-a-scrollviewer-element"></a><span data-ttu-id="4a93c-130">定义和使用 ScrollViewer 元素</span><span class="sxs-lookup"><span data-stu-id="4a93c-130">Defining and Using a ScrollViewer Element</span></span>  

 <span data-ttu-id="4a93c-131">下面的示例 <xref:System.Windows.Controls.ScrollViewer> 在包含一些文本和一个矩形的窗口中创建一个。</span><span class="sxs-lookup"><span data-stu-id="4a93c-131">The following example creates a <xref:System.Windows.Controls.ScrollViewer> in a window that contains some text and a rectangle.</span></span> <span data-ttu-id="4a93c-132"><xref:System.Windows.Controls.Primitives.ScrollBar> 元素只有在必要时才会出现。</span><span class="sxs-lookup"><span data-stu-id="4a93c-132"><xref:System.Windows.Controls.Primitives.ScrollBar> elements appear only when they are necessary.</span></span> <span data-ttu-id="4a93c-133">当调整窗口的大小时， <xref:System.Windows.Controls.Primitives.ScrollBar> 元素将显示并消失，因为和属性的更新 <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> 值 <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> 。</span><span class="sxs-lookup"><span data-stu-id="4a93c-133">When you resize the window, the <xref:System.Windows.Controls.Primitives.ScrollBar> elements appear and disappear, due to updated values of the <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> and <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> properties.</span></span>  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>

## <a name="styling-a-scrollviewer"></a><span data-ttu-id="4a93c-134">设置 ScrollViewer 的样式</span><span class="sxs-lookup"><span data-stu-id="4a93c-134">Styling a ScrollViewer</span></span>  

 <span data-ttu-id="4a93c-135">与 Windows Presentation Foundation 中的所有控件一样， <xref:System.Windows.Controls.ScrollViewer> 可以设置样式以便更改控件的默认呈现行为。</span><span class="sxs-lookup"><span data-stu-id="4a93c-135">Like all controls in Windows Presentation Foundation, the <xref:System.Windows.Controls.ScrollViewer> can be styled in order to change the default rendering behavior of the control.</span></span> <span data-ttu-id="4a93c-136">有关控件样式设置的其他信息，请参阅[样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)。</span><span class="sxs-lookup"><span data-stu-id="4a93c-136">For additional information on control styling, see [Styling and Templating](/dotnet/desktop-wpf/fundamentals/styles-templates-overview).</span></span>  
  
<a name="scrollviewer_scroll_vs_paginate"></a>

## <a name="paginating-documents"></a><span data-ttu-id="4a93c-137">对文档进行分页</span><span class="sxs-lookup"><span data-stu-id="4a93c-137">Paginating Documents</span></span>  

 <span data-ttu-id="4a93c-138">对于文档内容，一种替代滚动的方法是选择支持分页的文档容器。</span><span class="sxs-lookup"><span data-stu-id="4a93c-138">For document content, an alternative to scrolling is to choose a document container that supports pagination.</span></span> <span data-ttu-id="4a93c-139"><xref:System.Windows.Documents.FlowDocument> 适用于设计为承载于查看控件中的文档，如 <xref:System.Windows.Controls.FlowDocumentPageViewer> 支持跨多个页面对内容进行分页的文档，从而不需要进行滚动。</span><span class="sxs-lookup"><span data-stu-id="4a93c-139"><xref:System.Windows.Documents.FlowDocument> is for documents that are designed to be hosted within a viewing control, such as <xref:System.Windows.Controls.FlowDocumentPageViewer>, that supports paginating content across multiple pages, preventing the need for scrolling.</span></span> <span data-ttu-id="4a93c-140"><xref:System.Windows.Controls.DocumentViewer> 提供用于查看内容的解决方案 <xref:System.Windows.Documents.FixedDocument> ，该解决方案使用传统滚动显示显示区域外的内容。</span><span class="sxs-lookup"><span data-stu-id="4a93c-140"><xref:System.Windows.Controls.DocumentViewer> provides a solution for viewing <xref:System.Windows.Documents.FixedDocument> content, which uses traditional scrolling to display content outside the realm of the display area.</span></span>  
  
 <span data-ttu-id="4a93c-141">有关文档格式和演示选项的其他信息，请参阅 [WPF 中的文档](../advanced/documents-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="4a93c-141">For additional information about document formats and presentation options, see [Documents in WPF](../advanced/documents-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a93c-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a93c-142">See also</span></span>

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- <span data-ttu-id="4a93c-143">[如何：创建滚动查看器](/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="4a93c-143">[How to: Create a Scroll Viewer](/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))</span></span>
- [<span data-ttu-id="4a93c-144">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="4a93c-144">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)
- [<span data-ttu-id="4a93c-145">ScrollBar 样式和模板</span><span class="sxs-lookup"><span data-stu-id="4a93c-145">ScrollBar Styles and Templates</span></span>](scrollbar-styles-and-templates.md)
- [<span data-ttu-id="4a93c-146">控件</span><span class="sxs-lookup"><span data-stu-id="4a93c-146">Controls</span></span>](../advanced/optimizing-performance-controls.md)
