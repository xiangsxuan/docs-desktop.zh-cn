---
title: GDI+ 中的笔、直线和矩形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines
- GDI+, lines
- drawing [Windows Forms], rectangles
- rectangles
- drawing [Windows Forms], lines
- GDI+, pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- GDI+, rectangles
- examples [Windows Forms], GDI+
- lines [Windows Forms], dashed
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
ms.openlocfilehash: 06d2351ffa7d7f009d7b049f4689df7038b4d202
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971607"
---
# <a name="pens-lines-and-rectangles-in-gdi"></a><span data-ttu-id="106de-102">GDI+ 中的笔、直线和矩形</span><span class="sxs-lookup"><span data-stu-id="106de-102">Pens, Lines, and Rectangles in GDI+</span></span>
<span data-ttu-id="106de-103">若要使用 GDI + 绘制线条，需要创建 <xref:System.Drawing.Graphics> 对象和 <xref:System.Drawing.Pen> 对象。</span><span class="sxs-lookup"><span data-stu-id="106de-103">To draw lines with GDI+ you need to create a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="106de-104"><xref:System.Drawing.Graphics>对象提供实际执行绘图的方法， <xref:System.Drawing.Pen> 对象存储属性，如线条颜色、宽度和样式。</span><span class="sxs-lookup"><span data-stu-id="106de-104">The <xref:System.Drawing.Graphics> object provides the methods that actually do the drawing, and the <xref:System.Drawing.Pen> object stores attributes, such as line color, width, and style.</span></span>  
  
