---
title: 如何：在指定位置绘制文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text at a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
ms.openlocfilehash: 0c36b00e4f6f71f0ecf8042853bb8e99e57854da
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971463"
---
# <a name="how-to-draw-text-at-a-specified-location"></a><span data-ttu-id="8d96a-102">如何：在指定位置绘制文本</span><span class="sxs-lookup"><span data-stu-id="8d96a-102">How to: Draw Text at a Specified Location</span></span>
<span data-ttu-id="8d96a-103">执行自定义绘制时，可以在从指定点开始的单个水平行中绘制文本。</span><span class="sxs-lookup"><span data-stu-id="8d96a-103">When you perform custom drawing, you can draw text in a single horizontal line starting at a specified point.</span></span> <span data-ttu-id="8d96a-104">您可以使用 <xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Drawing.Graphics> 采用或参数的类的重载方法，以这种方式绘制文本 <xref:System.Drawing.Point> <xref:System.Drawing.PointF> 。</span><span class="sxs-lookup"><span data-stu-id="8d96a-104">You can draw text in this manner by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Point> or <xref:System.Drawing.PointF> parameter.</span></span> <span data-ttu-id="8d96a-105"><xref:System.Drawing.Graphics.DrawString%2A>方法还需要 <xref:System.Drawing.Brush> 和<xref:System.Drawing.Font></span><span class="sxs-lookup"><span data-stu-id="8d96a-105">The <xref:System.Drawing.Graphics.DrawString%2A> method also requires a <xref:System.Drawing.Brush> and <xref:System.Drawing.Font></span></span>  
  
 <span data-ttu-id="8d96a-106">你还可以使用的 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 重载方法，该方法 <xref:System.Windows.Forms.TextRenderer> 采用 <xref:System.Drawing.Point> 。</span><span class="sxs-lookup"><span data-stu-id="8d96a-106">You can also use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Point>.</span></span> <span data-ttu-id="8d96a-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> 还需要 <xref:System.Drawing.Color> 和 <xref:System.Drawing.Font> 。</span><span class="sxs-lookup"><span data-stu-id="8d96a-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> also requires a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="8d96a-108">下图显示使用重载方法时在指定点绘制的文本的输出 <xref:System.Drawing.Graphics.DrawString%2A> 。</span><span class="sxs-lookup"><span data-stu-id="8d96a-108">The following illustration shows the output of text drawn at a specified point when you use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method.</span></span>  
  
 ![显示指定点文本输出的屏幕截图。](./media/how-to-draw-text-at-a-specified-location/font-text-specified-point.png)  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="8d96a-110">使用 GDI + 绘制文本行</span><span class="sxs-lookup"><span data-stu-id="8d96a-110">To draw a line of text with GDI+</span></span>  
  
1. <span data-ttu-id="8d96a-111">使用 <xref:System.Drawing.Graphics.DrawString%2A> 方法，传递所需的文本、、 <xref:System.Drawing.Point> 、 <xref:System.Drawing.PointF> <xref:System.Drawing.Font> 和 <xref:System.Drawing.Brush> 。</span><span class="sxs-lookup"><span data-stu-id="8d96a-111">Use the <xref:System.Drawing.Graphics.DrawString%2A> method, passing the text you want, <xref:System.Drawing.Point> or <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="8d96a-112">使用 GDI 绘制一行文本</span><span class="sxs-lookup"><span data-stu-id="8d96a-112">To draw a line of text with GDI</span></span>  
  
1. <span data-ttu-id="8d96a-113">使用 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 方法，传递所需的文本、、 <xref:System.Drawing.Point> <xref:System.Drawing.Font> 和 <xref:System.Drawing.Color> 。</span><span class="sxs-lookup"><span data-stu-id="8d96a-113">Use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method, passing the text you want, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8d96a-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="8d96a-114">Compiling the Code</span></span>  
 <span data-ttu-id="8d96a-115">前面的示例需要：</span><span class="sxs-lookup"><span data-stu-id="8d96a-115">The previous examples require:</span></span>  
  
- <span data-ttu-id="8d96a-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`，它是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="8d96a-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d96a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d96a-117">See also</span></span>

- [<span data-ttu-id="8d96a-118">如何：用 GDI 绘制文本</span><span class="sxs-lookup"><span data-stu-id="8d96a-118">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="8d96a-119">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="8d96a-119">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="8d96a-120">如何：构造字体系列和字体</span><span class="sxs-lookup"><span data-stu-id="8d96a-120">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
- [<span data-ttu-id="8d96a-121">如何：在矩形中绘制换行文本</span><span class="sxs-lookup"><span data-stu-id="8d96a-121">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)
