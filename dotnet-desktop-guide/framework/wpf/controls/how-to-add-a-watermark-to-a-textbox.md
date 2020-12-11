---
title: 如何：在 TextBox 中添加水印
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
ms.openlocfilehash: abe276c686d394ded13ec03f08deae65e4098d03
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972949"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a><span data-ttu-id="001f8-102">如何：在 TextBox 中添加水印</span><span class="sxs-lookup"><span data-stu-id="001f8-102">How to: Add a Watermark to a TextBox</span></span>
<span data-ttu-id="001f8-103">下面的示例演示了如何 <xref:System.Windows.Controls.TextBox> 通过在用户输入文本之前，在中显示说明性背景图像来帮助的可用性 <xref:System.Windows.Controls.TextBox> ，此时将删除图像。</span><span class="sxs-lookup"><span data-stu-id="001f8-103">The following example shows how to aid usability of a <xref:System.Windows.Controls.TextBox> by displaying an explanatory background image inside of the <xref:System.Windows.Controls.TextBox> until the user inputs text, at which point the image is removed.</span></span> <span data-ttu-id="001f8-104">此外，如果用户删除了其输入，则会再次还原背景图像。</span><span class="sxs-lookup"><span data-stu-id="001f8-104">In addition, the background image is restored again if the user removes their input.</span></span> <span data-ttu-id="001f8-105">请参阅下图。</span><span class="sxs-lookup"><span data-stu-id="001f8-105">See illustration below.</span></span>  
  
 <span data-ttu-id="001f8-106">![具有背景图像的 TextBox](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span><span class="sxs-lookup"><span data-stu-id="001f8-106">![A TextBox with a background image](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="001f8-107">在此示例中使用背景图像而不是只是操作的 <xref:System.Windows.Controls.TextBox.Text%2A> 属性，这 <xref:System.Windows.Controls.TextBox> 是因为背景图像不会干扰数据绑定。</span><span class="sxs-lookup"><span data-stu-id="001f8-107">The reason a background image is used in this example rather then simply manipulating the <xref:System.Windows.Controls.TextBox.Text%2A> property of <xref:System.Windows.Controls.TextBox>, is that a background image will not interfere with data binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="001f8-108">示例</span><span class="sxs-lookup"><span data-stu-id="001f8-108">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="001f8-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="001f8-109">See also</span></span>

- [<span data-ttu-id="001f8-110">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="001f8-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="001f8-111">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="001f8-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
