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
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972973"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-inlines-property"></a><span data-ttu-id="40960-102">如何：通过 Inlines 属性操作流内容元素</span><span class="sxs-lookup"><span data-stu-id="40960-102">How to: Manipulate Flow Content Elements through the Inlines Property</span></span>
<span data-ttu-id="40960-103">这些示例演示了一些更常见的操作，这些操作可对内联流内容元素执行 (和此类元素的容器，例如 <xref:System.Windows.Controls.TextBlock> 通过 **Inlines** 属性) 。</span><span class="sxs-lookup"><span data-stu-id="40960-103">These examples demonstrate some of the more common operations that can be performed on inline flow content elements (and containers of such elements, such as <xref:System.Windows.Controls.TextBlock>) through the **Inlines** property.</span></span> <span data-ttu-id="40960-104">此属性用于在中添加和移除项 <xref:System.Windows.Documents.InlineCollection> 。</span><span class="sxs-lookup"><span data-stu-id="40960-104">This property is used to add and remove items from <xref:System.Windows.Documents.InlineCollection>.</span></span> <span data-ttu-id="40960-105">功能 **Inlines** 属性的流内容元素包括：</span><span class="sxs-lookup"><span data-stu-id="40960-105">Flow content elements that feature an **Inlines** property include:</span></span>  
  
- <xref:System.Windows.Documents.Bold>  
  
- <xref:System.Windows.Documents.Hyperlink>  
  
- <xref:System.Windows.Documents.Italic>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Span>  
  
- <xref:System.Windows.Documents.Underline>  
  
 <span data-ttu-id="40960-106">这些示例将 <xref:System.Windows.Documents.Span> 用作流内容元素，但这些方法适用于托管集合的所有元素或控件 <xref:System.Windows.Documents.InlineCollection> 。</span><span class="sxs-lookup"><span data-stu-id="40960-106">These examples happen to use <xref:System.Windows.Documents.Span> as the flow content element, but these techniques are applicable to all elements or controls that host an <xref:System.Windows.Documents.InlineCollection> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40960-107">示例</span><span class="sxs-lookup"><span data-stu-id="40960-107">Example</span></span>  
 <span data-ttu-id="40960-108">下面的示例创建一个新的 <xref:System.Windows.Documents.Span> 对象，然后使用 **add** 方法将两个文本运行添加为的内容子对象 <xref:System.Windows.Documents.Span> 。</span><span class="sxs-lookup"><span data-stu-id="40960-108">The following example creates a new <xref:System.Windows.Documents.Span> object, and then uses the **Add** method to add two text runs as content children of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## <a name="example"></a><span data-ttu-id="40960-109">示例</span><span class="sxs-lookup"><span data-stu-id="40960-109">Example</span></span>  
 <span data-ttu-id="40960-110">下面的示例创建一个新的 <xref:System.Windows.Documents.Run> 元素，并将其插入到的 <xref:System.Windows.Documents.Span> 开头。</span><span class="sxs-lookup"><span data-stu-id="40960-110">The following example creates a new <xref:System.Windows.Documents.Run> element and inserts it at the beginning of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## <a name="example"></a><span data-ttu-id="40960-111">示例</span><span class="sxs-lookup"><span data-stu-id="40960-111">Example</span></span>  
 <span data-ttu-id="40960-112">下面的示例获取中包含的顶级元素的数目 <xref:System.Windows.Documents.Inline> <xref:System.Windows.Documents.Span> 。</span><span class="sxs-lookup"><span data-stu-id="40960-112">The following example gets the number of top-level <xref:System.Windows.Documents.Inline> elements contained in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## <a name="example"></a><span data-ttu-id="40960-113">示例</span><span class="sxs-lookup"><span data-stu-id="40960-113">Example</span></span>  
 <span data-ttu-id="40960-114">下面的示例删除中的最后一个 <xref:System.Windows.Documents.Inline> 元素 <xref:System.Windows.Documents.Span> 。</span><span class="sxs-lookup"><span data-stu-id="40960-114">The following example deletes the last <xref:System.Windows.Documents.Inline> element in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## <a name="example"></a><span data-ttu-id="40960-115">示例</span><span class="sxs-lookup"><span data-stu-id="40960-115">Example</span></span>  
 <span data-ttu-id="40960-116">下面的示例从中清除)  (元素的所有内容 <xref:System.Windows.Documents.Inline> <xref:System.Windows.Documents.Span> 。</span><span class="sxs-lookup"><span data-stu-id="40960-116">The following example clears all of the contents (<xref:System.Windows.Documents.Inline> elements) from the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## <a name="see-also"></a><span data-ttu-id="40960-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40960-117">See also</span></span>

- <xref:System.Windows.Documents.BlockCollection>
- <xref:System.Windows.Documents.InlineCollection>
- <xref:System.Windows.Documents.ListItemCollection>
- [<span data-ttu-id="40960-118">流文档概述</span><span class="sxs-lookup"><span data-stu-id="40960-118">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="40960-119">通过 Blocks 属性操作 FlowDocument</span><span class="sxs-lookup"><span data-stu-id="40960-119">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="40960-120">通过 Columns 属性操作表的列</span><span class="sxs-lookup"><span data-stu-id="40960-120">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
- [<span data-ttu-id="40960-121">通过 RowGroups 属性操作表的行组</span><span class="sxs-lookup"><span data-stu-id="40960-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)