## <a name="drawing-a-line"></a><span data-ttu-id="106de-105">绘制线条</span><span class="sxs-lookup"><span data-stu-id="106de-105">Drawing a Line</span></span>  
 <span data-ttu-id="106de-106">若要绘制线条，请调用 <xref:System.Drawing.Graphics.DrawLine%2A> 对象的方法 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="106de-106">To draw a line, call the <xref:System.Drawing.Graphics.DrawLine%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="106de-107"><xref:System.Drawing.Pen>对象作为参数之一传递给 <xref:System.Drawing.Graphics.DrawLine%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="106de-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method.</span></span> <span data-ttu-id="106de-108">下面的示例从点 (4，2) 绘制一条直线， (12，6) ：</span><span class="sxs-lookup"><span data-stu-id="106de-108">The following example draws a line from the point (4, 2) to the point (12, 6):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#41](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <span data-ttu-id="106de-109"><xref:System.Drawing.Graphics.DrawLine%2A> 是类的重载方法 <xref:System.Drawing.Graphics> ，因此可以通过多种方式为其提供参数。</span><span class="sxs-lookup"><span data-stu-id="106de-109"><xref:System.Drawing.Graphics.DrawLine%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="106de-110">例如，可以构造两个 <xref:System.Drawing.Point> 对象，并将 <xref:System.Drawing.Point> 对象作为参数传递给 <xref:System.Drawing.Graphics.DrawLine%2A> 方法：</span><span class="sxs-lookup"><span data-stu-id="106de-110">For example, you can construct two <xref:System.Drawing.Point> objects and pass the <xref:System.Drawing.Point> objects as arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#42](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a><span data-ttu-id="106de-111">构造笔</span><span class="sxs-lookup"><span data-stu-id="106de-111">Constructing a Pen</span></span>  
 <span data-ttu-id="106de-112">构造对象时，可以指定某些属性 <xref:System.Drawing.Pen> 。</span><span class="sxs-lookup"><span data-stu-id="106de-112">You can specify certain attributes when you construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="106de-113">例如，通过一个 `Pen` 构造函数可以指定颜色和宽度。</span><span class="sxs-lookup"><span data-stu-id="106de-113">For example, one `Pen` constructor allows you to specify color and width.</span></span> <span data-ttu-id="106de-114">下面的示例将 (0，0) 中的蓝色线条绘制到 (60，30) ：</span><span class="sxs-lookup"><span data-stu-id="106de-114">The following example draws a blue line of width 2 from (0, 0) to (60, 30):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#43](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a><span data-ttu-id="106de-115">虚线和行帽</span><span class="sxs-lookup"><span data-stu-id="106de-115">Dashed Lines and Line Caps</span></span>  
 <span data-ttu-id="106de-116"><xref:System.Drawing.Pen>对象还公开了 <xref:System.Drawing.Pen.DashStyle%2A> 可用于指定线条功能的属性，例如。</span><span class="sxs-lookup"><span data-stu-id="106de-116">The <xref:System.Drawing.Pen> object also exposes properties, such as <xref:System.Drawing.Pen.DashStyle%2A>, that you can use to specify features of the line.</span></span> <span data-ttu-id="106de-117">下面的示例从 (100，50) 绘制虚线到 (300，80) ：</span><span class="sxs-lookup"><span data-stu-id="106de-117">The following example draws a dashed line from (100, 50) to (300, 80):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#44](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 <span data-ttu-id="106de-118">可以使用对象的属性 <xref:System.Drawing.Pen> 来设置行的更多属性。</span><span class="sxs-lookup"><span data-stu-id="106de-118">You can use the properties of the <xref:System.Drawing.Pen> object to set many more attributes of the line.</span></span> <span data-ttu-id="106de-119"><xref:System.Drawing.Pen.StartCap%2A>和 <xref:System.Drawing.Pen.EndCap%2A> 属性指定线条的端点的外观; 端点可以为平面、方形、圆角、三角或自定义形状。</span><span class="sxs-lookup"><span data-stu-id="106de-119">The <xref:System.Drawing.Pen.StartCap%2A> and <xref:System.Drawing.Pen.EndCap%2A> properties specify the appearance of the ends of the line; the ends can be flat, square, rounded, triangular, or a custom shape.</span></span> <span data-ttu-id="106de-120"><xref:System.Drawing.Pen.LineJoin%2A>通过属性，您可以指定连接的线是否 (联接) 、凹凸、圆形或剪裁的尖角。</span><span class="sxs-lookup"><span data-stu-id="106de-120">The <xref:System.Drawing.Pen.LineJoin%2A> property lets you specify whether connected lines are mitered (joined with sharp corners), beveled, rounded, or clipped.</span></span> <span data-ttu-id="106de-121">下图显示了具有各种大写字母和联接样式的行。</span><span class="sxs-lookup"><span data-stu-id="106de-121">The following illustration shows lines with various cap and join styles.</span></span>  
  
 <span data-ttu-id="106de-122">![行](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span><span class="sxs-lookup"><span data-stu-id="106de-122">![Lines](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span></span>  
  
## <a name="drawing-a-rectangle"></a><span data-ttu-id="106de-123">绘制矩形</span><span class="sxs-lookup"><span data-stu-id="106de-123">Drawing a Rectangle</span></span>  
 <span data-ttu-id="106de-124">用 GDI + 绘制矩形类似于绘制线条。</span><span class="sxs-lookup"><span data-stu-id="106de-124">Drawing rectangles with GDI+ is similar to drawing lines.</span></span> <span data-ttu-id="106de-125">若要绘制矩形，需要 <xref:System.Drawing.Graphics> 对象和 <xref:System.Drawing.Pen> 对象。</span><span class="sxs-lookup"><span data-stu-id="106de-125">To draw a rectangle, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="106de-126"><xref:System.Drawing.Graphics>对象提供 <xref:System.Drawing.Graphics.DrawRectangle%2A> 方法， <xref:System.Drawing.Pen> 对象存储属性，如线条宽度和颜色。</span><span class="sxs-lookup"><span data-stu-id="106de-126">The <xref:System.Drawing.Graphics> object provides a <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as line width and color.</span></span> <span data-ttu-id="106de-127"><xref:System.Drawing.Pen>对象作为参数之一传递给 <xref:System.Drawing.Graphics.DrawRectangle%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="106de-127">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method.</span></span> <span data-ttu-id="106de-128">下面的示例绘制一个矩形，其左上角位于 (100，50) ，宽度为80，高度为40：</span><span class="sxs-lookup"><span data-stu-id="106de-128">The following example draws a rectangle with its upper-left corner at (100, 50), a width of 80, and a height of 40:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#45](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <span data-ttu-id="106de-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> 是类的重载方法 <xref:System.Drawing.Graphics> ，因此可以通过多种方式为其提供参数。</span><span class="sxs-lookup"><span data-stu-id="106de-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="106de-130">例如，您可以构造一个 <xref:System.Drawing.Rectangle> 对象并将该 <xref:System.Drawing.Rectangle> 对象作为参数传递给该 <xref:System.Drawing.Graphics.DrawRectangle%2A> 方法：</span><span class="sxs-lookup"><span data-stu-id="106de-130">For example, you can construct a <xref:System.Drawing.Rectangle> object and pass the <xref:System.Drawing.Rectangle> object to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#46](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 <span data-ttu-id="106de-131"><xref:System.Drawing.Rectangle>对象具有用于处理和收集有关矩形的信息的方法和属性。</span><span class="sxs-lookup"><span data-stu-id="106de-131">A <xref:System.Drawing.Rectangle> object has methods and properties for manipulating and gathering information about the rectangle.</span></span> <span data-ttu-id="106de-132">例如， <xref:System.Drawing.Rectangle.Inflate%2A> 和 <xref:System.Drawing.Rectangle.Offset%2A> 方法更改矩形的大小和位置。</span><span class="sxs-lookup"><span data-stu-id="106de-132">For example, the <xref:System.Drawing.Rectangle.Inflate%2A> and <xref:System.Drawing.Rectangle.Offset%2A> methods change the size and position of the rectangle.</span></span> <span data-ttu-id="106de-133"><xref:System.Drawing.Rectangle.IntersectsWith%2A>方法会告诉您矩形是否与另一个给定矩形相交， <xref:System.Drawing.Rectangle.Contains%2A> 方法会告诉您给定点是否位于该矩形内。</span><span class="sxs-lookup"><span data-stu-id="106de-133">The <xref:System.Drawing.Rectangle.IntersectsWith%2A> method tells you whether the rectangle intersects another given rectangle, and the <xref:System.Drawing.Rectangle.Contains%2A> method tells you whether a given point is inside the rectangle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="106de-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="106de-134">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- [<span data-ttu-id="106de-135">如何：创建钢笔</span><span class="sxs-lookup"><span data-stu-id="106de-135">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="106de-136">如何：在 Windows 窗体上绘制直线</span><span class="sxs-lookup"><span data-stu-id="106de-136">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)
- [<span data-ttu-id="106de-137">如何：绘制轮廓形状</span><span class="sxs-lookup"><span data-stu-id="106de-137">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)
