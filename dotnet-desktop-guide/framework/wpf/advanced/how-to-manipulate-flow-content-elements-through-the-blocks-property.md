---
title: 如何：通过 Blocks 属性操作流内容元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating flow content elements through Blocks property
- flow content elements [WPF], manipulating through Blocks property
- properties [WPF], Blocks [WPF], manipulating flow content elements
- Blocks property [WPF], manipulating flow content elements
ms.assetid: aeda4ece-b979-4818-a093-ef938e908751
ms.openlocfilehash: 3ca05590bd1adf7f9c486382a08cb334b4731ac9
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970641"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-blocks-property"></a><span data-ttu-id="5a120-102">如何：通过 Blocks 属性操作流内容元素</span><span class="sxs-lookup"><span data-stu-id="5a120-102">How to: Manipulate Flow Content Elements through the Blocks Property</span></span>
<span data-ttu-id="5a120-103">这些示例演示了一些更常见的操作，这些操作可通过 **块** 属性在流内容元素上执行。</span><span class="sxs-lookup"><span data-stu-id="5a120-103">These examples demonstrate some of the more common operations that can be performed on flow content elements through the **Blocks** property.</span></span> <span data-ttu-id="5a120-104">此属性用于在中添加和移除项 <xref:System.Windows.Documents.BlockCollection> 。</span><span class="sxs-lookup"><span data-stu-id="5a120-104">This property is used to add and remove items from <xref:System.Windows.Documents.BlockCollection>.</span></span> <span data-ttu-id="5a120-105">功能 **块** 属性的流内容元素包括：</span><span class="sxs-lookup"><span data-stu-id="5a120-105">Flow content elements that feature a **Blocks** property include:</span></span>  
  
- <xref:System.Windows.Documents.Figure>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.ListItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="5a120-106">这些示例将 <xref:System.Windows.Documents.Section> 用作流内容元素，但这些方法适用于承载流内容元素集合的所有元素。</span><span class="sxs-lookup"><span data-stu-id="5a120-106">These examples happen to use <xref:System.Windows.Documents.Section> as the flow content element, but these techniques are applicable to all elements that host a flow content element collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a120-107">示例</span><span class="sxs-lookup"><span data-stu-id="5a120-107">Example</span></span>  
 <span data-ttu-id="5a120-108">下面的示例创建一个新的 <xref:System.Windows.Documents.Section> ，然后使用 **add** 方法将一个新段落添加到 **节** 内容。</span><span class="sxs-lookup"><span data-stu-id="5a120-108">The following example creates a new <xref:System.Windows.Documents.Section> and then uses the **Add** method to add a new Paragraph to the **Section** contents.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="5a120-109">示例</span><span class="sxs-lookup"><span data-stu-id="5a120-109">Example</span></span>  
 <span data-ttu-id="5a120-110">下面的示例创建一个新的 <xref:System.Windows.Documents.Paragraph> 元素，并将其插入到的 <xref:System.Windows.Documents.Section> 开头。</span><span class="sxs-lookup"><span data-stu-id="5a120-110">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="5a120-111">示例</span><span class="sxs-lookup"><span data-stu-id="5a120-111">Example</span></span>  
 <span data-ttu-id="5a120-112">下面的示例获取中包含的顶级元素的数目 <xref:System.Windows.Documents.Block> <xref:System.Windows.Documents.Section> 。</span><span class="sxs-lookup"><span data-stu-id="5a120-112">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksCount](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblockscount)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblockscount)]  
  
## <a name="example"></a><span data-ttu-id="5a120-113">示例</span><span class="sxs-lookup"><span data-stu-id="5a120-113">Example</span></span>  
 <span data-ttu-id="5a120-114">下面的示例删除中的最后一个 <xref:System.Windows.Documents.Block> 元素 <xref:System.Windows.Documents.Section> 。</span><span class="sxs-lookup"><span data-stu-id="5a120-114">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="5a120-115">示例</span><span class="sxs-lookup"><span data-stu-id="5a120-115">Example</span></span>  
 <span data-ttu-id="5a120-116">下面的示例从中清除)  (元素的所有内容 <xref:System.Windows.Documents.Block> <xref:System.Windows.Documents.Section> 。</span><span class="sxs-lookup"><span data-stu-id="5a120-116">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksClear](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksclear)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="5a120-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a120-117">See also</span></span>

- <xref:System.Windows.Documents.BlockCollection>
- <xref:System.Windows.Documents.InlineCollection>
- <xref:System.Windows.Documents.ListItemCollection>
- [<span data-ttu-id="5a120-118">流文档概述</span><span class="sxs-lookup"><span data-stu-id="5a120-118">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="5a120-119">通过 RowGroups 属性操作表的行组</span><span class="sxs-lookup"><span data-stu-id="5a120-119">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="5a120-120">通过 Columns 属性操作表的列</span><span class="sxs-lookup"><span data-stu-id="5a120-120">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
- [<span data-ttu-id="5a120-121">通过 RowGroups 属性操作表的行组</span><span class="sxs-lookup"><span data-stu-id="5a120-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
