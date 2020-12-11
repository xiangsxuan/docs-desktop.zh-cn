---
title: 如何：绘制单个 B&#233;zier 样条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: ebb53e7df979a553ed4a44deba34345c9ecac772
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971477"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="a9a4b-102">如何：绘制单个 B&#233;zier 样条</span><span class="sxs-lookup"><span data-stu-id="a9a4b-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="a9a4b-103">贝塞尔样条由四个点定义：一个开始点、两个控制点和一个终结点。</span><span class="sxs-lookup"><span data-stu-id="a9a4b-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9a4b-104">示例</span><span class="sxs-lookup"><span data-stu-id="a9a4b-104">Example</span></span>  
 <span data-ttu-id="a9a4b-105">下面的示例使用开始点 (10、100) 和终结点 (200，100) 绘制贝塞尔样条。</span><span class="sxs-lookup"><span data-stu-id="a9a4b-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="a9a4b-106">控制点为 (100、10)  (150、150) 。</span><span class="sxs-lookup"><span data-stu-id="a9a4b-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="a9a4b-107">下图显示了生成的贝塞尔曲线及其起点、控制点和端点。</span><span class="sxs-lookup"><span data-stu-id="a9a4b-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="a9a4b-108">该图还显示样条的凸球面，这是通过将四个点与直线连接而形成的多边形。</span><span class="sxs-lookup"><span data-stu-id="a9a4b-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 ![贝塞尔曲线的插图。](./media/how-to-draw-a-single-bezier-spline/bezier-spline-illustration.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a9a4b-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="a9a4b-110">Compiling the Code</span></span>  
 <span data-ttu-id="a9a4b-111">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="a9a4b-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9a4b-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9a4b-112">See also</span></span>

- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [<span data-ttu-id="a9a4b-113">GDI+ 中的贝塞尔自由绘制曲线</span><span class="sxs-lookup"><span data-stu-id="a9a4b-113">Bézier Splines in GDI+</span></span>](bezier-splines-in-gdi.md)
- [<span data-ttu-id="a9a4b-114">如何：绘制一系列贝塞尔自由绘制曲线</span><span class="sxs-lookup"><span data-stu-id="a9a4b-114">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)
