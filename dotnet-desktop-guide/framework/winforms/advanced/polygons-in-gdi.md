---
title: GDI+ 中的多边形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
ms.openlocfilehash: 2b1e3d387e4d056d9187c54dcef560544206c370
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970789"
---
# <a name="polygons-in-gdi"></a><span data-ttu-id="6c7d1-102">GDI+ 中的多边形</span><span class="sxs-lookup"><span data-stu-id="6c7d1-102">Polygons in GDI+</span></span>
<span data-ttu-id="6c7d1-103">多边形是具有三个或更多直线的闭合形状。</span><span class="sxs-lookup"><span data-stu-id="6c7d1-103">A polygon is a closed shape with three or more straight sides.</span></span> <span data-ttu-id="6c7d1-104">例如，三角形是具有三个边的多边形，矩形是具有四个边的多边形，而五边是具有五个边的多边形。</span><span class="sxs-lookup"><span data-stu-id="6c7d1-104">For example, a triangle is a polygon with three sides, a rectangle is a polygon with four sides, and a pentagon is a polygon with five sides.</span></span> <span data-ttu-id="6c7d1-105">下图显示了多个多边形。</span><span class="sxs-lookup"><span data-stu-id="6c7d1-105">The following illustration shows several polygons.</span></span>  
  
 <span data-ttu-id="6c7d1-106">![Polygon（多边形）](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span><span class="sxs-lookup"><span data-stu-id="6c7d1-106">![Polygons](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span></span>  
  
## <a name="drawing-a-polygon"></a><span data-ttu-id="6c7d1-107">绘制多边形</span><span class="sxs-lookup"><span data-stu-id="6c7d1-107">Drawing a Polygon</span></span>  
 <span data-ttu-id="6c7d1-108">若要绘制多边形，需要 <xref:System.Drawing.Graphics> 对象、 <xref:System.Drawing.Pen> 对象以及 <xref:System.Drawing.Point> (或 <xref:System.Drawing.PointF>) 对象的数组。</span><span class="sxs-lookup"><span data-stu-id="6c7d1-108">To draw a polygon, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and an array of <xref:System.Drawing.Point> (or <xref:System.Drawing.PointF>) objects.</span></span> <span data-ttu-id="6c7d1-109"><xref:System.Drawing.Graphics>对象提供 <xref:System.Drawing.Graphics.DrawPolygon%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="6c7d1-109">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="6c7d1-110"><xref:System.Drawing.Pen>对象存储用于呈现多边形的线条的属性，例如宽度和颜色，对象的数组 <xref:System.Drawing.Point> 存储要通过直线连接的点。</span><span class="sxs-lookup"><span data-stu-id="6c7d1-110">The <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the polygon, and the array of <xref:System.Drawing.Point> objects stores the points to be connected by straight lines.</span></span> <span data-ttu-id="6c7d1-111"><xref:System.Drawing.Pen>对象和 <xref:System.Drawing.Point> 对象数组作为参数传递给 <xref:System.Drawing.Graphics.DrawPolygon%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="6c7d1-111">The <xref:System.Drawing.Pen> object and the array of <xref:System.Drawing.Point> objects are passed as arguments to the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="6c7d1-112">下面的示例绘制一个三边多边形。</span><span class="sxs-lookup"><span data-stu-id="6c7d1-112">The following example draws a three-sided polygon.</span></span> <span data-ttu-id="6c7d1-113">请注意，只有三个点 `myPointArray` ： (0，0) ， (50，30) ， (30，60) 。</span><span class="sxs-lookup"><span data-stu-id="6c7d1-113">Note that there are only three points in `myPointArray`: (0, 0), (50, 30), and (30, 60).</span></span> <span data-ttu-id="6c7d1-114"><xref:System.Drawing.Graphics.DrawPolygon%2A>方法通过绘制一条从 (30，60) 返回到起始点 (0，0) 来自动关闭多边形。</span><span class="sxs-lookup"><span data-stu-id="6c7d1-114">The <xref:System.Drawing.Graphics.DrawPolygon%2A> method automatically closes the polygon by drawing a line from (30, 60) back to the starting point (0, 0).</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#111](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 <span data-ttu-id="6c7d1-115">下图显示了多边形。</span><span class="sxs-lookup"><span data-stu-id="6c7d1-115">The following illustration shows the polygon.</span></span>  
  
 <span data-ttu-id="6c7d1-116">![多边形](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span><span class="sxs-lookup"><span data-stu-id="6c7d1-116">![Polygon](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c7d1-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c7d1-117">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="6c7d1-118">直线、曲线和图形</span><span class="sxs-lookup"><span data-stu-id="6c7d1-118">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="6c7d1-119">如何：创建钢笔</span><span class="sxs-lookup"><span data-stu-id="6c7d1-119">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
