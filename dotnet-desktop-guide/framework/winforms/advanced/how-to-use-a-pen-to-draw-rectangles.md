---
title: 如何：使用钢笔绘制矩形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
ms.openlocfilehash: cd5d965f8b92d15cdeb3049330d9b3cc0de893b2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971391"
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a><span data-ttu-id="269b6-102">如何：使用钢笔绘制矩形</span><span class="sxs-lookup"><span data-stu-id="269b6-102">How to: Use a Pen to Draw Rectangles</span></span>
<span data-ttu-id="269b6-103">若要绘制矩形，需要 <xref:System.Drawing.Graphics> 对象和 <xref:System.Drawing.Pen> 对象。</span><span class="sxs-lookup"><span data-stu-id="269b6-103">To draw rectangles, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="269b6-104"><xref:System.Drawing.Graphics>对象提供 <xref:System.Drawing.Graphics.DrawRectangle%2A> 方法，而 <xref:System.Drawing.Pen> 对象存储行的功能，如颜色和宽度。</span><span class="sxs-lookup"><span data-stu-id="269b6-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="269b6-105">示例</span><span class="sxs-lookup"><span data-stu-id="269b6-105">Example</span></span>  
 <span data-ttu-id="269b6-106">下面的示例在 (10，10) 绘制其左上角的矩形。</span><span class="sxs-lookup"><span data-stu-id="269b6-106">The following example draws a rectangle with its upper-left corner at (10, 10).</span></span> <span data-ttu-id="269b6-107">矩形的宽度为100，高度为50。</span><span class="sxs-lookup"><span data-stu-id="269b6-107">The rectangle has a width of 100 and a height of 50.</span></span> <span data-ttu-id="269b6-108">传递给构造函数的第二个参数 <xref:System.Drawing.Pen.%23ctor%2A> 指示钢笔宽度为5像素。</span><span class="sxs-lookup"><span data-stu-id="269b6-108">The second argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor indicates that the pen width is 5 pixels.</span></span>  
  
 <span data-ttu-id="269b6-109">绘制矩形时，笔位于矩形边界上。</span><span class="sxs-lookup"><span data-stu-id="269b6-109">When the rectangle is drawn, the pen is centered on the rectangle's boundary.</span></span> <span data-ttu-id="269b6-110">由于笔宽度为5，矩形的边将绘制5个像素宽，这样，在边界本身绘制1个像素，在内部绘制2个像素，在外部绘制2个像素。</span><span class="sxs-lookup"><span data-stu-id="269b6-110">Because the pen width is 5, the sides of the rectangle are drawn 5 pixels wide, such that 1 pixel is drawn on the boundary itself, 2 pixels are drawn on the inside, and 2 pixels are drawn on the outside.</span></span> <span data-ttu-id="269b6-111">有关笔对齐的详细信息，请参阅 [如何：设置笔宽度和对齐方式](how-to-set-pen-width-and-alignment.md)。</span><span class="sxs-lookup"><span data-stu-id="269b6-111">For more details on pen alignment, see [How to: Set Pen Width and Alignment](how-to-set-pen-width-and-alignment.md).</span></span>  
  
 <span data-ttu-id="269b6-112">下图显示了生成的矩形。</span><span class="sxs-lookup"><span data-stu-id="269b6-112">The following illustration shows the resulting rectangle.</span></span> <span data-ttu-id="269b6-113">虚线显示画笔的宽度为1个像素时应绘制的矩形的位置。</span><span class="sxs-lookup"><span data-stu-id="269b6-113">The dotted lines show where the rectangle would have been drawn if the pen width had been one pixel.</span></span> <span data-ttu-id="269b6-114">矩形左上角的放大视图显示黑色黑色线条在这些点线上居中。</span><span class="sxs-lookup"><span data-stu-id="269b6-114">The enlarged view of the upper-left corner of the rectangle shows that the thick black lines are centered on those dotted lines.</span></span>  
  
 ![显示带有黑色和虚线的绘制矩形的屏幕截图。](./media/how-to-use-a-pen-to-draw-rectangles/drawn-rectangle-black-lines-dotted-lines.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="269b6-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="269b6-116">Compiling the Code</span></span>  
 <span data-ttu-id="269b6-117">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="269b6-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="269b6-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="269b6-118">See also</span></span>

- [<span data-ttu-id="269b6-119">使用笔绘制线条和形状</span><span class="sxs-lookup"><span data-stu-id="269b6-119">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
