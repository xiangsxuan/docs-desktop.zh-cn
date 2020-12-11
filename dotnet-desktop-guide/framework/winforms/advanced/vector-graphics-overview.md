---
title: 向量图形概述
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inclusive-inclusive endpoints
- coordinate systems
- graphics [Windows Forms], vector graphics
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
ms.openlocfilehash: 6f405f5ffc67a0cdb13fe83f4dd36b70769a4cd9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971365"
---
# <a name="vector-graphics-overview"></a><span data-ttu-id="59951-102">向量图形概述</span><span class="sxs-lookup"><span data-stu-id="59951-102">Vector Graphics Overview</span></span>
<span data-ttu-id="59951-103">GDI + 在坐标系统上绘制线条、矩形和其他形状。</span><span class="sxs-lookup"><span data-stu-id="59951-103">GDI+ draws lines, rectangles, and other shapes on a coordinate system.</span></span> <span data-ttu-id="59951-104">您可以从各种坐标系统中进行选择，但默认坐标系统的原点位于左上角，且 x 轴指向右方，y 轴指向下方。</span><span class="sxs-lookup"><span data-stu-id="59951-104">You can choose from a variety of coordinate systems, but the default coordinate system has the origin in the upper-left corner with the x-axis pointing to the right and the y-axis pointing down.</span></span> <span data-ttu-id="59951-105">默认坐标系统中的度量单位是像素。</span><span class="sxs-lookup"><span data-stu-id="59951-105">The unit of measure in the default coordinate system is the pixel.</span></span>  
  
## <a name="the-building-blocks-of-gdi"></a><span data-ttu-id="59951-106">GDI + 的构建基块</span><span class="sxs-lookup"><span data-stu-id="59951-106">The Building Blocks of GDI+</span></span>  
 <span data-ttu-id="59951-107">![矢量图形](./media/aboutgdip02-art01.gif "AboutGdip02_Art01")</span><span class="sxs-lookup"><span data-stu-id="59951-107">![Vector graphic](./media/aboutgdip02-art01.gif "AboutGdip02_Art01")</span></span>  
  
 <span data-ttu-id="59951-108">计算机监视器在一组名为图片元素或像素的圆点上创建其显示。</span><span class="sxs-lookup"><span data-stu-id="59951-108">A computer monitor creates its display on a rectangular array of dots called picture elements or pixels.</span></span> <span data-ttu-id="59951-109">屏幕上显示的像素数因监视器的不同而异，并且单个监视器上显示的像素数通常可以配置为用户的某些范围。</span><span class="sxs-lookup"><span data-stu-id="59951-109">The number of pixels that appear on the screen varies from one monitor to the next, and the number of pixels that appear on an individual monitor can usually be configured to some extent by the user.</span></span>  
  
 <span data-ttu-id="59951-110">![矢量图形](./media/aboutgdip02-art02.gif "AboutGdip02_Art02")</span><span class="sxs-lookup"><span data-stu-id="59951-110">![Vector graphic](./media/aboutgdip02-art02.gif "AboutGdip02_Art02")</span></span>  
  
 <span data-ttu-id="59951-111">使用 GDI + 绘制线条、矩形或曲线时，需要提供有关要绘制的项的某些关键信息。</span><span class="sxs-lookup"><span data-stu-id="59951-111">When you use GDI+ to draw a line, rectangle, or curve, you provide certain key information about the item to be drawn.</span></span> <span data-ttu-id="59951-112">例如，可以通过提供两个点来指定线条，还可以通过提供一个点、高度和宽度来指定矩形。</span><span class="sxs-lookup"><span data-stu-id="59951-112">For example, you can specify a line by providing two points, and you can specify a rectangle by providing a point, a height, and a width.</span></span> <span data-ttu-id="59951-113">GDI + 与显示器驱动程序软件结合使用，以确定必须打开哪些像素以显示线条、矩形或曲线。</span><span class="sxs-lookup"><span data-stu-id="59951-113">GDI+ works in conjunction with the display driver software to determine which pixels must be turned on to show the line, rectangle, or curve.</span></span> <span data-ttu-id="59951-114">下图显示了已打开以从点 (4，2) 到点 (12，8) 点的线条。</span><span class="sxs-lookup"><span data-stu-id="59951-114">The following illustration shows the pixels that are turned on to display a line from the point (4, 2) to the point (12, 8).</span></span>  
  
 <span data-ttu-id="59951-115">![矢量图形](./media/aboutgdip02-art03.gif "AboutGdip02_Art03")</span><span class="sxs-lookup"><span data-stu-id="59951-115">![Vector graphic](./media/aboutgdip02-art03.gif "AboutGdip02_Art03")</span></span>  
  
 <span data-ttu-id="59951-116">随着时间的推移，某些基本构建基块已证明最适用于创建二维图片。</span><span class="sxs-lookup"><span data-stu-id="59951-116">Over time, certain basic building blocks have proven to be the most useful for creating two-dimensional pictures.</span></span> <span data-ttu-id="59951-117">下面的列表中提供了这些构建基块，它们均受 GDI + 支持：</span><span class="sxs-lookup"><span data-stu-id="59951-117">These building blocks, which are all supported by GDI+, are given in the following list:</span></span>  
  
- <span data-ttu-id="59951-118">线条</span><span class="sxs-lookup"><span data-stu-id="59951-118">Lines</span></span>  
  
- <span data-ttu-id="59951-119">矩形</span><span class="sxs-lookup"><span data-stu-id="59951-119">Rectangles</span></span>  
  
- <span data-ttu-id="59951-120">椭圆</span><span class="sxs-lookup"><span data-stu-id="59951-120">Ellipses</span></span>  
  
