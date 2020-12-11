---
title: 如何：通过 Blocks 属性操作 FlowDocument
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], manipulating FlowDocuments through Blocks property [WPF], , '
- ', '
ms.assetid: cbb7291e-3f1b-433e-9e16-f4d93ced14e8
ms.openlocfilehash: c307d85bf24e2d8a20226856181e0758758d40c0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970880"
---
# <a name="how-to-manipulate-a-flowdocument-through-the-blocks-property"></a><span data-ttu-id="d2c5a-102">如何：通过 Blocks 属性操作 FlowDocument</span><span class="sxs-lookup"><span data-stu-id="d2c5a-102">How to: Manipulate a FlowDocument through the Blocks Property</span></span>
<span data-ttu-id="d2c5a-103">这些示例演示了可以通过属性在上执行的一些更常见的操作 <xref:System.Windows.Documents.FlowDocument> <xref:System.Windows.Documents.FlowDocument.Blocks%2A> 。</span><span class="sxs-lookup"><span data-stu-id="d2c5a-103">These examples demonstrate some of the more common operations that can be performed on a <xref:System.Windows.Documents.FlowDocument> through the <xref:System.Windows.Documents.FlowDocument.Blocks%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2c5a-104">示例</span><span class="sxs-lookup"><span data-stu-id="d2c5a-104">Example</span></span>  
 <span data-ttu-id="d2c5a-105">下面的示例创建一个新的 <xref:System.Windows.Documents.FlowDocument> ，然后向添加一个新 <xref:System.Windows.Documents.Paragraph> 元素 <xref:System.Windows.Documents.FlowDocument> 。</span><span class="sxs-lookup"><span data-stu-id="d2c5a-105">The following example creates a new <xref:System.Windows.Documents.FlowDocument> and then appends a new <xref:System.Windows.Documents.Paragraph> element to the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksadd)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="d2c5a-106">示例</span><span class="sxs-lookup"><span data-stu-id="d2c5a-106">Example</span></span>  
 <span data-ttu-id="d2c5a-107">下面的示例创建一个新的 <xref:System.Windows.Documents.Paragraph> 元素，并将其插入到的 <xref:System.Windows.Documents.FlowDocument> 开头。</span><span class="sxs-lookup"><span data-stu-id="d2c5a-107">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="d2c5a-108">示例</span><span class="sxs-lookup"><span data-stu-id="d2c5a-108">Example</span></span>  
 <span data-ttu-id="d2c5a-109">下面的示例获取中包含的顶级元素的数目 <xref:System.Windows.Documents.Block> <xref:System.Windows.Documents.FlowDocument> 。</span><span class="sxs-lookup"><span data-stu-id="d2c5a-109">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksCount](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblockscount)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblockscount)]  
  
## <a name="example"></a><span data-ttu-id="d2c5a-110">示例</span><span class="sxs-lookup"><span data-stu-id="d2c5a-110">Example</span></span>  
 <span data-ttu-id="d2c5a-111">下面的示例删除中的最后一个 <xref:System.Windows.Documents.Block> 元素 <xref:System.Windows.Documents.FlowDocument> 。</span><span class="sxs-lookup"><span data-stu-id="d2c5a-111">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="d2c5a-112">示例</span><span class="sxs-lookup"><span data-stu-id="d2c5a-112">Example</span></span>  
 <span data-ttu-id="d2c5a-113">下面的示例从中清除)  (元素的所有内容 <xref:System.Windows.Documents.Block> <xref:System.Windows.Documents.FlowDocument> 。</span><span class="sxs-lookup"><span data-stu-id="d2c5a-113">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksClear](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksclear)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="d2c5a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2c5a-114">See also</span></span>

- [<span data-ttu-id="d2c5a-115">通过 RowGroups 属性操作表的行组</span><span class="sxs-lookup"><span data-stu-id="d2c5a-115">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="d2c5a-116">通过 Columns 属性操作表的列</span><span class="sxs-lookup"><span data-stu-id="d2c5a-116">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
- [<span data-ttu-id="d2c5a-117">通过 RowGroups 属性操作表的行组</span><span class="sxs-lookup"><span data-stu-id="d2c5a-117">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
