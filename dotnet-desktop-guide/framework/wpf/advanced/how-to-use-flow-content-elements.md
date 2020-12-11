---
title: 如何：使用流内容元素
ms.date: 03/30/2017
helpviewer_keywords:
- flow content elements [WPF]
- documents [WPF], flow content elements
ms.assetid: 70fa11cd-5fa7-4872-a1cc-04d80f1132be
ms.openlocfilehash: f61116c0bf52ac726238d9e21c2422cedbb4716f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971805"
---
# <a name="how-to-use-flow-content-elements"></a><span data-ttu-id="2749e-102">如何：使用流内容元素</span><span class="sxs-lookup"><span data-stu-id="2749e-102">How to: Use Flow Content Elements</span></span>
<span data-ttu-id="2749e-103">下面的示例演示各种流内容元素及其相关联特性的声明性用法。</span><span class="sxs-lookup"><span data-stu-id="2749e-103">The following example demonstrates declarative usage for various flow content elements and associated attributes.</span></span>  <span data-ttu-id="2749e-104">演示的元素和特性包括：</span><span class="sxs-lookup"><span data-stu-id="2749e-104">Elements and attributes demonstrated include:</span></span>  
  
- <span data-ttu-id="2749e-105"><xref:System.Windows.Documents.Bold> 元素</span><span class="sxs-lookup"><span data-stu-id="2749e-105"><xref:System.Windows.Documents.Bold> element</span></span>  
  
- <span data-ttu-id="2749e-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> 特性</span><span class="sxs-lookup"><span data-stu-id="2749e-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> attribute</span></span>  
  
- <span data-ttu-id="2749e-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> 特性</span><span class="sxs-lookup"><span data-stu-id="2749e-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> attribute</span></span>  
  
- <span data-ttu-id="2749e-108"><xref:System.Windows.Documents.Italic> 元素</span><span class="sxs-lookup"><span data-stu-id="2749e-108"><xref:System.Windows.Documents.Italic> element</span></span>  
  
- <span data-ttu-id="2749e-109"><xref:System.Windows.Documents.LineBreak> 元素</span><span class="sxs-lookup"><span data-stu-id="2749e-109"><xref:System.Windows.Documents.LineBreak> element</span></span>  
  
- <span data-ttu-id="2749e-110"><xref:System.Windows.Documents.List> 元素</span><span class="sxs-lookup"><span data-stu-id="2749e-110"><xref:System.Windows.Documents.List> element</span></span>  
  
- <span data-ttu-id="2749e-111"><xref:System.Windows.Documents.ListItem> 元素</span><span class="sxs-lookup"><span data-stu-id="2749e-111"><xref:System.Windows.Documents.ListItem> element</span></span>  
  
- <span data-ttu-id="2749e-112"><xref:System.Windows.Documents.Paragraph> 元素</span><span class="sxs-lookup"><span data-stu-id="2749e-112"><xref:System.Windows.Documents.Paragraph> element</span></span>  
  
- <span data-ttu-id="2749e-113"><xref:System.Windows.Documents.Run> 元素</span><span class="sxs-lookup"><span data-stu-id="2749e-113"><xref:System.Windows.Documents.Run> element</span></span>  
  
- <span data-ttu-id="2749e-114"><xref:System.Windows.Documents.Section> 元素</span><span class="sxs-lookup"><span data-stu-id="2749e-114"><xref:System.Windows.Documents.Section> element</span></span>  
  
- <span data-ttu-id="2749e-115"><xref:System.Windows.Documents.Span> 元素</span><span class="sxs-lookup"><span data-stu-id="2749e-115"><xref:System.Windows.Documents.Span> element</span></span>  
  
- <span data-ttu-id="2749e-116"><xref:System.Windows.Documents.Typography.Variants%2A> 特性 (上标和下标) </span><span class="sxs-lookup"><span data-stu-id="2749e-116"><xref:System.Windows.Documents.Typography.Variants%2A> attribute (superscript and subscript)</span></span>  
  
- <span data-ttu-id="2749e-117"><xref:System.Windows.Documents.Underline> 元素</span><span class="sxs-lookup"><span data-stu-id="2749e-117"><xref:System.Windows.Documents.Underline> element</span></span>  
  
## <a name="example"></a><span data-ttu-id="2749e-118">示例</span><span class="sxs-lookup"><span data-stu-id="2749e-118">Example</span></span>  
 [!code-xaml[FlowDocInlineSnippets#_InlineElementsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocInlineSnippets/CS/document.xaml#_inlineelementsxaml)]
