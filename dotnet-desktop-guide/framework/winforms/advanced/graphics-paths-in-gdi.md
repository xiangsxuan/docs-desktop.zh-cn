---
title: GDI+ 中的图形路径
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
ms.openlocfilehash: 8e06032d145eb8c1aaf9bfcd1f205f8c6583634a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970341"
---
# <a name="graphics-paths-in-gdi"></a><span data-ttu-id="2a9da-102">GDI+ 中的图形路径</span><span class="sxs-lookup"><span data-stu-id="2a9da-102">Graphics Paths in GDI+</span></span>
<span data-ttu-id="2a9da-103">路径通过组合线条、矩形和简单曲线形成。</span><span class="sxs-lookup"><span data-stu-id="2a9da-103">Paths are formed by combining lines, rectangles, and simple curves.</span></span> <span data-ttu-id="2a9da-104">从 [矢量图形](vector-graphics-overview.md) 中回忆，以下基本构建基块已证明最适用于绘图图片：</span><span class="sxs-lookup"><span data-stu-id="2a9da-104">Recall from the [Vector Graphics Overview](vector-graphics-overview.md) that the following basic building blocks have proven to be the most useful for drawing pictures:</span></span>  
  
- <span data-ttu-id="2a9da-105">线条</span><span class="sxs-lookup"><span data-stu-id="2a9da-105">Lines</span></span>  
  
- <span data-ttu-id="2a9da-106">矩形</span><span class="sxs-lookup"><span data-stu-id="2a9da-106">Rectangles</span></span>  
  
- <span data-ttu-id="2a9da-107">椭圆</span><span class="sxs-lookup"><span data-stu-id="2a9da-107">Ellipses</span></span>  
  
- <span data-ttu-id="2a9da-108">形成</span><span class="sxs-lookup"><span data-stu-id="2a9da-108">Arcs</span></span>  
  
- <span data-ttu-id="2a9da-109">Polygon（多边形）</span><span class="sxs-lookup"><span data-stu-id="2a9da-109">Polygons</span></span>  
  
- <span data-ttu-id="2a9da-110">基数样条</span><span class="sxs-lookup"><span data-stu-id="2a9da-110">Cardinal splines</span></span>  
  
