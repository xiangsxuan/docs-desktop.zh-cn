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
# <a name="optimizing-performance-text"></a>优化性能：文本

[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 支持通过使用功能丰富的 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 控件实现的文本内容演示。 通常可以将文本呈现分为三层：

1. 直接使用 <xref:System.Windows.Documents.Glyphs> 和 <xref:System.Windows.Media.GlyphRun> 对象。

2. 使用 <xref:System.Windows.Media.FormattedText> 对象。

3. 使用高级控件，如 <xref:System.Windows.Controls.TextBlock> 和 <xref:System.Windows.Documents.FlowDocument> 对象。

本主题提供文本呈现性能方面的建议。

<a name="Glyph_Level"></a>

## <a name="rendering-text-at-the-glyph-level"></a>字形级别的呈现文本

[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 提供高级文本支持，包括可直接访问的标志符号级别标记， <xref:System.Windows.Documents.Glyphs> 以及在设置格式后要截获和保存文本的客户。 这些功能为以下每种方案中不同的文本呈现要求提供关键支持。

- 固定格式文档的屏幕显示。

- 打印方案。

  - [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 作为设备打印机语言。

  - Microsoft XPS 文档编写器。

  - 以前的打印机驱动程序，从 Win32 应用程序输出为固定格式。

  - 打印后台处理格式。

- 固定格式的文档表示形式，包括以前版本的 Windows 和其他计算设备的客户端。

> [!NOTE]
> <xref:System.Windows.Documents.Glyphs> 和 <xref:System.Windows.Media.GlyphRun> 专为固定格式的文档演示和打印方案而设计。 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 为一般布局和 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 方案（例如和）提供了多个元素 <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.TextBlock> 。 有关布局和 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 方案的详细信息，请参阅 [WPF 中的版式](typography-in-wpf.md)。

下面的示例演示如何 <xref:System.Windows.Documents.Glyphs> 在中定义对象的属性 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。 <xref:System.Windows.Documents.Glyphs>对象表示中的的输出 <xref:System.Windows.Media.GlyphRun> [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。 示例假定本地计算机上的 **C:\WINDOWS\Fonts** 文件夹中安装了 Arial、Courier New 和 Times New Roman 字体。

[!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]

### <a name="using-drawglyphrun"></a>使用 DrawGlyphRun

如果你具有自定义控件并且要呈现标志符号，请使用 <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A> 方法。

[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 还通过使用对象提供较低级别的自定义文本格式的服务 <xref:System.Windows.Media.FormattedText> 。 在中呈现文本最有效的方法 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 是使用和在字形级别生成文本内容 <xref:System.Windows.Documents.Glyphs> <xref:System.Windows.Media.GlyphRun> 。 但是，这种效率的代价是，难以使用丰富的文本格式，这是控件的内置功能 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] ，例如 <xref:System.Windows.Controls.TextBlock> 和 <xref:System.Windows.Documents.FlowDocument> 。

<a name="FormattedText_Object"></a>

## <a name="formattedtext-object"></a>FormattedText 对象

<xref:System.Windows.Media.FormattedText>对象允许您绘制多行文本，在这种情况下，文本中的每个字符都可以单独设置格式。 有关详细信息，请参阅[绘制格式化文本](drawing-formatted-text.md)。

若要创建格式化文本，请调用 <xref:System.Windows.Media.FormattedText.%23ctor%2A> 构造函数来创建 <xref:System.Windows.Media.FormattedText> 对象。 创建初始格式化文本字符串后，便可应用某一范围的格式样式。 如果你的应用程序想要实现自己的布局，则该 <xref:System.Windows.Media.FormattedText> 对象比使用控件（如）更好 <xref:System.Windows.Controls.TextBlock> 。 有关对象的详细信息 <xref:System.Windows.Media.FormattedText> ，请参阅 [绘制格式化文本](drawing-formatted-text.md) 。

<xref:System.Windows.Media.FormattedText>对象提供低级别文本格式设置功能。 可向一个或多个字符应用多种格式样式。 例如，可以调用 <xref:System.Windows.Media.FormattedText.SetFontSize%2A> 和 <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> 方法来更改文本中前五个字符的格式设置。

下面的代码示例将创建一个 <xref:System.Windows.Media.FormattedText> 对象并将其呈现。

[!code-csharp[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
[!code-vb[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]

<a name="FlowDocument_TextBlock_Label"></a>

## <a name="flowdocument-textblock-and-label-controls"></a>FlowDocument、TextBlock 和 Label 控件

[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 包括多个用于在屏幕中绘制文本的控件。 每个控件都面向不同的方案，并具有自己的功能和限制列表。

### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>FlowDocument 对性能的影响比 TextBlock 或 Label 大

通常， <xref:System.Windows.Controls.TextBlock> 当要求提供有限文本支持时，应使用元素，例如中的 brief 句子 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 。 <xref:System.Windows.Controls.Label> 需要最少文本支持时，可以使用。 <xref:System.Windows.Documents.FlowDocument>元素是一个容器，用于 flowable 支持丰富的内容表示形式的文档，因此，对性能的影响比使用或控件更大 <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.Label> 。

有关的详细信息 <xref:System.Windows.Documents.FlowDocument> ，请参阅 [流文档概述](flow-document-overview.md)。

### <a name="avoid-using-textblock-in-flowdocument"></a>避免在 FlowDocument 中使用 TextBlock

<xref:System.Windows.Controls.TextBlock>元素派生自 <xref:System.Windows.UIElement> 。 <xref:System.Windows.Documents.Run>元素派生自 <xref:System.Windows.Documents.TextElement> ，它比派生的对象使用的成本更低 <xref:System.Windows.UIElement> 。 如果可能，请使用 <xref:System.Windows.Documents.Run> 而不是 <xref:System.Windows.Controls.TextBlock> 在中显示文本内容 <xref:System.Windows.Documents.FlowDocument> 。

以下标记示例演示了在中设置文本内容的两种方式 <xref:System.Windows.Documents.FlowDocument> ：

[!code-xaml[Performance#PerformanceSnippet13](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]

### <a name="avoid-using-run-to-set-text-properties"></a>避免使用 Run 来设置文本属性

通常，在中使用 <xref:System.Windows.Documents.Run> 比根本 <xref:System.Windows.Controls.TextBlock> 不使用显式对象更高的性能 <xref:System.Windows.Documents.Run> 。 如果你使用 <xref:System.Windows.Documents.Run> 来设置文本属性，请直接在上设置这些属性 <xref:System.Windows.Controls.TextBlock> 。

以下标记示例演示了这两种设置文本属性的方法（在本例中为 <xref:System.Windows.Controls.TextBlock.FontWeight%2A> 属性）：

[!code-xaml[Performance#PerformanceSnippet12](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]

下表显示了 <xref:System.Windows.Controls.TextBlock> 使用和不使用显式显示1000对象的费用 <xref:System.Windows.Documents.Run> 。

|**TextBlock 类型**|**创建时间 (ms)**|**呈现时间 (ms)**|
|------------------------|------------------------------|----------------------------|
|运行设置文本属性|146|540|
|TextBlock 设置文本属性|43|453|

### <a name="avoid-databinding-to-the-labelcontent-property"></a>避免对 Label.Content 属性进行数据绑定

假设有这样一种情况：您有一个 <xref:System.Windows.Controls.Label> 从源中频繁更新的对象 <xref:System.String> 。 数据将 <xref:System.Windows.Controls.Label> 元素的属性绑定 <xref:System.Windows.Controls.ContentControl.Content%2A> 到 <xref:System.String> 源对象时，可能会遇到性能不佳的情况。 每次更新源时 <xref:System.String> ，将放弃旧 <xref:System.String> 对象并重新创建新的对象 <xref:System.String> <xref:System.String> ，因为对象是不可变的，因此不能修改。 这进而使 <xref:System.Windows.Controls.ContentPresenter> <xref:System.Windows.Controls.Label> 对象的旧内容放弃，并重新生成新内容以显示新的 <xref:System.String> 。

此问题的解决方法很简单。 如果 <xref:System.Windows.Controls.Label> 未设置为自定义值，则将替换为， <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 并将 <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.TextBlock> 其属性绑定 <xref:System.Windows.Controls.TextBlock.Text%2A> 到源字符串。

|**数据绑定属性**|**更新时间 (ms)**|
|-----------------------------|----------------------------|
|Label.Content|835|
|TextBlock.Text|242|

<a name="Hyperlink"></a>

## <a name="hyperlink"></a>Hyperlink

<xref:System.Windows.Documents.Hyperlink>对象是一个内联级别的流内容元素，它允许您在流内容中承载超链接。

### <a name="combine-hyperlinks-in-one-textblock-object"></a>在一个 TextBlock 对象中合并超链接

您可以通过将多个 <xref:System.Windows.Documents.Hyperlink> 元素组合在一起，在同一内对它们进行优化 <xref:System.Windows.Controls.TextBlock> 。 这有助于最小化在应用程序中创建的对象的数量。 例如，可显示多个超链接，如下所示：

MSN 主页 &#124; 我的 MSN

以下标记示例演示了 <xref:System.Windows.Controls.TextBlock> 用于显示超链接的多个元素：

[!code-xaml[Performance#PerformanceSnippet9](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]

以下标记示例演示了一种更有效的显示超链接的方法，这次使用单个 <xref:System.Windows.Controls.TextBlock> ：

[!code-xaml[Performance#PerformanceSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]

### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>仅在 MouseEnter 事件的超链接中显示下划线

<xref:System.Windows.TextDecoration>对象是可添加到文本的视觉对象，但它可能会对实例化的性能有很大的装饰。 如果对元素进行大量使用 <xref:System.Windows.Documents.Hyperlink> ，请考虑仅在触发事件（例如事件）时显示下划线 <xref:System.Windows.ContentElement.MouseEnter> 。 有关详细信息，请参阅[指定是否为超链接添加下划线](how-to-specify-whether-a-hyperlink-is-underlined.md)。

下图显示了 MouseEnter 事件如何触发带下划线的超链接：

![显示 TextDecoration 的超链接](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)

以下标记示例显示了 <xref:System.Windows.Documents.Hyperlink> 使用和不带下划线定义的：

[!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]

下表显示了 <xref:System.Windows.Documents.Hyperlink> 使用和不使用下划线显示1000元素的性能成本。

|**超链接**|**创建时间 (ms)**|**呈现时间 (ms)**|
|-------------------|------------------------------|----------------------------|
|使用下划线|289|1130|
|不使用下划线|299|776|

<a name="Text_Formatting_Features"></a>

## <a name="text-formatting-features"></a>文本格式设置功能

[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 提供丰富的文本格式设置服务，如自动断字。 这些服务可能会影响应用程序性能，应仅在需要时使用。

### <a name="avoid-unnecessary-use-of-hyphenation"></a>避免不必要地使用断字

自动断字功能可查找文本行的连字符断点，并允许和对象中的行具有额外的断点位置 <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Documents.FlowDocument> 。 默认禁用这些对象中的自动断字功能。 通过将该对象的 IsHyphenationEnabled 属性设置为 `true`，可以启用此功能。 但是，启用此功能会导致 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 启动组件对象模型 (COM) 互操作性，这可能会影响应用程序性能。 除非需要，否则不建议使用自动断字功能。

### <a name="use-figures-carefully"></a>谨慎使用图形

<xref:System.Windows.Documents.Figure>元素表示可以在内容页中完全定位的流内容部分。 在某些情况下， <xref:System.Windows.Documents.Figure> 可能会导致整个页面在其位置与已布局的内容冲突时自动重新设置格式。可以最大程度地减少不必要的重新格式化的可能性，只需分组 <xref:System.Windows.Documents.Figure> 元素，或在固定页面大小的情况下将其声明到内容顶部附近。

### <a name="optimal-paragraph"></a>最佳段落

对象的最佳段落功能 <xref:System.Windows.Documents.FlowDocument> 会将段落布局，以便尽可能均匀地分布空白。 默认禁用最佳段落功能。 可以通过将对象的 <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> 属性设置为来启用此功能 `true` 。 但是，启用此功能会影响应用程序的性能。 除非需要，否则不建议使用最佳段落功能。

## <a name="see-also"></a>请参阅

- [优化 WPF 应用程序性能](optimizing-wpf-application-performance.md)
- [规划应用程序性能](planning-for-application-performance.md)
- [利用硬件](optimizing-performance-taking-advantage-of-hardware.md)
- [布局和示例](optimizing-performance-layout-and-design.md)
- [二维图形和图像处理](optimizing-performance-2d-graphics-and-imaging.md)
- [对象行为](optimizing-performance-object-behavior.md)
- [应用程序资源](optimizing-performance-application-resources.md)
- [数据绑定](optimizing-performance-data-binding.md)
- [其他性能建议](optimizing-performance-other-recommendations.md)
