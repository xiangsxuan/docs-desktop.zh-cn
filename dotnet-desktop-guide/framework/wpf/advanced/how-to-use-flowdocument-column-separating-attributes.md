---
title: 如何：使用 FlowDocument 列分隔特性
ms.date: 03/30/2017
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
ms.openlocfilehash: 27491b21da587fa198061ba52d8daed5d3f28de3
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973743"
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a><span data-ttu-id="72340-102">如何：使用 FlowDocument 列分隔特性</span><span class="sxs-lookup"><span data-stu-id="72340-102">How to: Use FlowDocument Column-Separating Attributes</span></span>
<span data-ttu-id="72340-103">此示例演示如何使用的列分隔功能 <xref:System.Windows.Documents.FlowDocument> 。</span><span class="sxs-lookup"><span data-stu-id="72340-103">This example shows how to use the column-separating features of a <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72340-104">示例</span><span class="sxs-lookup"><span data-stu-id="72340-104">Example</span></span>  
 <span data-ttu-id="72340-105">下面的示例定义一个 <xref:System.Windows.Documents.FlowDocument> ，并设置 <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A> 、和 <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A> <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> 特性。</span><span class="sxs-lookup"><span data-stu-id="72340-105">The following example defines a <xref:System.Windows.Documents.FlowDocument>, and sets the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes.</span></span>  <span data-ttu-id="72340-106"><xref:System.Windows.Documents.FlowDocument>包含一段示例内容。</span><span class="sxs-lookup"><span data-stu-id="72340-106">The <xref:System.Windows.Documents.FlowDocument> contains a single paragraph of sample content.</span></span>  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 <span data-ttu-id="72340-107">下图显示了 <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A> <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A> 在呈现的中的、和 <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> 特性的影响 <xref:System.Windows.Documents.FlowDocument> 。</span><span class="sxs-lookup"><span data-stu-id="72340-107">The following figure shows the effects of the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes in a rendered <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 ![显示 FlowDocument 内部列属性的屏幕截图。](./media/how-to-use-flowdocument-column-separating-attributes/flowdocument-intra-column.png)
