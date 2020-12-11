---
title: 如何：以编程方式将元素插入文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Text Animation sample [WPF]
- elements [WPF], inserting into text
- inserting elements into text [WPF]
- TextPointer objects [WPF]
- text [WPF], inserting elements
ms.assetid: 97bd950a-25ac-4e42-a311-94b6420d4136
ms.openlocfilehash: ea9850c8490ec37032d4565c6b3375e3116d4313
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973200"
---
# <a name="how-to-insert-an-element-into-text-programmatically"></a><span data-ttu-id="4a6fb-102">如何：以编程方式将元素插入文本</span><span class="sxs-lookup"><span data-stu-id="4a6fb-102">How to: Insert an Element Into Text Programmatically</span></span>
<span data-ttu-id="4a6fb-103">下面的示例演示如何使用两个 <xref:System.Windows.Documents.TextPointer> 对象来指定要向其应用元素的文本范围 <xref:System.Windows.Documents.Span> 。</span><span class="sxs-lookup"><span data-stu-id="4a6fb-103">The following example shows how to use two <xref:System.Windows.Documents.TextPointer> objects to specify a range within text to apply a <xref:System.Windows.Documents.Span> element to.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a6fb-104">示例</span><span class="sxs-lookup"><span data-stu-id="4a6fb-104">Example</span></span>  
 [!code-csharp[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/CSharp/InsertInlineIntoTextExample.cs#insertinlineintotextexamplewholepage)]
 [!code-vb[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/VisualBasic/InsertInlineIntoTextExample.vb#insertinlineintotextexamplewholepage)]  
  
 <span data-ttu-id="4a6fb-105">下图显示此示例。</span><span class="sxs-lookup"><span data-stu-id="4a6fb-105">The illustration below shows what this example looks like.</span></span>  
  
 <span data-ttu-id="4a6fb-106">![应用于一定范围文本的 Span 元素](./media/flow-insertelementintotextprogrammatically.png "Flow_InsertElementIntoTextProgrammatically")</span><span class="sxs-lookup"><span data-stu-id="4a6fb-106">![A Span element applied to a range of text](./media/flow-insertelementintotextprogrammatically.png "Flow_InsertElementIntoTextProgrammatically")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a6fb-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a6fb-107">See also</span></span>

- [<span data-ttu-id="4a6fb-108">流文档概述</span><span class="sxs-lookup"><span data-stu-id="4a6fb-108">Flow Document Overview</span></span>](flow-document-overview.md)
