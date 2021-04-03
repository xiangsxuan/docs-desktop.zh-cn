---
title: 以编程方式更改 RichTextBox 中的选定内容
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- changing selections in a text box [WPF]
- changing selections in a RichTextBox [WPF]
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
ms.openlocfilehash: e3c76bd244e567857ebf132db5cc19c2d51139bd
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973259"
---
# <a name="change-selection-in-a-richtextbox-programmatically"></a><span data-ttu-id="d6e9b-102">以编程方式更改 RichTextBox 中的选定内容</span><span class="sxs-lookup"><span data-stu-id="d6e9b-102">Change Selection in a RichTextBox Programmatically</span></span>
<span data-ttu-id="d6e9b-103">此示例演示如何以编程方式更改中的当前选定内容 <xref:System.Windows.Controls.RichTextBox> 。</span><span class="sxs-lookup"><span data-stu-id="d6e9b-103">This example shows how to programmatically change the current selection in a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="d6e9b-104">此选择与用户通过使用用户界面选择内容的情况相同。</span><span class="sxs-lookup"><span data-stu-id="d6e9b-104">This selection is the same as if the user had selected the content by using the user interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6e9b-105">示例</span><span class="sxs-lookup"><span data-stu-id="d6e9b-105">Example</span></span>  
 <span data-ttu-id="d6e9b-106">下面的 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 代码描述了 <xref:System.Windows.Controls.RichTextBox> 具有简单内容的命名控件。</span><span class="sxs-lookup"><span data-stu-id="d6e9b-106">The following [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="d6e9b-107">示例</span><span class="sxs-lookup"><span data-stu-id="d6e9b-107">Example</span></span>  
 <span data-ttu-id="d6e9b-108">当用户在内单击时，以下代码以编程方式选择一些任意文本 <xref:System.Windows.Controls.RichTextBox> 。</span><span class="sxs-lookup"><span data-stu-id="d6e9b-108">The following code programmatically selects some arbitrary text when the user clicks inside the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="d6e9b-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6e9b-109">See also</span></span>

- [<span data-ttu-id="d6e9b-110">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="d6e9b-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="d6e9b-111">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="d6e9b-111">TextBox Overview</span></span>](textbox-overview.md)
