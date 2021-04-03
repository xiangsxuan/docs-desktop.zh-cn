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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973240"
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a><span data-ttu-id="c00c7-102">如何：从 RichTextBox 中提取文本内容</span><span class="sxs-lookup"><span data-stu-id="c00c7-102">How to: Extract the Text Content from a RichTextBox</span></span>
<span data-ttu-id="c00c7-103">此示例演示如何以 <xref:System.Windows.Controls.RichTextBox> 纯文本形式提取的内容。</span><span class="sxs-lookup"><span data-stu-id="c00c7-103">This example shows how to extract the contents of a <xref:System.Windows.Controls.RichTextBox> as plain text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c00c7-104">示例</span><span class="sxs-lookup"><span data-stu-id="c00c7-104">Example</span></span>  
 <span data-ttu-id="c00c7-105">下面的 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 代码描述了 <xref:System.Windows.Controls.RichTextBox> 具有简单内容的命名控件。</span><span class="sxs-lookup"><span data-stu-id="c00c7-105">The following [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a><span data-ttu-id="c00c7-106">示例</span><span class="sxs-lookup"><span data-stu-id="c00c7-106">Example</span></span>  
 <span data-ttu-id="c00c7-107">下面的代码实现一个方法，该方法采用 <xref:System.Windows.Controls.RichTextBox> 作为参数，并返回表示的纯文本内容的字符串 <xref:System.Windows.Controls.RichTextBox> 。</span><span class="sxs-lookup"><span data-stu-id="c00c7-107">The following code implements a method that takes a <xref:System.Windows.Controls.RichTextBox> as an argument, and returns a string representing the plain text contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="c00c7-108">方法 <xref:System.Windows.Documents.TextRange> <xref:System.Windows.Controls.RichTextBox> 使用 <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> 和 <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> 来指定要提取的内容的范围，从的内容创建一个新的。</span><span class="sxs-lookup"><span data-stu-id="c00c7-108">The method creates a new <xref:System.Windows.Documents.TextRange> from the contents of the <xref:System.Windows.Controls.RichTextBox>, using the <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> to indicate the range of the contents to extract.</span></span>  <span data-ttu-id="c00c7-109"><xref:System.Windows.Documents.FlowDocument.ContentStart%2A> 和 <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> 每个属性都返回一个 <xref:System.Windows.Documents.TextPointer> ，并可在表示的内容的基础 FlowDocument 上访问 <xref:System.Windows.Controls.RichTextBox> 。</span><span class="sxs-lookup"><span data-stu-id="c00c7-109"><xref:System.Windows.Documents.FlowDocument.ContentStart%2A> and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> properties each return a <xref:System.Windows.Documents.TextPointer>, and are accessible on the underlying FlowDocument that represents the contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  <span data-ttu-id="c00c7-110"><xref:System.Windows.Documents.TextRange> 提供一个文本属性，该属性以字符串的形式返回的纯文本部分 <xref:System.Windows.Documents.TextRange> 。</span><span class="sxs-lookup"><span data-stu-id="c00c7-110"><xref:System.Windows.Documents.TextRange> provides a Text property, which returns the plain text portions of the <xref:System.Windows.Documents.TextRange> as a string.</span></span>  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a><span data-ttu-id="c00c7-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c00c7-111">See also</span></span>

- [<span data-ttu-id="c00c7-112">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="c00c7-112">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="c00c7-113">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="c00c7-113">TextBox Overview</span></span>](textbox-overview.md)
