---
title: 如何：绘制 B&#233;zier 样条的序列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
ms.openlocfilehash: 976787f5830282a581d05a9c24d1f83dceca4b25
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971478"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a><span data-ttu-id="50f53-102">如何：绘制 B&#233;zier 样条的序列</span><span class="sxs-lookup"><span data-stu-id="50f53-102">How to: Draw a Sequence of B&#233;zier Splines</span></span>
<span data-ttu-id="50f53-103">您可以使用 <xref:System.Drawing.Graphics.DrawBeziers%2A> 类的方法 <xref:System.Drawing.Graphics> 来绘制一系列已连接的贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="50f53-103">You can use the <xref:System.Drawing.Graphics.DrawBeziers%2A> method of the <xref:System.Drawing.Graphics> class to draw a sequence of connected Bézier splines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50f53-104">示例</span><span class="sxs-lookup"><span data-stu-id="50f53-104">Example</span></span>  
 <span data-ttu-id="50f53-105">下面的示例绘制一个曲线，其中包含两个连接的贝塞尔样条。</span><span class="sxs-lookup"><span data-stu-id="50f53-105">The following example draws a curve that consists of two connected Bézier splines.</span></span> <span data-ttu-id="50f53-106">第一条贝塞尔曲线的端点是第二条贝塞尔曲线的起点。</span><span class="sxs-lookup"><span data-stu-id="50f53-106">The endpoint of the first Bézier spline is the start point of the second Bézier spline.</span></span>  
  
 <span data-ttu-id="50f53-107">下图显示了已连接的曲线以及七个点：</span><span class="sxs-lookup"><span data-stu-id="50f53-107">The following illustration shows the connected splines along with the seven points:</span></span>  
  
 ![显示连接的曲线以及七个点的图形。](./media/how-to-draw-a-sequence-of-bezier-splines/bezier-spline-seven-points.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="50f53-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="50f53-109">Compiling the Code</span></span>  
 <span data-ttu-id="50f53-110">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="50f53-110">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50f53-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50f53-111">See also</span></span>

- [<span data-ttu-id="50f53-112">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="50f53-112">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="50f53-113">GDI+ 中的贝塞尔自由绘制曲线</span><span class="sxs-lookup"><span data-stu-id="50f53-113">Bézier Splines in GDI+</span></span>](bezier-splines-in-gdi.md)
- [<span data-ttu-id="50f53-114">构造并绘制曲线</span><span class="sxs-lookup"><span data-stu-id="50f53-114">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
