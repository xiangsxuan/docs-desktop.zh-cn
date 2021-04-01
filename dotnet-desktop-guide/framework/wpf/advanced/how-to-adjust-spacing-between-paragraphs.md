---
title: 如何：调整段落间的间距
ms.date: 03/30/2017
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
ms.openlocfilehash: e2a6ba34e3ab15eb316671fef7c11bea03d53c73
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972471"
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a>如何：调整段落间的间距
此示例演示如何调整或消除流内容中段落间的间距。  
  
 在流内容中，在段落之间出现的额外空间是对这些段落设置的边距的结果;因此，可以通过调整这些段落的边距来控制段落间的间距。  若要在两个段落之间完全消除额外的间距，请将段落边距设置为 **0**。  若要在整个中的段落间实现统一 <xref:System.Windows.Documents.FlowDocument> 的间距，请使用样式设置为中的所有段落设置统一的边距值 <xref:System.Windows.Documents.FlowDocument> 。  
  
 需要注意的是，两个相邻段落的边距将 "折叠" 到两个边距中的较大者，而不是加倍。 因此，如果两个相邻段落分别具有20个像素和40像素的边距，则段落间的间距为40像素，这是两个边距值中较大的一个。  
  
## <a name="example"></a>示例  
 下面的示例使用样式设置将中所有元素的边距设置 <xref:System.Windows.Documents.Paragraph> <xref:System.Windows.Documents.FlowDocument> 为 **0**，从而有效地消除中的段落间的额外间距 <xref:System.Windows.Documents.FlowDocument> 。  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
