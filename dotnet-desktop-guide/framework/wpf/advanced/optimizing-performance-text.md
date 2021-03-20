---
title: 优化性能：文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rendering text [WPF]
- hyperlinks [WPF]
- formatted text [WPF]
- text [WPF], performance
- glyphs [WPF]
ms.assetid: 66b1b9a7-8618-48db-b616-c57ea4327b98
ms.openlocfilehash: d0d8a0f83473deed54c36bcfb9827710e6c02fea
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665297"
---
# <a name="optimizing-performance-text"></a><span data-ttu-id="b51e3-102">优化性能：文本</span><span class="sxs-lookup"><span data-stu-id="b51e3-102">Optimizing Performance: Text</span></span>

[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="b51e3-103">支持通过使用功能丰富的 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 控件实现的文本内容演示。</span><span class="sxs-lookup"><span data-stu-id="b51e3-103">includes support for the presentation of text content through the use of feature-rich [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] controls.</span></span> <span data-ttu-id="b51e3-104">通常可以将文本呈现分为三层：</span><span class="sxs-lookup"><span data-stu-id="b51e3-104">In general you can divide text rendering in three layers:</span></span>

1. <span data-ttu-id="b51e3-105">直接使用 <xref:System.Windows.Documents.Glyphs> 和 <xref:System.Windows.Media.GlyphRun> 对象。</span><span class="sxs-lookup"><span data-stu-id="b51e3-105">Using the <xref:System.Windows.Documents.Glyphs> and <xref:System.Windows.Media.GlyphRun> objects directly.</span></span>

2. <span data-ttu-id="b51e3-106">使用 <xref:System.Windows.Media.FormattedText> 对象。</span><span class="sxs-lookup"><span data-stu-id="b51e3-106">Using the <xref:System.Windows.Media.FormattedText> object.</span></span>

3. <span data-ttu-id="b51e3-107">使用高级控件，如 <xref:System.Windows.Controls.TextBlock> 和 <xref:System.Windows.Documents.FlowDocument> 对象。</span><span class="sxs-lookup"><span data-stu-id="b51e3-107">Using high-level controls, such as the <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span>

<span data-ttu-id="b51e3-108">本主题提供文本呈现性能方面的建议。</span><span class="sxs-lookup"><span data-stu-id="b51e3-108">This topic provides text rendering performance recommendations.</span></span>

<a name="Glyph_Level"></a>

## <a name="rendering-text-at-the-glyph-level"></a><span data-ttu-id="b51e3-109">字形级别的呈现文本</span><span class="sxs-lookup"><span data-stu-id="b51e3-109">Rendering Text at the Glyph Level</span></span>

[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="b51e3-110">提供高级文本支持，包括可直接访问的标志符号级别标记， <xref:System.Windows.Documents.Glyphs> 以及在设置格式后要截获和保存文本的客户。</span><span class="sxs-lookup"><span data-stu-id="b51e3-110">provides advanced text support including glyph-level markup with direct access to <xref:System.Windows.Documents.Glyphs> for customers who want to intercept and persist text after formatting.</span></span> <span data-ttu-id="b51e3-111">这些功能为以下每种方案中不同的文本呈现要求提供关键支持。</span><span class="sxs-lookup"><span data-stu-id="b51e3-111">These features provide critical support for the different text rendering requirements in each of the following scenarios.</span></span>

- <span data-ttu-id="b51e3-112">固定格式文档的屏幕显示。</span><span class="sxs-lookup"><span data-stu-id="b51e3-112">Screen display of fixed-format documents.</span></span>

- <span data-ttu-id="b51e3-113">打印方案。</span><span class="sxs-lookup"><span data-stu-id="b51e3-113">Print scenarios.</span></span>

  - [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] <span data-ttu-id="b51e3-114">作为设备打印机语言。</span><span class="sxs-lookup"><span data-stu-id="b51e3-114">as a device printer language.</span></span>

  - <span data-ttu-id="b51e3-115">Microsoft XPS 文档编写器。</span><span class="sxs-lookup"><span data-stu-id="b51e3-115">Microsoft XPS Document Writer.</span></span>

  - <span data-ttu-id="b51e3-116">以前的打印机驱动程序，从 Win32 应用程序输出为固定格式。</span><span class="sxs-lookup"><span data-stu-id="b51e3-116">Previous printer drivers, output from Win32 applications to the fixed format.</span></span>

  - <span data-ttu-id="b51e3-117">打印后台处理格式。</span><span class="sxs-lookup"><span data-stu-id="b51e3-117">Print spool format.</span></span>

- <span data-ttu-id="b51e3-118">固定格式的文档表示形式，包括以前版本的 Windows 和其他计算设备的客户端。</span><span class="sxs-lookup"><span data-stu-id="b51e3-118">Fixed-format document representation, including clients for previous versions of Windows and other computing devices.</span></span>

> [!NOTE]
> <span data-ttu-id="b51e3-119"><xref:System.Windows.Documents.Glyphs> 和 <xref:System.Windows.Media.GlyphRun> 专为固定格式的文档演示和打印方案而设计。</span><span class="sxs-lookup"><span data-stu-id="b51e3-119"><xref:System.Windows.Documents.Glyphs> and <xref:System.Windows.Media.GlyphRun> are designed for fixed-format document presentation and print scenarios.</span></span> [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="b51e3-120">为一般布局和 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 方案（例如和）提供了多个元素 <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.TextBlock> 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-120">provides several elements for general layout and [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] scenarios such as <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="b51e3-121">有关布局和 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 方案的详细信息，请参阅 [WPF 中的版式](typography-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="b51e3-121">For more information on layout and [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] scenarios, see the [Typography in WPF](typography-in-wpf.md).</span></span>

<span data-ttu-id="b51e3-122">下面的示例演示如何 <xref:System.Windows.Documents.Glyphs> 在中定义对象的属性 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-122">The following examples show how to define properties for a <xref:System.Windows.Documents.Glyphs> object in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="b51e3-123"><xref:System.Windows.Documents.Glyphs>对象表示中的的输出 <xref:System.Windows.Media.GlyphRun> [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-123">The <xref:System.Windows.Documents.Glyphs> object represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="b51e3-124">示例假定本地计算机上的 **C:\WINDOWS\Fonts** 文件夹中安装了 Arial、Courier New 和 Times New Roman 字体。</span><span class="sxs-lookup"><span data-stu-id="b51e3-124">The examples assume that the Arial, Courier New, and Times New Roman fonts are installed in the **C:\WINDOWS\Fonts** folder on the local computer.</span></span>

[!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]

### <a name="using-drawglyphrun"></a><span data-ttu-id="b51e3-125">使用 DrawGlyphRun</span><span class="sxs-lookup"><span data-stu-id="b51e3-125">Using DrawGlyphRun</span></span>

<span data-ttu-id="b51e3-126">如果你具有自定义控件并且要呈现标志符号，请使用 <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="b51e3-126">If you have custom control and you want to render glyphs, use the <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A> method.</span></span>

[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="b51e3-127">还通过使用对象提供较低级别的自定义文本格式的服务 <xref:System.Windows.Media.FormattedText> 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-127">also provides lower-level services for custom text formatting through the use of the <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="b51e3-128">在中呈现文本最有效的方法 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 是使用和在字形级别生成文本内容 <xref:System.Windows.Documents.Glyphs> <xref:System.Windows.Media.GlyphRun> 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-128">The most efficient way of rendering text in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] is by generating text content at the glyph level using <xref:System.Windows.Documents.Glyphs> and <xref:System.Windows.Media.GlyphRun>.</span></span> <span data-ttu-id="b51e3-129">但是，这种效率的代价是，难以使用丰富的文本格式，这是控件的内置功能 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] ，例如 <xref:System.Windows.Controls.TextBlock> 和 <xref:System.Windows.Documents.FlowDocument> 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-129">However, the cost of this efficiency is the loss of easy to use rich text formatting, which are built-in features of [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] controls, such as <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument>.</span></span>

<a name="FormattedText_Object"></a>

## <a name="formattedtext-object"></a><span data-ttu-id="b51e3-130">FormattedText 对象</span><span class="sxs-lookup"><span data-stu-id="b51e3-130">FormattedText Object</span></span>

<span data-ttu-id="b51e3-131"><xref:System.Windows.Media.FormattedText>对象允许您绘制多行文本，在这种情况下，文本中的每个字符都可以单独设置格式。</span><span class="sxs-lookup"><span data-stu-id="b51e3-131">The <xref:System.Windows.Media.FormattedText> object allows you to draw multi-line text, in which each character in the text can be individually formatted.</span></span> <span data-ttu-id="b51e3-132">有关详细信息，请参阅[绘制格式化文本](drawing-formatted-text.md)。</span><span class="sxs-lookup"><span data-stu-id="b51e3-132">For more information, see [Drawing Formatted Text](drawing-formatted-text.md).</span></span>

<span data-ttu-id="b51e3-133">若要创建格式化文本，请调用 <xref:System.Windows.Media.FormattedText.%23ctor%2A> 构造函数来创建 <xref:System.Windows.Media.FormattedText> 对象。</span><span class="sxs-lookup"><span data-stu-id="b51e3-133">To create formatted text, call the <xref:System.Windows.Media.FormattedText.%23ctor%2A> constructor to create a <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="b51e3-134">创建初始格式化文本字符串后，便可应用某一范围的格式样式。</span><span class="sxs-lookup"><span data-stu-id="b51e3-134">Once you have created the initial formatted text string, you can apply a range of formatting styles.</span></span> <span data-ttu-id="b51e3-135">如果你的应用程序想要实现自己的布局，则该 <xref:System.Windows.Media.FormattedText> 对象比使用控件（如）更好 <xref:System.Windows.Controls.TextBlock> 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-135">If your application wants to implement its own layout, then the <xref:System.Windows.Media.FormattedText> object is better choice than using a control, such as <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="b51e3-136">有关对象的详细信息 <xref:System.Windows.Media.FormattedText> ，请参阅 [绘制格式化文本](drawing-formatted-text.md) 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-136">For more information on the <xref:System.Windows.Media.FormattedText> object, see [Drawing Formatted Text](drawing-formatted-text.md) .</span></span>

<span data-ttu-id="b51e3-137"><xref:System.Windows.Media.FormattedText>对象提供低级别文本格式设置功能。</span><span class="sxs-lookup"><span data-stu-id="b51e3-137">The <xref:System.Windows.Media.FormattedText> object provides low-level text formatting capability.</span></span> <span data-ttu-id="b51e3-138">可向一个或多个字符应用多种格式样式。</span><span class="sxs-lookup"><span data-stu-id="b51e3-138">You can apply multiple formatting styles to one or more characters.</span></span> <span data-ttu-id="b51e3-139">例如，可以调用 <xref:System.Windows.Media.FormattedText.SetFontSize%2A> 和 <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> 方法来更改文本中前五个字符的格式设置。</span><span class="sxs-lookup"><span data-stu-id="b51e3-139">For example, you could call both the <xref:System.Windows.Media.FormattedText.SetFontSize%2A> and <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> methods to change the formatting of the first five characters in the text.</span></span>

<span data-ttu-id="b51e3-140">下面的代码示例将创建一个 <xref:System.Windows.Media.FormattedText> 对象并将其呈现。</span><span class="sxs-lookup"><span data-stu-id="b51e3-140">The following code example creates a <xref:System.Windows.Media.FormattedText> object and renders it.</span></span>

[!code-csharp[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
[!code-vb[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]

<a name="FlowDocument_TextBlock_Label"></a>

## <a name="flowdocument-textblock-and-label-controls"></a><span data-ttu-id="b51e3-141">FlowDocument、TextBlock 和 Label 控件</span><span class="sxs-lookup"><span data-stu-id="b51e3-141">FlowDocument, TextBlock, and Label Controls</span></span>

[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="b51e3-142">包括多个用于在屏幕中绘制文本的控件。</span><span class="sxs-lookup"><span data-stu-id="b51e3-142">includes multiple controls for drawing text to the screen.</span></span> <span data-ttu-id="b51e3-143">每个控件都面向不同的方案，并具有自己的功能和限制列表。</span><span class="sxs-lookup"><span data-stu-id="b51e3-143">Each control is targeted to a different scenario and has its own list of features and limitations.</span></span>

### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a><span data-ttu-id="b51e3-144">FlowDocument 对性能的影响比 TextBlock 或 Label 大</span><span class="sxs-lookup"><span data-stu-id="b51e3-144">FlowDocument Impacts Performance More than TextBlock or Label</span></span>

<span data-ttu-id="b51e3-145">通常， <xref:System.Windows.Controls.TextBlock> 当要求提供有限文本支持时，应使用元素，例如中的 brief 句子 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-145">In general, the <xref:System.Windows.Controls.TextBlock> element should be used when limited text support is required, such as a brief sentence in a [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)].</span></span> <span data-ttu-id="b51e3-146"><xref:System.Windows.Controls.Label> 需要最少文本支持时，可以使用。</span><span class="sxs-lookup"><span data-stu-id="b51e3-146"><xref:System.Windows.Controls.Label> can be used when minimal text support is required.</span></span> <span data-ttu-id="b51e3-147"><xref:System.Windows.Documents.FlowDocument>元素是一个容器，用于 flowable 支持丰富的内容表示形式的文档，因此，对性能的影响比使用或控件更大 <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.Label> 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-147">The <xref:System.Windows.Documents.FlowDocument> element is a container for re-flowable documents that support rich presentation of content, and therefore, has a greater performance impact than using the <xref:System.Windows.Controls.TextBlock> or <xref:System.Windows.Controls.Label> controls.</span></span>

<span data-ttu-id="b51e3-148">有关的详细信息 <xref:System.Windows.Documents.FlowDocument> ，请参阅 [流文档概述](flow-document-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b51e3-148">For more information on <xref:System.Windows.Documents.FlowDocument>, see [Flow Document Overview](flow-document-overview.md).</span></span>

### <a name="avoid-using-textblock-in-flowdocument"></a><span data-ttu-id="b51e3-149">避免在 FlowDocument 中使用 TextBlock</span><span class="sxs-lookup"><span data-stu-id="b51e3-149">Avoid Using TextBlock in FlowDocument</span></span>

<span data-ttu-id="b51e3-150"><xref:System.Windows.Controls.TextBlock>元素派生自 <xref:System.Windows.UIElement> 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-150">The <xref:System.Windows.Controls.TextBlock> element is derived from <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="b51e3-151"><xref:System.Windows.Documents.Run>元素派生自 <xref:System.Windows.Documents.TextElement> ，它比派生的对象使用的成本更低 <xref:System.Windows.UIElement> 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-151">The <xref:System.Windows.Documents.Run> element is derived from <xref:System.Windows.Documents.TextElement>, which is less costly to use than a <xref:System.Windows.UIElement>-derived object.</span></span> <span data-ttu-id="b51e3-152">如果可能，请使用 <xref:System.Windows.Documents.Run> 而不是 <xref:System.Windows.Controls.TextBlock> 在中显示文本内容 <xref:System.Windows.Documents.FlowDocument> 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-152">When possible, use <xref:System.Windows.Documents.Run> rather than <xref:System.Windows.Controls.TextBlock> for displaying text content in a <xref:System.Windows.Documents.FlowDocument>.</span></span>

<span data-ttu-id="b51e3-153">以下标记示例演示了在中设置文本内容的两种方式 <xref:System.Windows.Documents.FlowDocument> ：</span><span class="sxs-lookup"><span data-stu-id="b51e3-153">The following markup sample illustrates two ways of setting text content within a <xref:System.Windows.Documents.FlowDocument>:</span></span>

[!code-xaml[Performance#PerformanceSnippet13](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]

### <a name="avoid-using-run-to-set-text-properties"></a><span data-ttu-id="b51e3-154">避免使用 Run 来设置文本属性</span><span class="sxs-lookup"><span data-stu-id="b51e3-154">Avoid Using Run to Set Text Properties</span></span>

<span data-ttu-id="b51e3-155">通常，在中使用 <xref:System.Windows.Documents.Run> 比根本 <xref:System.Windows.Controls.TextBlock> 不使用显式对象更高的性能 <xref:System.Windows.Documents.Run> 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-155">In general, using a <xref:System.Windows.Documents.Run> within a <xref:System.Windows.Controls.TextBlock> is more performance intensive than not using an explicit <xref:System.Windows.Documents.Run> object at all.</span></span> <span data-ttu-id="b51e3-156">如果你使用 <xref:System.Windows.Documents.Run> 来设置文本属性，请直接在上设置这些属性 <xref:System.Windows.Controls.TextBlock> 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-156">If you are using a <xref:System.Windows.Documents.Run> in order to set text properties, set those properties directly on the <xref:System.Windows.Controls.TextBlock> instead.</span></span>

<span data-ttu-id="b51e3-157">以下标记示例演示了这两种设置文本属性的方法（在本例中为 <xref:System.Windows.Controls.TextBlock.FontWeight%2A> 属性）：</span><span class="sxs-lookup"><span data-stu-id="b51e3-157">The following markup sample illustrates these two ways of setting a text property, in this case, the <xref:System.Windows.Controls.TextBlock.FontWeight%2A> property:</span></span>

[!code-xaml[Performance#PerformanceSnippet12](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]

<span data-ttu-id="b51e3-158">下表显示了 <xref:System.Windows.Controls.TextBlock> 使用和不使用显式显示1000对象的费用 <xref:System.Windows.Documents.Run> 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-158">The following table shows the cost of displaying 1000 <xref:System.Windows.Controls.TextBlock> objects with and without an explicit <xref:System.Windows.Documents.Run>.</span></span>

|<span data-ttu-id="b51e3-159">**TextBlock 类型**</span><span class="sxs-lookup"><span data-stu-id="b51e3-159">**TextBlock type**</span></span>|<span data-ttu-id="b51e3-160">**创建时间 (ms)**</span><span class="sxs-lookup"><span data-stu-id="b51e3-160">**Creation time (ms)**</span></span>|<span data-ttu-id="b51e3-161">**呈现时间 (ms)**</span><span class="sxs-lookup"><span data-stu-id="b51e3-161">**Render time (ms)**</span></span>|
|------------------------|------------------------------|----------------------------|
|<span data-ttu-id="b51e3-162">运行设置文本属性</span><span class="sxs-lookup"><span data-stu-id="b51e3-162">Run setting text properties</span></span>|<span data-ttu-id="b51e3-163">146</span><span class="sxs-lookup"><span data-stu-id="b51e3-163">146</span></span>|<span data-ttu-id="b51e3-164">540</span><span class="sxs-lookup"><span data-stu-id="b51e3-164">540</span></span>|
|<span data-ttu-id="b51e3-165">TextBlock 设置文本属性</span><span class="sxs-lookup"><span data-stu-id="b51e3-165">TextBlock setting text properties</span></span>|<span data-ttu-id="b51e3-166">43</span><span class="sxs-lookup"><span data-stu-id="b51e3-166">43</span></span>|<span data-ttu-id="b51e3-167">453</span><span class="sxs-lookup"><span data-stu-id="b51e3-167">453</span></span>|

### <a name="avoid-databinding-to-the-labelcontent-property"></a><span data-ttu-id="b51e3-168">避免对 Label.Content 属性进行数据绑定</span><span class="sxs-lookup"><span data-stu-id="b51e3-168">Avoid Databinding to the Label.Content Property</span></span>

<span data-ttu-id="b51e3-169">假设有这样一种情况：您有一个 <xref:System.Windows.Controls.Label> 从源中频繁更新的对象 <xref:System.String> 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-169">Imagine a scenario where you have a <xref:System.Windows.Controls.Label> object that is updated frequently from a <xref:System.String> source.</span></span> <span data-ttu-id="b51e3-170">数据将 <xref:System.Windows.Controls.Label> 元素的属性绑定 <xref:System.Windows.Controls.ContentControl.Content%2A> 到 <xref:System.String> 源对象时，可能会遇到性能不佳的情况。</span><span class="sxs-lookup"><span data-stu-id="b51e3-170">When data binding the <xref:System.Windows.Controls.Label> element's <xref:System.Windows.Controls.ContentControl.Content%2A> property to the <xref:System.String> source object, you may experience poor performance.</span></span> <span data-ttu-id="b51e3-171">每次更新源时 <xref:System.String> ，将放弃旧 <xref:System.String> 对象并重新创建新的对象 <xref:System.String> <xref:System.String> ，因为对象是不可变的，因此不能修改。</span><span class="sxs-lookup"><span data-stu-id="b51e3-171">Each time the source <xref:System.String> is updated, the old <xref:System.String> object is discarded and a new <xref:System.String> is recreated—because a <xref:System.String> object is immutable, it cannot be modified.</span></span> <span data-ttu-id="b51e3-172">这进而使 <xref:System.Windows.Controls.ContentPresenter> <xref:System.Windows.Controls.Label> 对象的旧内容放弃，并重新生成新内容以显示新的 <xref:System.String> 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-172">This, in turn, causes the <xref:System.Windows.Controls.ContentPresenter> of the <xref:System.Windows.Controls.Label> object to discard its old content and regenerate the new content to display the new <xref:System.String>.</span></span>

<span data-ttu-id="b51e3-173">此问题的解决方法很简单。</span><span class="sxs-lookup"><span data-stu-id="b51e3-173">The solution to this problem is simple.</span></span> <span data-ttu-id="b51e3-174">如果 <xref:System.Windows.Controls.Label> 未设置为自定义值，则将替换为， <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 并将 <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.TextBlock> 其属性绑定 <xref:System.Windows.Controls.TextBlock.Text%2A> 到源字符串。</span><span class="sxs-lookup"><span data-stu-id="b51e3-174">If the <xref:System.Windows.Controls.Label> is not set to a custom <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> value, replace the <xref:System.Windows.Controls.Label> with a <xref:System.Windows.Controls.TextBlock> and data bind its <xref:System.Windows.Controls.TextBlock.Text%2A> property to the source string.</span></span>

|<span data-ttu-id="b51e3-175">**数据绑定属性**</span><span class="sxs-lookup"><span data-stu-id="b51e3-175">**Data bound property**</span></span>|<span data-ttu-id="b51e3-176">**更新时间 (ms)**</span><span class="sxs-lookup"><span data-stu-id="b51e3-176">**Update time (ms)**</span></span>|
|-----------------------------|----------------------------|
|<span data-ttu-id="b51e3-177">Label.Content</span><span class="sxs-lookup"><span data-stu-id="b51e3-177">Label.Content</span></span>|<span data-ttu-id="b51e3-178">835</span><span class="sxs-lookup"><span data-stu-id="b51e3-178">835</span></span>|
|<span data-ttu-id="b51e3-179">TextBlock.Text</span><span class="sxs-lookup"><span data-stu-id="b51e3-179">TextBlock.Text</span></span>|<span data-ttu-id="b51e3-180">242</span><span class="sxs-lookup"><span data-stu-id="b51e3-180">242</span></span>|

<a name="Hyperlink"></a>

## <a name="hyperlink"></a><span data-ttu-id="b51e3-181">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="b51e3-181">Hyperlink</span></span>

<span data-ttu-id="b51e3-182"><xref:System.Windows.Documents.Hyperlink>对象是一个内联级别的流内容元素，它允许您在流内容中承载超链接。</span><span class="sxs-lookup"><span data-stu-id="b51e3-182">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span>

### <a name="combine-hyperlinks-in-one-textblock-object"></a><span data-ttu-id="b51e3-183">在一个 TextBlock 对象中合并超链接</span><span class="sxs-lookup"><span data-stu-id="b51e3-183">Combine Hyperlinks in One TextBlock Object</span></span>

<span data-ttu-id="b51e3-184">您可以通过将多个 <xref:System.Windows.Documents.Hyperlink> 元素组合在一起，在同一内对它们进行优化 <xref:System.Windows.Controls.TextBlock> 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-184">You can optimize the use of multiple <xref:System.Windows.Documents.Hyperlink> elements by grouping them together within the same <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="b51e3-185">这有助于最小化在应用程序中创建的对象的数量。</span><span class="sxs-lookup"><span data-stu-id="b51e3-185">This helps to minimize the number of objects you create in your application.</span></span> <span data-ttu-id="b51e3-186">例如，可显示多个超链接，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b51e3-186">For example, you may want to display multiple hyperlinks, such as the following:</span></span>

<span data-ttu-id="b51e3-187">MSN 主页 &#124; 我的 MSN</span><span class="sxs-lookup"><span data-stu-id="b51e3-187">MSN Home &#124; My MSN</span></span>

<span data-ttu-id="b51e3-188">以下标记示例演示了 <xref:System.Windows.Controls.TextBlock> 用于显示超链接的多个元素：</span><span class="sxs-lookup"><span data-stu-id="b51e3-188">The following markup example shows multiple <xref:System.Windows.Controls.TextBlock> elements used to display the hyperlinks:</span></span>

[!code-xaml[Performance#PerformanceSnippet9](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]

<span data-ttu-id="b51e3-189">以下标记示例演示了一种更有效的显示超链接的方法，这次使用单个 <xref:System.Windows.Controls.TextBlock> ：</span><span class="sxs-lookup"><span data-stu-id="b51e3-189">The following markup example shows a more efficient way of displaying the hyperlinks, this time, using a single <xref:System.Windows.Controls.TextBlock>:</span></span>

[!code-xaml[Performance#PerformanceSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]

### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a><span data-ttu-id="b51e3-190">仅在 MouseEnter 事件的超链接中显示下划线</span><span class="sxs-lookup"><span data-stu-id="b51e3-190">Showing Underlines on Hyperlinks Only on MouseEnter Events</span></span>

<span data-ttu-id="b51e3-191"><xref:System.Windows.TextDecoration>对象是可添加到文本的视觉对象，但它可能会对实例化的性能有很大的装饰。</span><span class="sxs-lookup"><span data-stu-id="b51e3-191">A <xref:System.Windows.TextDecoration> object is a visual ornamentation that you can add to text; however, it can be performance intensive to instantiate.</span></span> <span data-ttu-id="b51e3-192">如果对元素进行大量使用 <xref:System.Windows.Documents.Hyperlink> ，请考虑仅在触发事件（例如事件）时显示下划线 <xref:System.Windows.ContentElement.MouseEnter> 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-192">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span> <span data-ttu-id="b51e3-193">有关详细信息，请参阅[指定是否为超链接添加下划线](how-to-specify-whether-a-hyperlink-is-underlined.md)。</span><span class="sxs-lookup"><span data-stu-id="b51e3-193">For more information, see [Specify Whether a Hyperlink is Underlined](how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>

<span data-ttu-id="b51e3-194">下图显示了 MouseEnter 事件如何触发带下划线的超链接：</span><span class="sxs-lookup"><span data-stu-id="b51e3-194">The following image shows how the MouseEnter event triggers the underlined hyperlink:</span></span>

![显示 TextDecoration 的超链接](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)

<span data-ttu-id="b51e3-196">以下标记示例显示了 <xref:System.Windows.Documents.Hyperlink> 使用和不带下划线定义的：</span><span class="sxs-lookup"><span data-stu-id="b51e3-196">The following markup sample shows a <xref:System.Windows.Documents.Hyperlink> defined with and without an underline:</span></span>

[!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]

<span data-ttu-id="b51e3-197">下表显示了 <xref:System.Windows.Documents.Hyperlink> 使用和不使用下划线显示1000元素的性能成本。</span><span class="sxs-lookup"><span data-stu-id="b51e3-197">The following table shows the performance cost of displaying 1000 <xref:System.Windows.Documents.Hyperlink> elements with and without an underline.</span></span>

|<span data-ttu-id="b51e3-198">**超链接**</span><span class="sxs-lookup"><span data-stu-id="b51e3-198">**Hyperlink**</span></span>|<span data-ttu-id="b51e3-199">**创建时间 (ms)**</span><span class="sxs-lookup"><span data-stu-id="b51e3-199">**Creation time (ms)**</span></span>|<span data-ttu-id="b51e3-200">**呈现时间 (ms)**</span><span class="sxs-lookup"><span data-stu-id="b51e3-200">**Render time (ms)**</span></span>|
|-------------------|------------------------------|----------------------------|
|<span data-ttu-id="b51e3-201">使用下划线</span><span class="sxs-lookup"><span data-stu-id="b51e3-201">With underline</span></span>|<span data-ttu-id="b51e3-202">289</span><span class="sxs-lookup"><span data-stu-id="b51e3-202">289</span></span>|<span data-ttu-id="b51e3-203">1130</span><span class="sxs-lookup"><span data-stu-id="b51e3-203">1130</span></span>|
|<span data-ttu-id="b51e3-204">不使用下划线</span><span class="sxs-lookup"><span data-stu-id="b51e3-204">Without underline</span></span>|<span data-ttu-id="b51e3-205">299</span><span class="sxs-lookup"><span data-stu-id="b51e3-205">299</span></span>|<span data-ttu-id="b51e3-206">776</span><span class="sxs-lookup"><span data-stu-id="b51e3-206">776</span></span>|

<a name="Text_Formatting_Features"></a>

## <a name="text-formatting-features"></a><span data-ttu-id="b51e3-207">文本格式设置功能</span><span class="sxs-lookup"><span data-stu-id="b51e3-207">Text Formatting Features</span></span>

[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="b51e3-208">提供丰富的文本格式设置服务，如自动断字。</span><span class="sxs-lookup"><span data-stu-id="b51e3-208">provides rich text formatting services, such as automatic hyphenations.</span></span> <span data-ttu-id="b51e3-209">这些服务可能会影响应用程序性能，应仅在需要时使用。</span><span class="sxs-lookup"><span data-stu-id="b51e3-209">These services may impact application performance and should only be used when needed.</span></span>

### <a name="avoid-unnecessary-use-of-hyphenation"></a><span data-ttu-id="b51e3-210">避免不必要地使用断字</span><span class="sxs-lookup"><span data-stu-id="b51e3-210">Avoid Unnecessary Use of Hyphenation</span></span>

<span data-ttu-id="b51e3-211">自动断字功能可查找文本行的连字符断点，并允许和对象中的行具有额外的断点位置 <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Documents.FlowDocument> 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-211">Automatic hyphenation finds hyphen breakpoints for lines of text, and allows additional break positions for lines in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="b51e3-212">默认禁用这些对象中的自动断字功能。</span><span class="sxs-lookup"><span data-stu-id="b51e3-212">By default, the automatic hyphenation feature is disabled in these objects.</span></span> <span data-ttu-id="b51e3-213">通过将该对象的 IsHyphenationEnabled 属性设置为 `true`，可以启用此功能。</span><span class="sxs-lookup"><span data-stu-id="b51e3-213">You can enable this feature by setting the object's IsHyphenationEnabled property to `true`.</span></span> <span data-ttu-id="b51e3-214">但是，启用此功能会导致 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 启动组件对象模型 (COM) 互操作性，这可能会影响应用程序性能。</span><span class="sxs-lookup"><span data-stu-id="b51e3-214">However, enabling this feature causes [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] to initiate Component Object Model (COM) interoperability, which can impact application performance.</span></span> <span data-ttu-id="b51e3-215">除非需要，否则不建议使用自动断字功能。</span><span class="sxs-lookup"><span data-stu-id="b51e3-215">It is recommended that you do not use automatic hyphenation unless you need it.</span></span>

### <a name="use-figures-carefully"></a><span data-ttu-id="b51e3-216">谨慎使用图形</span><span class="sxs-lookup"><span data-stu-id="b51e3-216">Use Figures Carefully</span></span>

<span data-ttu-id="b51e3-217"><xref:System.Windows.Documents.Figure>元素表示可以在内容页中完全定位的流内容部分。</span><span class="sxs-lookup"><span data-stu-id="b51e3-217">A <xref:System.Windows.Documents.Figure> element represents a portion of flow content that can be absolutely-positioned within a page of content.</span></span> <span data-ttu-id="b51e3-218">在某些情况下， <xref:System.Windows.Documents.Figure> 可能会导致整个页面在其位置与已布局的内容冲突时自动重新设置格式。可以最大程度地减少不必要的重新格式化的可能性，只需分组 <xref:System.Windows.Documents.Figure> 元素，或在固定页面大小的情况下将其声明到内容顶部附近。</span><span class="sxs-lookup"><span data-stu-id="b51e3-218">In some cases, a <xref:System.Windows.Documents.Figure> may cause an entire page to automatically reformat if its position collides with content that has already been laid-out. You can minimize the possibility of unnecessary reformatting by either grouping <xref:System.Windows.Documents.Figure> elements next to each other, or declaring them near the top of content in a fixed page size scenario.</span></span>

### <a name="optimal-paragraph"></a><span data-ttu-id="b51e3-219">最佳段落</span><span class="sxs-lookup"><span data-stu-id="b51e3-219">Optimal Paragraph</span></span>

<span data-ttu-id="b51e3-220">对象的最佳段落功能 <xref:System.Windows.Documents.FlowDocument> 会将段落布局，以便尽可能均匀地分布空白。</span><span class="sxs-lookup"><span data-stu-id="b51e3-220">The optimal paragraph feature of the <xref:System.Windows.Documents.FlowDocument> object lays out paragraphs so that white space is distributed as evenly as possible.</span></span> <span data-ttu-id="b51e3-221">默认禁用最佳段落功能。</span><span class="sxs-lookup"><span data-stu-id="b51e3-221">By default, the optimal paragraph feature is disabled.</span></span> <span data-ttu-id="b51e3-222">可以通过将对象的 <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> 属性设置为来启用此功能 `true` 。</span><span class="sxs-lookup"><span data-stu-id="b51e3-222">You can enable this feature by setting the object's <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> property to `true`.</span></span> <span data-ttu-id="b51e3-223">但是，启用此功能会影响应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="b51e3-223">However, enabling this feature impacts application performance.</span></span> <span data-ttu-id="b51e3-224">除非需要，否则不建议使用最佳段落功能。</span><span class="sxs-lookup"><span data-stu-id="b51e3-224">It is recommended that you do not use the optimal paragraph feature unless you need it.</span></span>

## <a name="see-also"></a><span data-ttu-id="b51e3-225">请参阅</span><span class="sxs-lookup"><span data-stu-id="b51e3-225">See also</span></span>

- [<span data-ttu-id="b51e3-226">优化 WPF 应用程序性能</span><span class="sxs-lookup"><span data-stu-id="b51e3-226">Optimizing WPF Application Performance</span></span>](optimizing-wpf-application-performance.md)
- [<span data-ttu-id="b51e3-227">规划应用程序性能</span><span class="sxs-lookup"><span data-stu-id="b51e3-227">Planning for Application Performance</span></span>](planning-for-application-performance.md)
- [<span data-ttu-id="b51e3-228">利用硬件</span><span class="sxs-lookup"><span data-stu-id="b51e3-228">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)
- [<span data-ttu-id="b51e3-229">布局和示例</span><span class="sxs-lookup"><span data-stu-id="b51e3-229">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)
- [<span data-ttu-id="b51e3-230">二维图形和图像处理</span><span class="sxs-lookup"><span data-stu-id="b51e3-230">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="b51e3-231">对象行为</span><span class="sxs-lookup"><span data-stu-id="b51e3-231">Object Behavior</span></span>](optimizing-performance-object-behavior.md)
- [<span data-ttu-id="b51e3-232">应用程序资源</span><span class="sxs-lookup"><span data-stu-id="b51e3-232">Application Resources</span></span>](optimizing-performance-application-resources.md)
- [<span data-ttu-id="b51e3-233">数据绑定</span><span class="sxs-lookup"><span data-stu-id="b51e3-233">Data Binding</span></span>](optimizing-performance-data-binding.md)
- [<span data-ttu-id="b51e3-234">其他性能建议</span><span class="sxs-lookup"><span data-stu-id="b51e3-234">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)
