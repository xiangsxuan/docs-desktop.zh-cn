---
title: 如何：调整段落间的间距
ms.date: 03/30/2017
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
ms.openlocfilehash: e2a6ba34e3ab15eb316671fef7c11bea03d53c73
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972471"
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a><span data-ttu-id="0122c-102">如何：调整段落间的间距</span><span class="sxs-lookup"><span data-stu-id="0122c-102">How to: Adjust Spacing Between Paragraphs</span></span>
<span data-ttu-id="0122c-103">此示例演示如何调整或消除流内容中段落间的间距。</span><span class="sxs-lookup"><span data-stu-id="0122c-103">This example shows how to adjust or eliminate spacing between paragraphs in flow content.</span></span>  
  
 <span data-ttu-id="0122c-104">在流内容中，在段落之间出现的额外空间是对这些段落设置的边距的结果;因此，可以通过调整这些段落的边距来控制段落间的间距。</span><span class="sxs-lookup"><span data-stu-id="0122c-104">In flow content, extra space that appears between paragraphs is the result of margins set on these paragraphs; thus, the spacing between paragraphs can be controlled by adjusting the margins on those paragraphs.</span></span>  <span data-ttu-id="0122c-105">若要在两个段落之间完全消除额外的间距，请将段落边距设置为 **0**。</span><span class="sxs-lookup"><span data-stu-id="0122c-105">To eliminate extra spacing between two paragraphs altogether, set the margins for the paragraphs to **0**.</span></span>  <span data-ttu-id="0122c-106">若要在整个中的段落间实现统一 <xref:System.Windows.Documents.FlowDocument> 的间距，请使用样式设置为中的所有段落设置统一的边距值 <xref:System.Windows.Documents.FlowDocument> 。</span><span class="sxs-lookup"><span data-stu-id="0122c-106">To achieve uniform spacing between paragraphs throughout an entire <xref:System.Windows.Documents.FlowDocument>, use styling to set a uniform margin value for all paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="0122c-107">需要注意的是，两个相邻段落的边距将 "折叠" 到两个边距中的较大者，而不是加倍。</span><span class="sxs-lookup"><span data-stu-id="0122c-107">It is important to note that the margins for two adjacent paragraphs will "collapse" to the larger of the two margins, rather than doubling up.</span></span> <span data-ttu-id="0122c-108">因此，如果两个相邻段落分别具有20个像素和40像素的边距，则段落间的间距为40像素，这是两个边距值中较大的一个。</span><span class="sxs-lookup"><span data-stu-id="0122c-108">So, if two adjacent paragraphs have margins of 20 pixels and 40 pixels respectively, the resulting space between the paragraphs is 40 pixels, the larger of the two margin values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0122c-109">示例</span><span class="sxs-lookup"><span data-stu-id="0122c-109">Example</span></span>  
 <span data-ttu-id="0122c-110">下面的示例使用样式设置将中所有元素的边距设置 <xref:System.Windows.Documents.Paragraph> <xref:System.Windows.Documents.FlowDocument> 为 **0**，从而有效地消除中的段落间的额外间距 <xref:System.Windows.Documents.FlowDocument> 。</span><span class="sxs-lookup"><span data-stu-id="0122c-110">The following example uses styling to set the margin for all <xref:System.Windows.Documents.Paragraph> elements in a <xref:System.Windows.Documents.FlowDocument> to **0**, which effectively eliminates extra spacing between paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
