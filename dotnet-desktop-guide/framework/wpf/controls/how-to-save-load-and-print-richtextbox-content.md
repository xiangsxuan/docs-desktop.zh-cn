---
title: 如何：保存、加载和打印 RichTextBox 内容
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- saving RichTextBox controls [WPF]
- printing RichTextBox controls [WPF]
- loading RichTextBox controls [WPF]
- RichTextBox control [WPF], saving
- RichTextBox control [WPF], printing
- RichTextBox control [WPF], loading
ms.assetid: ffb113d3-c68a-47ca-8ac0-882283f38326
ms.openlocfilehash: 90581bee7815dafd44c3cae18a8af7394fee1e9a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973589"
---
# <a name="how-to-save-load-and-print-richtextbox-content"></a><span data-ttu-id="3cd56-102">如何：保存、加载和打印 RichTextBox 内容</span><span class="sxs-lookup"><span data-stu-id="3cd56-102">How to: Save, Load, and Print RichTextBox Content</span></span>
<span data-ttu-id="3cd56-103">下面的示例演示如何将的内容保存 <xref:System.Windows.Controls.RichTextBox> 到文件，将该内容重新加载到 <xref:System.Windows.Controls.RichTextBox> 中，然后打印内容。</span><span class="sxs-lookup"><span data-stu-id="3cd56-103">The following example shows how to save content of a <xref:System.Windows.Controls.RichTextBox> to a file, load that content back into the <xref:System.Windows.Controls.RichTextBox>, and print the contents.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cd56-104">示例</span><span class="sxs-lookup"><span data-stu-id="3cd56-104">Example</span></span>  
 <span data-ttu-id="3cd56-105">下面是示例的标记。</span><span class="sxs-lookup"><span data-stu-id="3cd56-105">Below is the markup for the example.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="3cd56-106">示例</span><span class="sxs-lookup"><span data-stu-id="3cd56-106">Example</span></span>  
 <span data-ttu-id="3cd56-107">下面是该示例的隐藏代码。</span><span class="sxs-lookup"><span data-stu-id="3cd56-107">Below is the code behind for the example.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="3cd56-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cd56-108">See also</span></span>

- [<span data-ttu-id="3cd56-109">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="3cd56-109">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="3cd56-110">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="3cd56-110">TextBox Overview</span></span>](textbox-overview.md)
