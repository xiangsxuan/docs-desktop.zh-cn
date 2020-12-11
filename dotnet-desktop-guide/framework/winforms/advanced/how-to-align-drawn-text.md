---
title: 如何：对齐绘制的文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
ms.openlocfilehash: 3a569284a1c4b43fa7264e0354934436f95b8dc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970337"
---
# <a name="how-to-align-drawn-text"></a><span data-ttu-id="72ac7-102">如何：对齐绘制的文本</span><span class="sxs-lookup"><span data-stu-id="72ac7-102">How to: Align Drawn Text</span></span>
<span data-ttu-id="72ac7-103">执行自定义绘制时，可能经常需要在窗体或控件上居中绘制文本。</span><span class="sxs-lookup"><span data-stu-id="72ac7-103">When you perform custom drawing, you may often want to center drawn text on a form or control.</span></span> <span data-ttu-id="72ac7-104">您可以 <xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 通过创建正确的格式设置对象并设置相应的格式标志来轻松地对齐使用或方法绘制的文本。</span><span class="sxs-lookup"><span data-stu-id="72ac7-104">You can easily align text drawn with the <xref:System.Drawing.Graphics.DrawString%2A> or <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods by creating the correct formatting object and setting the appropriate format flags.</span></span>  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a><span data-ttu-id="72ac7-105">若要用 GDI + (System.drawing.graphics.drawstring 绘制居中文本) </span><span class="sxs-lookup"><span data-stu-id="72ac7-105">To draw centered text with GDI+ (DrawString)</span></span>  
  
1. <span data-ttu-id="72ac7-106">使用 <xref:System.Drawing.StringFormat> 带有相应方法的 <xref:System.Drawing.Graphics.DrawString%2A> 来指定居中文本。</span><span class="sxs-lookup"><span data-stu-id="72ac7-106">Use a <xref:System.Drawing.StringFormat> with the appropriate <xref:System.Drawing.Graphics.DrawString%2A> method to specify centered text.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a><span data-ttu-id="72ac7-107">用 GDI (DrawText 来绘制居中文本) </span><span class="sxs-lookup"><span data-stu-id="72ac7-107">To draw centered text with GDI (DrawText)</span></span>  
  
1. <span data-ttu-id="72ac7-108">使用 <xref:System.Windows.Forms.TextFormatFlags> 枚举进行包装，同时使用适当的方法垂直和水平居中文本 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 。</span><span class="sxs-lookup"><span data-stu-id="72ac7-108">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration for wrapping as well as vertically and horizontally centering text with the appropriate <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="72ac7-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="72ac7-109">Compiling the Code</span></span>  
 <span data-ttu-id="72ac7-110">前面的代码示例旨在与 Windows 窗体一起使用，并且它们需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，后者是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="72ac7-110">The preceding code examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72ac7-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72ac7-111">See also</span></span>

- [<span data-ttu-id="72ac7-112">如何：用 GDI 绘制文本</span><span class="sxs-lookup"><span data-stu-id="72ac7-112">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="72ac7-113">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="72ac7-113">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="72ac7-114">如何：构造字体系列和字体</span><span class="sxs-lookup"><span data-stu-id="72ac7-114">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
