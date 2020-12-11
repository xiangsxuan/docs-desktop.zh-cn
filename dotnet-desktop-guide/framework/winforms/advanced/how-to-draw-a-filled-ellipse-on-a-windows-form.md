---
title: 如何：在 Windows 窗体上绘制实心椭圆
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- circular shapes
- drawing [Windows Forms], ellipses
- shapes [Windows Forms], drawing
- forms [Windows Forms], drawing ellipses
ms.assetid: 781db806-950d-4c5b-b022-493f7fd0c4a8
ms.openlocfilehash: 2e7be3f2c4c710bb24568dd2e70f6f5cc4706c63
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970306"
---
# <a name="how-to-draw-a-filled-ellipse-on-a-windows-form"></a><span data-ttu-id="41490-102">如何：在 Windows 窗体上绘制实心椭圆</span><span class="sxs-lookup"><span data-stu-id="41490-102">How to: Draw a Filled Ellipse on a Windows Form</span></span>
<span data-ttu-id="41490-103">此示例在窗体上绘制实心椭圆。</span><span class="sxs-lookup"><span data-stu-id="41490-103">This example draws a filled ellipse on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41490-104">示例</span><span class="sxs-lookup"><span data-stu-id="41490-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="41490-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="41490-105">Compiling the Code</span></span>  
 <span data-ttu-id="41490-106">不能在事件处理程序中调用此方法 <xref:System.Windows.Forms.Form.Load> 。</span><span class="sxs-lookup"><span data-stu-id="41490-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="41490-107">如果窗体调整或被其他窗体遮住，则不会重新绘制所绘制的内容。</span><span class="sxs-lookup"><span data-stu-id="41490-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="41490-108">若要自动重绘内容，应重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="41490-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="41490-109">可靠编程</span><span class="sxs-lookup"><span data-stu-id="41490-109">Robust Programming</span></span>  
 <span data-ttu-id="41490-110">应始终对 <xref:System.IDisposable.Dispose%2A> 使用系统资源的任何对象（如 <xref:System.Drawing.Brush> 和对象）调用 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="41490-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41490-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41490-111">See also</span></span>

- [<span data-ttu-id="41490-112">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="41490-112">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="41490-113">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="41490-113">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="41490-114">Alpha 混合线条和填充</span><span class="sxs-lookup"><span data-stu-id="41490-114">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
- [<span data-ttu-id="41490-115">使用画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="41490-115">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
