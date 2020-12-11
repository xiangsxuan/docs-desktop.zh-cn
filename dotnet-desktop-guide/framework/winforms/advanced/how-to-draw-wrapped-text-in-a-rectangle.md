---
title: 如何：在矩形中绘制换行文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: ace79e45737a3ce26d8bdcd603e923c1e6040d4d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971451"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a><span data-ttu-id="a037c-102">如何：在矩形中绘制换行文本</span><span class="sxs-lookup"><span data-stu-id="a037c-102">How to: Draw Wrapped Text in a Rectangle</span></span>
<span data-ttu-id="a037c-103">您可以使用 <xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Drawing.Graphics> 采用或参数的类的重载方法在矩形中绘制换行文本 <xref:System.Drawing.Rectangle> <xref:System.Drawing.RectangleF> 。</span><span class="sxs-lookup"><span data-stu-id="a037c-103">You can draw wrapped text in a rectangle by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF> parameter.</span></span> <span data-ttu-id="a037c-104">你还将使用 <xref:System.Drawing.Brush> 和 <xref:System.Drawing.Font> 。</span><span class="sxs-lookup"><span data-stu-id="a037c-104">You will also use a <xref:System.Drawing.Brush> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="a037c-105">你还可以使用 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> <xref:System.Windows.Forms.TextRenderer> 采用和参数的的重载方法在矩形中绘制换行文本 <xref:System.Drawing.Rectangle> <xref:System.Windows.Forms.TextFormatFlags> 。</span><span class="sxs-lookup"><span data-stu-id="a037c-105">You can also draw wrapped text in a rectangle by using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Rectangle> and a <xref:System.Windows.Forms.TextFormatFlags> parameter.</span></span> <span data-ttu-id="a037c-106">你还将使用 <xref:System.Drawing.Color> 和 <xref:System.Drawing.Font> 。</span><span class="sxs-lookup"><span data-stu-id="a037c-106">You will also use a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="a037c-107">下图显示使用方法时在矩形中绘制的文本的输出 <xref:System.Drawing.Graphics.DrawString%2A> ：</span><span class="sxs-lookup"><span data-stu-id="a037c-107">The following illustration shows the output of text drawn in the rectangle when you use the <xref:System.Drawing.Graphics.DrawString%2A> method:</span></span>
  
 ![使用 System.drawing.graphics.drawstring 方法时显示输出的屏幕截图。](./media/how-to-draw-wrapped-text-in-a-rectangle/drawstring-method-font-text.png)  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="a037c-109">使用 GDI + 在矩形中绘制换行文本</span><span class="sxs-lookup"><span data-stu-id="a037c-109">To draw wrapped text in a rectangle with GDI+</span></span>  
  
1. <span data-ttu-id="a037c-110">使用 <xref:System.Drawing.Graphics.DrawString%2A> 重载的方法，传递所需的文本、 <xref:System.Drawing.Rectangle> 或 <xref:System.Drawing.RectangleF> <xref:System.Drawing.Font> <xref:System.Drawing.Brush> 。</span><span class="sxs-lookup"><span data-stu-id="a037c-110">Use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="a037c-111">使用 GDI 在矩形中绘制换行文本</span><span class="sxs-lookup"><span data-stu-id="a037c-111">To draw wrapped text in a rectangle with GDI</span></span>  
  
1. <span data-ttu-id="a037c-112">使用 <xref:System.Windows.Forms.TextFormatFlags> 枚举值指定应使用 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 重载方法包装文本，传递所需的文本、 <xref:System.Drawing.Rectangle> <xref:System.Drawing.Font> 和 <xref:System.Drawing.Color> 。</span><span class="sxs-lookup"><span data-stu-id="a037c-112">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration value to specify the text should be wrapped with the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a037c-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="a037c-113">Compiling the Code</span></span>  
 <span data-ttu-id="a037c-114">前面的示例需要：</span><span class="sxs-lookup"><span data-stu-id="a037c-114">The previous examples require:</span></span>  
  
- <span data-ttu-id="a037c-115"><xref:System.Windows.Forms.PaintEventArgs>`e`，它是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="a037c-115"><xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a037c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a037c-116">See also</span></span>

- [<span data-ttu-id="a037c-117">如何：用 GDI 绘制文本</span><span class="sxs-lookup"><span data-stu-id="a037c-117">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="a037c-118">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="a037c-118">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="a037c-119">如何：构造字体系列和字体</span><span class="sxs-lookup"><span data-stu-id="a037c-119">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
- [<span data-ttu-id="a037c-120">如何：在指定位置绘制文本</span><span class="sxs-lookup"><span data-stu-id="a037c-120">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)
