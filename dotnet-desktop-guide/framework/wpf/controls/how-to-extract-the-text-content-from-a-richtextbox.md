---
title: 如何：从 RichTextBox 中提取文本内容
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], extracting
- RichTextBox control [WPF], extracting text content
- content [WPF], extracting
- extracting text content [WPF]
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
ms.openlocfilehash: d1d40f37c23455dfc48206f84bca1b8438fec6c4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973240"
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a>如何：从 RichTextBox 中提取文本内容
此示例演示如何以 <xref:System.Windows.Controls.RichTextBox> 纯文本形式提取的内容。  
  
## <a name="example"></a>示例  
 下面的 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 代码描述了 <xref:System.Windows.Controls.RichTextBox> 具有简单内容的命名控件。  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a>示例  
 下面的代码实现一个方法，该方法采用 <xref:System.Windows.Controls.RichTextBox> 作为参数，并返回表示的纯文本内容的字符串 <xref:System.Windows.Controls.RichTextBox> 。  
  
 方法 <xref:System.Windows.Documents.TextRange> <xref:System.Windows.Controls.RichTextBox> 使用 <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> 和 <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> 来指定要提取的内容的范围，从的内容创建一个新的。  <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> 和 <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> 每个属性都返回一个 <xref:System.Windows.Documents.TextPointer> ，并可在表示的内容的基础 FlowDocument 上访问 <xref:System.Windows.Controls.RichTextBox> 。  <xref:System.Windows.Documents.TextRange> 提供一个文本属性，该属性以字符串的形式返回的纯文本部分 <xref:System.Windows.Documents.TextRange> 。  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a>另请参阅

- [RichTextBox 概述](richtextbox-overview.md)
- [TextBox 概述](textbox-overview.md)
