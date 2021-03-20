---
title: XAML 中的空白处理
ms.date: 03/30/2017
helpviewer_keywords:
- East Asian characters [XAML Services]
- XAML [XAML Services], white-space processing
- white-space processing in XAML [XAML Services]
- characters [XAML Services], East Asian
ms.assetid: cc9cc377-7544-4fd0-b65b-117b90bb0b23
ms.openlocfilehash: 4bba980f69800c85b9f3b443f4965ca52f5abf19
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667658"
---
# <a name="white-space-processing-in-xaml"></a>XAML 中的空白处理

XAML 的语言规则状态必须由处理器实现处理有效空白 [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] 。 本文介绍了这些 XAML 语言规则。 它还记录了由 [!INCLUDE[TLA#tla_winclient](../includes/tlasharptla-winclient-md.md)] xaml 处理器的实现和用于序列化的 xaml 编写器定义的其他空白处理。

## <a name="white-space-definition"></a>空格定义

与 XML 一致，中的空格字符 [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] 是空格、换行符和制表符。它们分别对应于 Unicode 值0020、000A 和0009。

## <a name="white-space-normalization"></a>空白标准化

默认情况下，当处理器处理文件时，将发生以下空白标准化 [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] ：

1. 删除中文字符间的换行符。 有关此术语的定义，请稍后参阅本主题中的“中文字符”一节。

2.  (空格、换行符、制表符) 的所有空白字符都将转换为空格。

3. 删除所有连续的空格，并替换为一个空格。

4. 删除开始标记后紧跟的一个空格。

5. 删除结束标记前紧跟的一个空格。

“默认”对应于由 [xml: space](xml-space-handling.md) 属性的默认值表示的状态。

## <a name="white-space-in-inner-text-and-string-primitives"></a>内部文本和字符串基元中的空格

先前的标准化规则适用于 XAML 元素中找到的内部文本。 标准化后，XAML 处理器将所有内部文本转换为适当的类型，如下所示：

- 如果属性的类型不是一个集合，但不直接是 <xref:System.Object> 类型，则 XAML 处理器会尝试使用其类型转换器来转换为该类型。 此处的转换失败将导致编译时错误。

- 如果该属性的类型是一个集合，并且内部文本是连续的（无干扰元素标记），则内部文本解析为单个 <xref:System.String>。 如果集合类型不能接受 <xref:System.String>，这也会导致编译时错误。

- 如果该属性的类型为 <xref:System.Object>，则内部文本解析为单个 <xref:System.String>。 如果存在干扰元素标记，这将导致编译时错误，因为 <xref:System.Object> 类型表示单个对象（<xref:System.String> 或其他）。

- 如果属性的类型是一个集合，并且内部文本是不连续的，则第一个子字符串将转换为 <xref:System.String> 并添加为集合项，干扰元素将添加为集合项，并且最后尾随的子字符串（如果有）将作为第三个 <xref:System.String> 项添加到集合。

## <a name="preserving-white-space"></a>保留空白

有几种方法可用于保留源中的空白 [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] ，以最终表示不受 [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] 处理器空白标准化的影响。

**xml： space = "preserve"**：在需要保留空格的元素级别指定此属性。 这样保留了所有的空格，其中包括可能由代码编辑应用程序添加到“优质打印”对齐元素以作为可视化直观嵌套的空格。 但是，是否呈现这些空白是由包含元素的内容模型决定的。 避免 `xml:space="preserve"` 在根级别指定，因为无论你如何设置该属性，大多数对象模型都不会将空格视为重要。 全局设置 `xml:space` 可能对 XAML 在某些实现中的处理（特别是序列化）产生性能后果。 更好的做法是仅在元素级别上设置属性，这些元素会在字符串中呈现空白，或者是空白的重要集合。

**实体和非换行空格**： [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] 支持在文本对象模型中放置任何 Unicode 实体。 可以在 UTF-8 编码) 中使用专用实体，如不间断空格 (&\# 160;。 还可以使用支持不间断空格字符的富文本控件。 如果使用实体来模拟布局特征（例如缩进），则应当小心，因为实体的运行时输出将根据更大数量的因素变化，而不是根据在典型布局系统中产生缩进结果的能力，如面板和边距的正确使用。 例如，实体映射到字体，并且可以响应用户的字体选择更改大小。

## <a name="east-asian-characters"></a>东亚字符

"中文字符" 定义为一组 Unicode 字符范围 U + 20000 到 U + 2FFFD 和 U + 30000 到 U + 3FFFD。 此子集有时也称为“CJK 表意文字”。 有关详细信息，请参阅 <https://www.unicode.org>。

## <a name="white-space-and-text-content-models"></a>空格和文本内容模型

在实践中，保留空白只是为了实现所有可能的内容模型的子集。 该子集由内容模型组成，这些模型可以采用某种形式的单独 <xref:System.String> 类型、专用 <xref:System.String> 集合，或 <xref:System.String> 和 <xref:System.Collections.IList> 或 <xref:System.Collections.Generic.ICollection%601> 集合中其他类型的混合。

### <a name="white-space-and-text-content-models-in-wpf"></a>WPF 中的空格和文本内容模型

为了便于说明，此部分的其余部分引用由 WPF 定义的特定类型。 本文中所述的空白处理功能与 .NET XAML 服务和 WPF 相关。 若要查看运行中的此行为，可以使用一些 WPF XAML 标记进行试验，在对象图中查看结果，然后重新序列化为标记。

即使对于可以采用字符串的内容模型，这些内容模型内的默认行为也不会被视为重要。 例如， <xref:System.Windows.Controls.ListBox> 采用 <xref:System.Collections.IList> ，但 <xref:System.Windows.Controls.ListBoxItem> 不会保留且不会呈现每个) 之间的 (（如换行符）。 如果尝试使用换行符作为 <xref:System.Windows.Controls.ListBoxItem> 项的字符串之间的分隔符，则完全不适用；由换行符分隔的字符串将被视为一个字符串和一个项。

那些将空格视为重要的集合通常是流文档模型的一部分。 支持空白保存行为的主集合为 <xref:System.Windows.Documents.InlineCollection> 。 此集合类与一起声明 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> ; 找到此属性时， [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] 处理器会将集合内的空格视为重要。 表示的集合中的和空格的组合 `xml:space="preserve"` 是指 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> 保留并呈现所有空格。 和中的空格组合 `xml:space="default"` <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> 会导致前面所述的初始空白标准化，这会在某些位置留下一个空格，并保留并呈现这些空格。 需要哪种行为由你决定，并且应有选择地使用 `xml:space` 以启用需要的行为。

此外，流文档模型中换行符换行符的某些内联元素应特意不会引入额外的空间，即使是在空白有意义的集合中。 例如，元素与 <xref:System.Windows.Documents.LineBreak> HTML 中的标记具有相同的用途， \<BR/> 为标记可读性，通常 <xref:System.Windows.Documents.LineBreak> 是由创作的换行符与任何后续文本分隔开。 不应标准化该换行符以使它成为后续行中的前导空格。 若要启用此行为，则元素的类定义 <xref:System.Windows.Documents.LineBreak> 将应用 <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> ，然后由处理器进行解释， [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] 以表示始终修整周围的空格 <xref:System.Windows.Documents.LineBreak> 。

## <a name="see-also"></a>请参阅

- [XAML 概述 (WPF)](../net/wpf/fundamentals/xaml.md)
- [XML 字符实体和 XAML](xml-character-entities.md)
- [xml：在 XAML 中处理空间](xml-space-handling.md)
