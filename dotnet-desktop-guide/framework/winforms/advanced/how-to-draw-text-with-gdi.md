---
title: 如何：用 GDI 绘制文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
ms.openlocfilehash: 3ed2b5c94e4a38a5873a34e61287c4038cab5cbb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971460"
---
# <a name="how-to-draw-text-with-gdi"></a><span data-ttu-id="47c53-102">如何：用 GDI 绘制文本</span><span class="sxs-lookup"><span data-stu-id="47c53-102">How to: Draw Text with GDI</span></span>
<span data-ttu-id="47c53-103">使用 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 类中的方法 <xref:System.Windows.Forms.TextRenderer> ，可以访问用于在窗体或控件上绘制文本的 GDI 功能。</span><span class="sxs-lookup"><span data-stu-id="47c53-103">With the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method in the <xref:System.Windows.Forms.TextRenderer> class, you can access GDI functionality for drawing text on a form or control.</span></span> <span data-ttu-id="47c53-104">GDI 文本呈现通常提供比 GDI + 更好的性能和更准确的文本度量。</span><span class="sxs-lookup"><span data-stu-id="47c53-104">GDI text rendering typically offers better performance and more accurate text measuring than GDI+.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="47c53-105"><xref:System.Windows.Forms.TextRenderer.DrawText%2A>类的方法 <xref:System.Windows.Forms.TextRenderer> 不支持打印。</span><span class="sxs-lookup"><span data-stu-id="47c53-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of the <xref:System.Windows.Forms.TextRenderer> class are not supported for printing.</span></span> <span data-ttu-id="47c53-106">打印时，请始终使用 <xref:System.Drawing.Graphics.DrawString%2A> 类的方法 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="47c53-106">When printing, always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47c53-107">示例</span><span class="sxs-lookup"><span data-stu-id="47c53-107">Example</span></span>  
 <span data-ttu-id="47c53-108">下面的代码示例演示如何使用方法在一个矩形内的多行上绘制文本 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 。</span><span class="sxs-lookup"><span data-stu-id="47c53-108">The following code example demonstrates how to draw text on multiple lines within a rectangle using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 <span data-ttu-id="47c53-109">若要使用类呈现文本 <xref:System.Windows.Forms.TextRenderer> ，需要一个 <xref:System.Drawing.IDeviceContext> ，如 <xref:System.Drawing.Graphics> 和 <xref:System.Drawing.Font> ，一个用于绘制文本的位置以及应在其中绘制文本的颜色。</span><span class="sxs-lookup"><span data-stu-id="47c53-109">To render text with the <xref:System.Windows.Forms.TextRenderer> class, you need an <xref:System.Drawing.IDeviceContext>, such as a <xref:System.Drawing.Graphics> and a <xref:System.Drawing.Font>, a location to draw the text, and the color in which it should be drawn.</span></span> <span data-ttu-id="47c53-110">（可选）可以使用枚举指定文本格式 <xref:System.Windows.Forms.TextFormatFlags> 。</span><span class="sxs-lookup"><span data-stu-id="47c53-110">Optionally, you can specify the text formatting by using the <xref:System.Windows.Forms.TextFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="47c53-111">有关获取的详细信息 <xref:System.Drawing.Graphics> ，请参阅 [如何：为绘图创建图形对象](how-to-create-graphics-objects-for-drawing.md)。</span><span class="sxs-lookup"><span data-stu-id="47c53-111">For more information about obtaining a <xref:System.Drawing.Graphics>, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="47c53-112">有关构造的详细信息 <xref:System.Drawing.Font> ，请参阅 [如何：构造字体系列和字体](how-to-construct-font-families-and-fonts.md)。</span><span class="sxs-lookup"><span data-stu-id="47c53-112">For more information about constructing a <xref:System.Drawing.Font>, see [How to: Construct Font Families and Fonts](how-to-construct-font-families-and-fonts.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="47c53-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="47c53-113">Compiling the Code</span></span>  
 <span data-ttu-id="47c53-114">前面的代码示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` （参数） <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="47c53-114">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47c53-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47c53-115">See also</span></span>

- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- [<span data-ttu-id="47c53-116">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="47c53-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
