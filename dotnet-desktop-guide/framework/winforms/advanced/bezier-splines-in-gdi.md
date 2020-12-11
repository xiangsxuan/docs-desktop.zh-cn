---
title: B&#233;GDI + 中的 zier 样条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
ms.openlocfilehash: ff4e9eb18610b70c88e057d3d44020321bbb9f4f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970366"
---
# <a name="b233zier-splines-in-gdi"></a><span data-ttu-id="22061-102">B&#233;GDI + 中的 zier 样条</span><span class="sxs-lookup"><span data-stu-id="22061-102">B&#233;zier Splines in GDI+</span></span>
<span data-ttu-id="22061-103">贝塞尔样条是由四个点指定的曲线：两个端点 (p1 和 p2) ，两个控制点 (C1 和 c2) 。</span><span class="sxs-lookup"><span data-stu-id="22061-103">A Bézier spline is a curve specified by four points: two end points (p1 and p2) and two control points (c1 and c2).</span></span> <span data-ttu-id="22061-104">曲线从 p1 开始，到 p2 结束。</span><span class="sxs-lookup"><span data-stu-id="22061-104">The curve begins at p1 and ends at p2.</span></span> <span data-ttu-id="22061-105">曲线不通过控制点，但控制点作为磁体，在某些方向上拉动曲线并影响曲线弯曲的方式。</span><span class="sxs-lookup"><span data-stu-id="22061-105">The curve does not pass through the control points, but the control points act as magnets, pulling the curve in certain directions and influencing the way the curve bends.</span></span> <span data-ttu-id="22061-106">下图显示了一条贝塞尔曲线及其终结点和控制点。</span><span class="sxs-lookup"><span data-stu-id="22061-106">The following illustration shows a Bézier curve along with its endpoints and control points.</span></span>  
  
 <span data-ttu-id="22061-107">![贝塞尔曲线](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span><span class="sxs-lookup"><span data-stu-id="22061-107">![Bezier Splines](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span></span>  
  
 <span data-ttu-id="22061-108">曲线从 p1 开始向控制点 c1 方向移动。</span><span class="sxs-lookup"><span data-stu-id="22061-108">The curve starts at p1 and moves toward the control point c1.</span></span> <span data-ttu-id="22061-109">P1 上曲线的切线是从 p1 绘制到 c1 的直线。</span><span class="sxs-lookup"><span data-stu-id="22061-109">The tangent line to the curve at p1 is the line drawn from p1 to c1.</span></span> <span data-ttu-id="22061-110">终结点 p2 处的切线是从 c2 到 p2 的直线。</span><span class="sxs-lookup"><span data-stu-id="22061-110">The tangent line at the endpoint p2 is the line drawn from c2 to p2.</span></span>  
  
## <a name="drawing-bzier-splines"></a><span data-ttu-id="22061-111">绘制贝塞尔样条</span><span class="sxs-lookup"><span data-stu-id="22061-111">Drawing Bézier Splines</span></span>  
 <span data-ttu-id="22061-112">若要绘制贝塞尔曲线，需要 <xref:System.Drawing.Graphics> 类和的实例 <xref:System.Drawing.Pen> 。</span><span class="sxs-lookup"><span data-stu-id="22061-112">To draw a Bézier spline, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Pen>.</span></span> <span data-ttu-id="22061-113">类的实例 <xref:System.Drawing.Graphics> 提供 <xref:System.Drawing.Graphics.DrawBezier%2A> 方法，并 <xref:System.Drawing.Pen> 存储用于呈现曲线的线条的属性，例如宽度和颜色。</span><span class="sxs-lookup"><span data-stu-id="22061-113">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawBezier%2A> method, and the <xref:System.Drawing.Pen> stores attributes, such as width and color, of the line used to render the curve.</span></span> <span data-ttu-id="22061-114"><xref:System.Drawing.Pen>作为参数之一传递给 <xref:System.Drawing.Graphics.DrawBezier%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="22061-114">The <xref:System.Drawing.Pen> is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawBezier%2A> method.</span></span> <span data-ttu-id="22061-115">传递给方法的其余参数 <xref:System.Drawing.Graphics.DrawBezier%2A> 是终结点和控制点。</span><span class="sxs-lookup"><span data-stu-id="22061-115">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawBezier%2A> method are the endpoints and the control points.</span></span> <span data-ttu-id="22061-116">下面的示例使用起点 (0，0) ，控制点 (40，20) ， (80、150) 和结束点 (100，10) 绘制贝塞尔样条：</span><span class="sxs-lookup"><span data-stu-id="22061-116">The following example draws a Bézier spline with starting point (0, 0), control points (40, 20) and (80, 150), and ending point (100, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#71](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 <span data-ttu-id="22061-117">下图显示了曲线、控制点和两条切线。</span><span class="sxs-lookup"><span data-stu-id="22061-117">The following illustration shows the curve, the control points, and two tangent lines.</span></span>  
  
 <span data-ttu-id="22061-118">![贝塞尔曲线](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span><span class="sxs-lookup"><span data-stu-id="22061-118">![Bezier Splines](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span></span>  
  
 <span data-ttu-id="22061-119">贝塞尔样条最初由圣皮埃尔 Bezier 开发，以实现汽车行业的设计。</span><span class="sxs-lookup"><span data-stu-id="22061-119">Bézier splines were originally developed by Pierre Bézier for design in the automotive industry.</span></span> <span data-ttu-id="22061-120">由于它们已经过验证，可在多种类型的计算机辅助设计中使用，并且还用于定义字体的轮廓。</span><span class="sxs-lookup"><span data-stu-id="22061-120">They have since proven to be useful in many types of computer-aided design and are also used to define the outlines of fonts.</span></span> <span data-ttu-id="22061-121">贝塞尔样条可以产生各种形状，下图显示了其中的一部分。</span><span class="sxs-lookup"><span data-stu-id="22061-121">Bézier splines can yield a wide variety of shapes, some of which are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="22061-122">![路径](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span><span class="sxs-lookup"><span data-stu-id="22061-122">![Paths](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22061-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22061-123">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="22061-124">直线、曲线和图形</span><span class="sxs-lookup"><span data-stu-id="22061-124">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="22061-125">构造并绘制曲线</span><span class="sxs-lookup"><span data-stu-id="22061-125">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
- [<span data-ttu-id="22061-126">如何：创建用于绘制的 Graphics 对象</span><span class="sxs-lookup"><span data-stu-id="22061-126">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="22061-127">如何：创建钢笔</span><span class="sxs-lookup"><span data-stu-id="22061-127">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