- <span data-ttu-id="2a9da-111">贝塞尔样条</span><span class="sxs-lookup"><span data-stu-id="2a9da-111">Bézier splines</span></span>  
  
 <span data-ttu-id="2a9da-112">在 GDI + 中， <xref:System.Drawing.Drawing2D.GraphicsPath> 对象允许您将这些构建基块的序列收集到一个单元中。</span><span class="sxs-lookup"><span data-stu-id="2a9da-112">In GDI+, the <xref:System.Drawing.Drawing2D.GraphicsPath> object allows you to collect a sequence of these building blocks into a single unit.</span></span> <span data-ttu-id="2a9da-113">然后，可以通过调用类的方法来绘制整个直线、矩形、多边形和曲线序列 <xref:System.Drawing.Graphics.DrawPath%2A> <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="2a9da-113">The entire sequence of lines, rectangles, polygons, and curves can then be drawn with one call to the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="2a9da-114">下图显示了通过组合直线、圆弧、贝塞尔曲线和基数样条创建的路径。</span><span class="sxs-lookup"><span data-stu-id="2a9da-114">The following illustration shows a path created by combining a line, an arc, a Bézier spline, and a cardinal spline.</span></span>  
  
 <span data-ttu-id="2a9da-115">![路径](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span><span class="sxs-lookup"><span data-stu-id="2a9da-115">![Path](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span></span>  
  
## <a name="using-a-path"></a><span data-ttu-id="2a9da-116">使用路径</span><span class="sxs-lookup"><span data-stu-id="2a9da-116">Using a Path</span></span>  
 <span data-ttu-id="2a9da-117"><xref:System.Drawing.Drawing2D.GraphicsPath>类提供以下方法用于创建要绘制的项序列： <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A> 、、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A> <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> 、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A> 、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (用于基数样条) 和 <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A> 。</span><span class="sxs-lookup"><span data-stu-id="2a9da-117">The <xref:System.Drawing.Drawing2D.GraphicsPath> class provides the following methods for creating a sequence of items to be drawn: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (for cardinal splines), and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span></span> <span data-ttu-id="2a9da-118">其中每个方法都是重载的;也就是说，每个方法都支持多个不同的参数列表。</span><span class="sxs-lookup"><span data-stu-id="2a9da-118">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="2a9da-119">例如，方法的一种变体 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 接收四个整数，而另一种变体 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 方法接收两个 <xref:System.Drawing.Point> 对象。</span><span class="sxs-lookup"><span data-stu-id="2a9da-119">For example, one variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives four integers, and another variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="2a9da-120">向路径添加直线、矩形和贝塞尔样条的方法具有在单个调用中将多个项添加到路径的复数伴随方法： <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A> 、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A> 和 <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A> 。</span><span class="sxs-lookup"><span data-stu-id="2a9da-120">The methods for adding lines, rectangles, and Bézier splines to a path have plural companion methods that add several items to the path in a single call: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span></span> <span data-ttu-id="2a9da-121">此外， <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> 和 <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> 方法具有伴随方法 <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> 和 <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A> ，后者将闭合曲线或饼图添加到路径。</span><span class="sxs-lookup"><span data-stu-id="2a9da-121">Also, the <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> methods have companion methods, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, that add a closed curve or pie to the path.</span></span>  
  
 <span data-ttu-id="2a9da-122">若要绘制路径，需要 <xref:System.Drawing.Graphics> 对象、对象 <xref:System.Drawing.Pen> 和 <xref:System.Drawing.Drawing2D.GraphicsPath> 对象。</span><span class="sxs-lookup"><span data-stu-id="2a9da-122">To draw a path, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="2a9da-123"><xref:System.Drawing.Graphics>对象提供 <xref:System.Drawing.Graphics.DrawPath%2A> 方法， <xref:System.Drawing.Pen> 对象存储用于呈现路径的线条的属性，例如宽度和颜色。</span><span class="sxs-lookup"><span data-stu-id="2a9da-123">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPath%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the path.</span></span> <span data-ttu-id="2a9da-124"><xref:System.Drawing.Drawing2D.GraphicsPath>对象存储构成路径的直线和曲线的序列。</span><span class="sxs-lookup"><span data-stu-id="2a9da-124">The <xref:System.Drawing.Drawing2D.GraphicsPath> object stores the sequence of lines and curves that make up the path.</span></span> <span data-ttu-id="2a9da-125"><xref:System.Drawing.Pen>对象和 <xref:System.Drawing.Drawing2D.GraphicsPath> 对象作为参数传递给 <xref:System.Drawing.Graphics.DrawPath%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="2a9da-125">The <xref:System.Drawing.Pen> object and the <xref:System.Drawing.Drawing2D.GraphicsPath> object are passed as arguments to the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="2a9da-126">下面的示例绘制一个由直线、椭圆和贝塞尔样条组成的路径：</span><span class="sxs-lookup"><span data-stu-id="2a9da-126">The following example draws a path that consists of a line, an ellipse, and a Bézier spline:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#101](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 <span data-ttu-id="2a9da-127">下图显示了该路径。</span><span class="sxs-lookup"><span data-stu-id="2a9da-127">The following illustration shows the path.</span></span>  
  
 <span data-ttu-id="2a9da-128">![路径](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span><span class="sxs-lookup"><span data-stu-id="2a9da-128">![Path](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span></span>  
  
 <span data-ttu-id="2a9da-129">除了向路径添加线条、矩形和曲线外，还可以将路径添加到路径。</span><span class="sxs-lookup"><span data-stu-id="2a9da-129">In addition to adding lines, rectangles, and curves to a path, you can add paths to a path.</span></span> <span data-ttu-id="2a9da-130">这样，便可以将现有路径组合起来以形成大型复杂路径。</span><span class="sxs-lookup"><span data-stu-id="2a9da-130">This allows you to combine existing paths to form large, complex paths.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#102](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 <span data-ttu-id="2a9da-131">还有两个可以添加到路径中的项：字符串和饼图。</span><span class="sxs-lookup"><span data-stu-id="2a9da-131">There are two other items you can add to a path: strings and pies.</span></span> <span data-ttu-id="2a9da-132">饼图是椭圆内部的一部分。</span><span class="sxs-lookup"><span data-stu-id="2a9da-132">A pie is a portion of the interior of an ellipse.</span></span> <span data-ttu-id="2a9da-133">下面的示例创建一个路径，从弧形、基数样条、字符串和饼形：</span><span class="sxs-lookup"><span data-stu-id="2a9da-133">The following example creates a path from an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#103](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 <span data-ttu-id="2a9da-134">下图显示了该路径。</span><span class="sxs-lookup"><span data-stu-id="2a9da-134">The following illustration shows the path.</span></span> <span data-ttu-id="2a9da-135">请注意，不需要连接路径;圆弧、基数样条、字符串和饼图是分隔的。</span><span class="sxs-lookup"><span data-stu-id="2a9da-135">Note that a path does not have to be connected; the arc, cardinal spline, string, and pie are separated.</span></span>  
  
 <span data-ttu-id="2a9da-136">![路径](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span><span class="sxs-lookup"><span data-stu-id="2a9da-136">![Paths](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a9da-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a9da-137">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [<span data-ttu-id="2a9da-138">直线、曲线和图形</span><span class="sxs-lookup"><span data-stu-id="2a9da-138">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="2a9da-139">如何：创建用于绘制的 Graphics 对象</span><span class="sxs-lookup"><span data-stu-id="2a9da-139">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="2a9da-140">构造并绘制轨迹</span><span class="sxs-lookup"><span data-stu-id="2a9da-140">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
