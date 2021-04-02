---
title: 如何：将文本绘制到控件的背景上
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: 14300f763b67c6ac67ee408de2009c328d499c13
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970090"
---
# <a name="how-to-draw-text-to-a-controls-background"></a><span data-ttu-id="8fc5f-102">如何：将文本绘制到控件的背景上</span><span class="sxs-lookup"><span data-stu-id="8fc5f-102">How to: Draw Text to a Control's Background</span></span>
<span data-ttu-id="8fc5f-103">您可以通过将文本字符串转换为 <xref:System.Windows.Media.FormattedText> 对象，然后将该对象绘制到控件的，来直接将文本绘制到控件的背景中 <xref:System.Windows.Media.DrawingContext> 。</span><span class="sxs-lookup"><span data-stu-id="8fc5f-103">You can draw text directly to the background of a control by converting a text string to a <xref:System.Windows.Media.FormattedText> object, and then drawing the object to the control's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="8fc5f-104">你还可以使用此方法来绘制到派生自的对象的背景 <xref:System.Windows.Controls.Panel> ，例如 <xref:System.Windows.Controls.Canvas> 和 <xref:System.Windows.Controls.StackPanel> 。</span><span class="sxs-lookup"><span data-stu-id="8fc5f-104">You can also use this technique for drawing to the background of objects derived from <xref:System.Windows.Controls.Panel>, such as <xref:System.Windows.Controls.Canvas> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 <span data-ttu-id="8fc5f-105">![以背景形式显示文本的控件的屏幕截图。](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")</span><span class="sxs-lookup"><span data-stu-id="8fc5f-105">![Screenshot of controls displaying text as background.](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")</span></span>  
<span data-ttu-id="8fc5f-106">具有自定义文本背景的控件的示例</span><span class="sxs-lookup"><span data-stu-id="8fc5f-106">Example of controls with custom text backgrounds</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fc5f-107">示例</span><span class="sxs-lookup"><span data-stu-id="8fc5f-107">Example</span></span>  
 <span data-ttu-id="8fc5f-108">若要在控件的背景上绘制，请创建新的 <xref:System.Windows.Media.DrawingBrush> 对象，并将转换后的文本绘制到对象的 <xref:System.Windows.Media.DrawingContext> 。</span><span class="sxs-lookup"><span data-stu-id="8fc5f-108">To draw to the background of a control, create a new <xref:System.Windows.Media.DrawingBrush> object and draw the converted text to the object's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="8fc5f-109">然后，将新的分配 <xref:System.Windows.Media.DrawingBrush> 给控件的背景属性。</span><span class="sxs-lookup"><span data-stu-id="8fc5f-109">Then, assign the new <xref:System.Windows.Media.DrawingBrush> to the control's background property.</span></span>  
  
 <span data-ttu-id="8fc5f-110">下面的代码示例演示如何创建 <xref:System.Windows.Media.FormattedText> 对象并将其绘制到和对象的背景 <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.Button> 。</span><span class="sxs-lookup"><span data-stu-id="8fc5f-110">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and draw to the background of a <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Button> object.</span></span>  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a><span data-ttu-id="8fc5f-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8fc5f-111">See also</span></span>

- <xref:System.Windows.Media.FormattedText>
- [<span data-ttu-id="8fc5f-112">绘制格式化文本</span><span class="sxs-lookup"><span data-stu-id="8fc5f-112">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
