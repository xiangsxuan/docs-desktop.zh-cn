---
title: 如何：通过 Inlines 属性操作流内容元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], manipulating through Inlines property
- documents [WPF], manipulating flow Content elements through Inlines property
- Inlines property [WPF], manipulating flow Content elements
- properties [WPF], Inlines [WPF], manipulating flow Content elements
ms.assetid: 510780d2-3da1-4360-8763-7054bda22ea3
ms.openlocfilehash: 92f23fbf44464eb7658f3382f873f3db63f7cb26
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972973"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-inlines-property"></a>如何：通过 Inlines 属性操作流内容元素
这些示例演示了一些更常见的操作，这些操作可对内联流内容元素执行 (和此类元素的容器，例如 <xref:System.Windows.Controls.TextBlock> 通过 **Inlines** 属性) 。 此属性用于在中添加和移除项 <xref:System.Windows.Documents.InlineCollection> 。 功能 **Inlines** 属性的流内容元素包括：  
  
- <xref:System.Windows.Documents.Bold>  
  
- <xref:System.Windows.Documents.Hyperlink>  
  
- <xref:System.Windows.Documents.Italic>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Span>  
  
- <xref:System.Windows.Documents.Underline>  
  
 这些示例将 <xref:System.Windows.Documents.Span> 用作流内容元素，但这些方法适用于托管集合的所有元素或控件 <xref:System.Windows.Documents.InlineCollection> 。  
  
## <a name="example"></a>示例  
 下面的示例创建一个新的 <xref:System.Windows.Documents.Span> 对象，然后使用 **add** 方法将两个文本运行添加为的内容子对象 <xref:System.Windows.Documents.Span> 。  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## <a name="example"></a>示例  
 下面的示例创建一个新的 <xref:System.Windows.Documents.Run> 元素，并将其插入到的 <xref:System.Windows.Documents.Span> 开头。  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## <a name="example"></a>示例  
 下面的示例获取中包含的顶级元素的数目 <xref:System.Windows.Documents.Inline> <xref:System.Windows.Documents.Span> 。  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## <a name="example"></a>示例  
 下面的示例删除中的最后一个 <xref:System.Windows.Documents.Inline> 元素 <xref:System.Windows.Documents.Span> 。  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## <a name="example"></a>示例  
 下面的示例从中清除)  (元素的所有内容 <xref:System.Windows.Documents.Inline> <xref:System.Windows.Documents.Span> 。  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Documents.BlockCollection>
- <xref:System.Windows.Documents.InlineCollection>
- <xref:System.Windows.Documents.ListItemCollection>
- [流文档概述](flow-document-overview.md)
- [通过 Blocks 属性操作 FlowDocument](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [通过 Columns 属性操作表的列](how-to-manipulate-table-columns-through-the-columns-property.md)
- [通过 RowGroups 属性操作表的行组](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
