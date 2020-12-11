---
title: 如何：绘制轮廓形状
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.DrawEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- drawing [Windows Forms], shapes
- circular shapes
- forms [Windows Forms], drawing circular shapes
- circles
- outlined shapes [Windows Forms], examples
- outlined shapes [Windows Forms], drawing
- drawing [Windows Forms], circular shapes
- shapes [Windows Forms], drawing
ms.assetid: f4f9214c-607e-407d-8cdd-6549f0278451
ms.openlocfilehash: 019bbc19cc4b26c42f8539eccd93ec4ff87fab12
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971473"
---
# <a name="how-to-draw-an-outlined-shape"></a><span data-ttu-id="e3229-102">如何：绘制轮廓形状</span><span class="sxs-lookup"><span data-stu-id="e3229-102">How to: Draw an Outlined Shape</span></span>
<span data-ttu-id="e3229-103">此示例在窗体上绘制空心椭圆和矩形。</span><span class="sxs-lookup"><span data-stu-id="e3229-103">This example draws outlined ellipses and rectangles on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3229-104">示例</span><span class="sxs-lookup"><span data-stu-id="e3229-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#6)]
 [!code-csharp[System.Drawing.ConceptualHowTos#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#6)]
 [!code-vb[System.Drawing.ConceptualHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e3229-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="e3229-105">Compiling the Code</span></span>  
 <span data-ttu-id="e3229-106">不能在事件处理程序中调用此方法 <xref:System.Windows.Forms.Form.Load> 。</span><span class="sxs-lookup"><span data-stu-id="e3229-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="e3229-107">如果窗体调整或被其他窗体遮住，则不会重新绘制所绘制的内容。</span><span class="sxs-lookup"><span data-stu-id="e3229-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="e3229-108">若要自动重绘内容，应重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="e3229-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e3229-109">可靠编程</span><span class="sxs-lookup"><span data-stu-id="e3229-109">Robust Programming</span></span>  
 <span data-ttu-id="e3229-110">应始终对 <xref:System.IDisposable.Dispose%2A> 使用系统资源的任何对象（如 <xref:System.Drawing.Pen> 和对象）调用 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="e3229-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3229-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3229-111">See also</span></span>

- <xref:System.Drawing.Graphics.DrawEllipse%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Drawing.Graphics.DrawRectangle%2A>
- [<span data-ttu-id="e3229-112">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="e3229-112">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="e3229-113">使用笔绘制线条和形状</span><span class="sxs-lookup"><span data-stu-id="e3229-113">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="e3229-114">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="e3229-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
