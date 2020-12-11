---
title: GDI+ 中的椭圆和弧线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- arcs
- GDI+, arcs
- drawing [Windows Forms], ellipses
- GDI+, ellipses
- ellipses
- drawing [Windows Forms], arcs
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
ms.openlocfilehash: 8bbc2eda6450128eac55576259880e83f07099ab
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970812"
---
# <a name="ellipses-and-arcs-in-gdi"></a><span data-ttu-id="a3e15-102">GDI+ 中的椭圆和弧线</span><span class="sxs-lookup"><span data-stu-id="a3e15-102">Ellipses and Arcs in GDI+</span></span>
<span data-ttu-id="a3e15-103">使用类的和方法，可以轻松地绘制省略号和弧线 <xref:System.Drawing.Graphics.DrawEllipse%2A> <xref:System.Drawing.Graphics.DrawArc%2A> <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="a3e15-103">You can easily draw ellipses and arcs using the <xref:System.Drawing.Graphics.DrawEllipse%2A> and <xref:System.Drawing.Graphics.DrawArc%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="drawing-an-ellipse"></a><span data-ttu-id="a3e15-104">绘制椭圆</span><span class="sxs-lookup"><span data-stu-id="a3e15-104">Drawing an Ellipse</span></span>  
 <span data-ttu-id="a3e15-105">若要绘制椭圆，需要 <xref:System.Drawing.Graphics> 对象和 <xref:System.Drawing.Pen> 对象。</span><span class="sxs-lookup"><span data-stu-id="a3e15-105">To draw an ellipse, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="a3e15-106"><xref:System.Drawing.Graphics>对象提供 <xref:System.Drawing.Graphics.DrawEllipse%2A> 方法， <xref:System.Drawing.Pen> 对象存储用于呈现椭圆的线条的属性，例如宽度和颜色。</span><span class="sxs-lookup"><span data-stu-id="a3e15-106">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the ellipse.</span></span> <span data-ttu-id="a3e15-107"><xref:System.Drawing.Pen>对象作为参数之一传递给 <xref:System.Drawing.Graphics.DrawEllipse%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="a3e15-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="a3e15-108">传递给方法的其余参数 <xref:System.Drawing.Graphics.DrawEllipse%2A> 指定椭圆的边框。</span><span class="sxs-lookup"><span data-stu-id="a3e15-108">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method specify the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="a3e15-109">下图显示了一个椭圆及其边框。</span><span class="sxs-lookup"><span data-stu-id="a3e15-109">The following illustration shows an ellipse along with its bounding rectangle.</span></span>  
  
 <span data-ttu-id="a3e15-110">![省略号和弧形](./media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span><span class="sxs-lookup"><span data-stu-id="a3e15-110">![Ellipses and arcs](./media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span></span>  
  
 <span data-ttu-id="a3e15-111">下面的示例绘制一个椭圆形;边框的宽度为80，高度为40， (100，50) 的左上角：</span><span class="sxs-lookup"><span data-stu-id="a3e15-111">The following example draws an ellipse; the bounding rectangle has a width of 80, a height of 40, and an upper-left corner of (100, 50):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#51](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <span data-ttu-id="a3e15-112"><xref:System.Drawing.Graphics.DrawEllipse%2A> 是类的重载方法 <xref:System.Drawing.Graphics> ，因此可以通过多种方式为其提供参数。</span><span class="sxs-lookup"><span data-stu-id="a3e15-112"><xref:System.Drawing.Graphics.DrawEllipse%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="a3e15-113">例如，可以构造 <xref:System.Drawing.Rectangle> ，并将 <xref:System.Drawing.Rectangle> <xref:System.Drawing.Graphics.DrawEllipse%2A> 作为参数传递给方法：</span><span class="sxs-lookup"><span data-stu-id="a3e15-113">For example, you can construct a <xref:System.Drawing.Rectangle> and pass the <xref:System.Drawing.Rectangle> to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#52](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a><span data-ttu-id="a3e15-114">绘制弧形</span><span class="sxs-lookup"><span data-stu-id="a3e15-114">Drawing an Arc</span></span>  
 <span data-ttu-id="a3e15-115">弧形是椭圆的一部分。</span><span class="sxs-lookup"><span data-stu-id="a3e15-115">An arc is a portion of an ellipse.</span></span> <span data-ttu-id="a3e15-116">若要绘制弧形，请调用 <xref:System.Drawing.Graphics.DrawArc%2A> 类的方法 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="a3e15-116">To draw an arc, you call the <xref:System.Drawing.Graphics.DrawArc%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="a3e15-117">方法的参数与 <xref:System.Drawing.Graphics.DrawArc%2A> 方法的参数相同 <xref:System.Drawing.Graphics.DrawEllipse%2A> ，不同之处在于 <xref:System.Drawing.Graphics.DrawArc%2A> 需要开始角度和扫描角度。</span><span class="sxs-lookup"><span data-stu-id="a3e15-117">The parameters of the <xref:System.Drawing.Graphics.DrawArc%2A> method are the same as the parameters of the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, except that <xref:System.Drawing.Graphics.DrawArc%2A> requires a starting angle and sweep angle.</span></span> <span data-ttu-id="a3e15-118">下面的示例绘制一个弧，其起始角度为30度，扫描角度为180度：</span><span class="sxs-lookup"><span data-stu-id="a3e15-118">The following example draws an arc with a starting angle of 30 degrees and a sweep angle of 180 degrees:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#53](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 <span data-ttu-id="a3e15-119">下图显示了弧线、椭圆和边框。</span><span class="sxs-lookup"><span data-stu-id="a3e15-119">The following illustration shows the arc, the ellipse, and the bounding rectangle.</span></span>  
  
 <span data-ttu-id="a3e15-120">![省略号和弧形](./media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span><span class="sxs-lookup"><span data-stu-id="a3e15-120">![Ellipses and arcs](./media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3e15-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3e15-121">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="a3e15-122">直线、曲线和图形</span><span class="sxs-lookup"><span data-stu-id="a3e15-122">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="a3e15-123">如何：创建用于绘制的 Graphics 对象</span><span class="sxs-lookup"><span data-stu-id="a3e15-123">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="a3e15-124">如何：创建钢笔</span><span class="sxs-lookup"><span data-stu-id="a3e15-124">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="a3e15-125">如何：绘制轮廓形状</span><span class="sxs-lookup"><span data-stu-id="a3e15-125">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)
