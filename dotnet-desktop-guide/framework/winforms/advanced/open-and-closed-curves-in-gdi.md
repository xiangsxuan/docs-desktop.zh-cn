---
title: GDI+ 中的开放曲线和闭合曲线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- curves [Windows Forms], filling
- GDI+, curves
- curves [Windows Forms], drawing
- curves
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
ms.openlocfilehash: 06afdc4549f7c3c9b0636e5c7052dcca87a153f1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971608"
---
# <a name="open-and-closed-curves-in-gdi"></a><span data-ttu-id="e5ed0-102">GDI+ 中的开放曲线和闭合曲线</span><span class="sxs-lookup"><span data-stu-id="e5ed0-102">Open and Closed Curves in GDI+</span></span>
<span data-ttu-id="e5ed0-103">下图显示了两条曲线：一个打开，一个闭合。</span><span class="sxs-lookup"><span data-stu-id="e5ed0-103">The following illustration shows two curves: one open and one closed.</span></span>  
  
 <span data-ttu-id="e5ed0-104">![打开 & 闭合曲线](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span><span class="sxs-lookup"><span data-stu-id="e5ed0-104">![Open & Closed curves](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span></span>  
  
## <a name="managed-interface-for-curves"></a><span data-ttu-id="e5ed0-105">用于曲线的托管接口</span><span class="sxs-lookup"><span data-stu-id="e5ed0-105">Managed Interface for Curves</span></span>  
 <span data-ttu-id="e5ed0-106">闭合曲线具有内部，因此可以使用画笔进行填充。</span><span class="sxs-lookup"><span data-stu-id="e5ed0-106">Closed curves have an interior and therefore can be filled with a brush.</span></span> <span data-ttu-id="e5ed0-107"><xref:System.Drawing.Graphics>Gdi + 中的类提供以下用于填充闭合形状和曲线的方法： <xref:System.Drawing.Graphics.FillRectangle%2A> 、 <xref:System.Drawing.Graphics.FillEllipse%2A> 、 <xref:System.Drawing.Graphics.FillPie%2A> 、、、 <xref:System.Drawing.Graphics.FillPolygon%2A> <xref:System.Drawing.Graphics.FillClosedCurve%2A> <xref:System.Drawing.Graphics.FillPath%2A> 和 <xref:System.Drawing.Graphics.FillRegion%2A> 。</span><span class="sxs-lookup"><span data-stu-id="e5ed0-107">The <xref:System.Drawing.Graphics> class in GDI+ provides the following methods for filling closed shapes and curves: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, and <xref:System.Drawing.Graphics.FillRegion%2A>.</span></span> <span data-ttu-id="e5ed0-108">每次调用其中一个方法时，都必须将 (<xref:System.Drawing.SolidBrush> 、 <xref:System.Drawing.Drawing2D.HatchBrush> 、 <xref:System.Drawing.TextureBrush> 、或) 的特定画笔类型之一 <xref:System.Drawing.Drawing2D.LinearGradientBrush> <xref:System.Drawing.Drawing2D.PathGradientBrush> 作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="e5ed0-108">Whenever you call one of these methods, you must pass one of the specific brush types (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, or <xref:System.Drawing.Drawing2D.PathGradientBrush>) as an argument.</span></span>  
  
 <span data-ttu-id="e5ed0-109"><xref:System.Drawing.Graphics.FillPie%2A>方法与方法一起使用 <xref:System.Drawing.Graphics.DrawArc%2A> 。</span><span class="sxs-lookup"><span data-stu-id="e5ed0-109">The <xref:System.Drawing.Graphics.FillPie%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawArc%2A> method.</span></span> <span data-ttu-id="e5ed0-110">正如 <xref:System.Drawing.Graphics.DrawArc%2A> 方法绘制椭圆轮廓的一部分一样，该 <xref:System.Drawing.Graphics.FillPie%2A> 方法将填充椭圆的一部分。</span><span class="sxs-lookup"><span data-stu-id="e5ed0-110">Just as the <xref:System.Drawing.Graphics.DrawArc%2A> method draws a portion of the outline of an ellipse, the <xref:System.Drawing.Graphics.FillPie%2A> method fills a portion of the interior of an ellipse.</span></span> <span data-ttu-id="e5ed0-111">下面的示例绘制一段弧线，并填充椭圆内部的相应部分：</span><span class="sxs-lookup"><span data-stu-id="e5ed0-111">The following example draws an arc and fills the corresponding portion of the interior of the ellipse:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#21](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 <span data-ttu-id="e5ed0-112">下图显示了弧线和填充的饼图。</span><span class="sxs-lookup"><span data-stu-id="e5ed0-112">The following illustration shows the arc and the filled pie.</span></span>  
  
 <span data-ttu-id="e5ed0-113">![打开 & 闭合曲线](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span><span class="sxs-lookup"><span data-stu-id="e5ed0-113">![Open & Closed curves](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span></span>  
  
 <span data-ttu-id="e5ed0-114"><xref:System.Drawing.Graphics.FillClosedCurve%2A>方法与方法一起使用 <xref:System.Drawing.Graphics.DrawClosedCurve%2A> 。</span><span class="sxs-lookup"><span data-stu-id="e5ed0-114">The <xref:System.Drawing.Graphics.FillClosedCurve%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method.</span></span> <span data-ttu-id="e5ed0-115">这两种方法都通过将结束点连接到起始点来自动闭合曲线。</span><span class="sxs-lookup"><span data-stu-id="e5ed0-115">Both methods automatically close the curve by connecting the ending point to the starting point.</span></span> <span data-ttu-id="e5ed0-116">下面的示例绘制一个曲线，该曲线通过 (0，0) ， (60，20) ， (40，50) 。</span><span class="sxs-lookup"><span data-stu-id="e5ed0-116">The following example draws a curve that passes through (0, 0), (60, 20), and (40, 50).</span></span> <span data-ttu-id="e5ed0-117">然后，通过将 (40，50) 连接到起始点 (0，0) ，并使用纯色填充内部来自动关闭曲线。</span><span class="sxs-lookup"><span data-stu-id="e5ed0-117">Then, the curve is automatically closed by connecting (40, 50) to the starting point (0, 0), and the interior is filled with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#22](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 <span data-ttu-id="e5ed0-118"><xref:System.Drawing.Graphics.FillPath%2A>方法填充路径的各个部分的内部。</span><span class="sxs-lookup"><span data-stu-id="e5ed0-118">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the interiors of the separate pieces of a path.</span></span> <span data-ttu-id="e5ed0-119">如果路径中的某一段不构成闭合曲线或形状，则在填充该路径之前，该 <xref:System.Drawing.Graphics.FillPath%2A> 方法将自动关闭该路径部分。</span><span class="sxs-lookup"><span data-stu-id="e5ed0-119">If a piece of a path doesn't form a closed curve or shape, the <xref:System.Drawing.Graphics.FillPath%2A> method automatically closes that piece of the path before filling it.</span></span> <span data-ttu-id="e5ed0-120">下面的示例绘制并填充一个路径，该路径包含一个圆弧、一个基数样条、一个字符串和一个扇形：</span><span class="sxs-lookup"><span data-stu-id="e5ed0-120">The following example draws and fills a path that consists of an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#23](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 <span data-ttu-id="e5ed0-121">下图显示了具有和没有纯色填充的路径。</span><span class="sxs-lookup"><span data-stu-id="e5ed0-121">The following illustration shows the path with and without the solid fill.</span></span> <span data-ttu-id="e5ed0-122">请注意，该字符串中的文本带有方法，而不是填充 <xref:System.Drawing.Graphics.DrawPath%2A> 。</span><span class="sxs-lookup"><span data-stu-id="e5ed0-122">Note that the text in the string is outlined, but not filled, by the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="e5ed0-123">这是 <xref:System.Drawing.Graphics.FillPath%2A> 绘制字符串中字符的内部的方法。</span><span class="sxs-lookup"><span data-stu-id="e5ed0-123">It is the <xref:System.Drawing.Graphics.FillPath%2A> method that paints the interiors of the characters in the string.</span></span>  
  
 <span data-ttu-id="e5ed0-124">![路径中的字符串](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span><span class="sxs-lookup"><span data-stu-id="e5ed0-124">![String in a path](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5ed0-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5ed0-125">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [<span data-ttu-id="e5ed0-126">直线、曲线和图形</span><span class="sxs-lookup"><span data-stu-id="e5ed0-126">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="e5ed0-127">如何：创建用于绘制的 Graphics 对象</span><span class="sxs-lookup"><span data-stu-id="e5ed0-127">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="e5ed0-128">构造并绘制轨迹</span><span class="sxs-lookup"><span data-stu-id="e5ed0-128">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