- <span data-ttu-id="59951-121">形成</span><span class="sxs-lookup"><span data-stu-id="59951-121">Arcs</span></span>  
  
- <span data-ttu-id="59951-122">Polygon（多边形）</span><span class="sxs-lookup"><span data-stu-id="59951-122">Polygons</span></span>  
  
- <span data-ttu-id="59951-123">基数样条</span><span class="sxs-lookup"><span data-stu-id="59951-123">Cardinal splines</span></span>  
  
- <span data-ttu-id="59951-124">贝塞尔曲线样条</span><span class="sxs-lookup"><span data-stu-id="59951-124">Bezier splines</span></span>  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a><span data-ttu-id="59951-125">使用图形对象进行绘制的方法</span><span class="sxs-lookup"><span data-stu-id="59951-125">Methods For Drawing with a Graphics Object</span></span>  
 <span data-ttu-id="59951-126"><xref:System.Drawing.Graphics>Gdi + 中的类提供以下方法用于绘制上一列表中的项： <xref:System.Drawing.Graphics.DrawLine%2A> 、 <xref:System.Drawing.Graphics.DrawRectangle%2A> 、 <xref:System.Drawing.Graphics.DrawEllipse%2A> 、 <xref:System.Drawing.Graphics.DrawPolygon%2A> 、 <xref:System.Drawing.Graphics.DrawArc%2A> 、 <xref:System.Drawing.Graphics.DrawCurve%2A> (用于基数样条) 和 <xref:System.Drawing.Graphics.DrawBezier%2A> 。</span><span class="sxs-lookup"><span data-stu-id="59951-126">The <xref:System.Drawing.Graphics> class in GDI+ provides the following methods for drawing the items in the previous list: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (for cardinal splines), and <xref:System.Drawing.Graphics.DrawBezier%2A>.</span></span> <span data-ttu-id="59951-127">其中每个方法都是重载的;也就是说，每个方法都支持多个不同的参数列表。</span><span class="sxs-lookup"><span data-stu-id="59951-127">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="59951-128">例如，方法的一个变体 <xref:System.Drawing.Graphics.DrawLine%2A> 接收一个 <xref:System.Drawing.Pen> 对象和四个整数，而该方法的另一个变体 <xref:System.Drawing.Graphics.DrawLine%2A> 接收 <xref:System.Drawing.Pen> 对象和两个 <xref:System.Drawing.Point> 对象。</span><span class="sxs-lookup"><span data-stu-id="59951-128">For example, one variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and four integers, while another variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="59951-129">绘制线条、矩形和贝塞尔样条的方法具有在单个调用中绘制若干项的复数伴生方法： <xref:System.Drawing.Graphics.DrawLines%2A> 、 <xref:System.Drawing.Graphics.DrawRectangles%2A> 和 <xref:System.Drawing.Graphics.DrawBeziers%2A> 。</span><span class="sxs-lookup"><span data-stu-id="59951-129">The methods for drawing lines, rectangles, and Bézier splines have plural companion methods that draw several items in a single call: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, and <xref:System.Drawing.Graphics.DrawBeziers%2A>.</span></span> <span data-ttu-id="59951-130">此外，该 <xref:System.Drawing.Graphics.DrawCurve%2A> 方法还具有一个伴随方法， <xref:System.Drawing.Graphics.DrawClosedCurve%2A> 该方法通过将曲线的结束点连接到起始点来关闭曲线。</span><span class="sxs-lookup"><span data-stu-id="59951-130">Also, the <xref:System.Drawing.Graphics.DrawCurve%2A> method has a companion method, <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, that closes a curve by connecting the ending point of the curve to the starting point.</span></span>  
  
 <span data-ttu-id="59951-131">类的所有绘图方法均 <xref:System.Drawing.Graphics> 与对象结合使用 <xref:System.Drawing.Pen> 。</span><span class="sxs-lookup"><span data-stu-id="59951-131">All of the drawing methods of the <xref:System.Drawing.Graphics> class work in conjunction with a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="59951-132">若要绘制任何内容，你必须至少创建两个对象： <xref:System.Drawing.Graphics> 对象和 <xref:System.Drawing.Pen> 对象。</span><span class="sxs-lookup"><span data-stu-id="59951-132">To draw anything, you must create at least two objects: a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="59951-133"><xref:System.Drawing.Pen>对象存储要绘制的项的属性，如线条宽度和颜色。</span><span class="sxs-lookup"><span data-stu-id="59951-133">The <xref:System.Drawing.Pen> object stores attributes, such as line width and color, of the item to be drawn.</span></span> <span data-ttu-id="59951-134"><xref:System.Drawing.Pen>对象作为一个自变量传递给绘图方法。</span><span class="sxs-lookup"><span data-stu-id="59951-134">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the drawing method.</span></span> <span data-ttu-id="59951-135">例如，方法的一种变体 <xref:System.Drawing.Graphics.DrawLine%2A> 接收一个 <xref:System.Drawing.Pen> 对象和四个整数，如下面的示例所示，它绘制一个宽度为100的矩形，高度为50，左上角的 (20，10) ：</span><span class="sxs-lookup"><span data-stu-id="59951-135">For example, one variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and four integers as shown in the following example, which draws a rectangle with a width of 100, a height of 50 and an upper-left corner of (20, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#11](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="59951-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59951-136">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="59951-137">直线、曲线和图形</span><span class="sxs-lookup"><span data-stu-id="59951-137">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="59951-138">如何：创建用于绘制的 Graphics 对象</span><span class="sxs-lookup"><span data-stu-id="59951-138">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
