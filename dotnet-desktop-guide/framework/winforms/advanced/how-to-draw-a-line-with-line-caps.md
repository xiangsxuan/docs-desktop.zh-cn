---
title: 如何：绘制具有线帽的线条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
ms.openlocfilehash: 34abfc86e980a24ebb835cfd88d2522f8372c68d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971482"
---
# <a name="how-to-draw-a-line-with-line-caps"></a><span data-ttu-id="7f80d-102">如何：绘制具有线帽的线条</span><span class="sxs-lookup"><span data-stu-id="7f80d-102">How to: Draw a Line with Line Caps</span></span>
<span data-ttu-id="7f80d-103">您可以在多个名为 "线帽" 的形状之一中绘制线条的开头或结尾。</span><span class="sxs-lookup"><span data-stu-id="7f80d-103">You can draw the start or end of a line in one of several shapes called line caps.</span></span> <span data-ttu-id="7f80d-104">GDI + 支持多个行帽，如圆形、方形、菱形和箭头。</span><span class="sxs-lookup"><span data-stu-id="7f80d-104">GDI+ supports several line caps, such as round, square, diamond, and arrowhead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f80d-105">示例</span><span class="sxs-lookup"><span data-stu-id="7f80d-105">Example</span></span>  
 <span data-ttu-id="7f80d-106">您可以指定线帽 (开始端) 、行尾 (端) ，或是虚线 (虚线帽) 的短划线。</span><span class="sxs-lookup"><span data-stu-id="7f80d-106">You can specify line caps for the start of a line (start cap), the end of a line (end cap), or the dashes of a dashed line (dash cap).</span></span>  
  
 <span data-ttu-id="7f80d-107">下面的示例在一端绘制一个箭头，并在另一端绘制一个圆角端。</span><span class="sxs-lookup"><span data-stu-id="7f80d-107">The following example draws a line with an arrowhead at one end and a round cap at the other end.</span></span> <span data-ttu-id="7f80d-108">下图显示了生成的行：</span><span class="sxs-lookup"><span data-stu-id="7f80d-108">The illustration shows the resulting line:</span></span>  
  
 ![显示带有圆角帽的线条的插图。](./media/how-to-draw-a-line-with-line-caps/line-cap-arrowhead-example.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7f80d-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="7f80d-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="7f80d-111">创建 Windows 窗体并处理窗体的 <xref:System.Windows.Forms.Control.Paint> 事件。</span><span class="sxs-lookup"><span data-stu-id="7f80d-111">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="7f80d-112">将示例代码粘贴到 <xref:System.Windows.Forms.Control.Paint> 作为传递的事件处理程序中 `e` <xref:System.Windows.Forms.PaintEventArgs> 。</span><span class="sxs-lookup"><span data-stu-id="7f80d-112">Paste the example code into the <xref:System.Windows.Forms.Control.Paint> event handler passing `e` as <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f80d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f80d-113">See also</span></span>

- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>
- [<span data-ttu-id="7f80d-114">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="7f80d-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="7f80d-115">使用笔绘制线条和形状</span><span class="sxs-lookup"><span data-stu-id="7f80d-115">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
