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
# <a name="ellipses-and-arcs-in-gdi"></a>GDI+ 中的椭圆和弧线
使用类的和方法，可以轻松地绘制省略号和弧线 <xref:System.Drawing.Graphics.DrawEllipse%2A> <xref:System.Drawing.Graphics.DrawArc%2A> <xref:System.Drawing.Graphics> 。  
  
## <a name="drawing-an-ellipse"></a>绘制椭圆  
 若要绘制椭圆，需要 <xref:System.Drawing.Graphics> 对象和 <xref:System.Drawing.Pen> 对象。 <xref:System.Drawing.Graphics>对象提供 <xref:System.Drawing.Graphics.DrawEllipse%2A> 方法， <xref:System.Drawing.Pen> 对象存储用于呈现椭圆的线条的属性，例如宽度和颜色。 <xref:System.Drawing.Pen>对象作为参数之一传递给 <xref:System.Drawing.Graphics.DrawEllipse%2A> 方法。 传递给方法的其余参数 <xref:System.Drawing.Graphics.DrawEllipse%2A> 指定椭圆的边框。 下图显示了一个椭圆及其边框。  
  
 ![省略号和弧形](./media/aboutgdip02-art05.gif "Aboutgdip02_art05")  
  
 下面的示例绘制一个椭圆形;边框的宽度为80，高度为40， (100，50) 的左上角：  
  
 [!code-csharp[LinesCurvesAndShapes#51](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <xref:System.Drawing.Graphics.DrawEllipse%2A> 是类的重载方法 <xref:System.Drawing.Graphics> ，因此可以通过多种方式为其提供参数。 例如，可以构造 <xref:System.Drawing.Rectangle> ，并将 <xref:System.Drawing.Rectangle> <xref:System.Drawing.Graphics.DrawEllipse%2A> 作为参数传递给方法：  
  
 [!code-csharp[LinesCurvesAndShapes#52](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a>绘制弧形  
 弧形是椭圆的一部分。 若要绘制弧形，请调用 <xref:System.Drawing.Graphics.DrawArc%2A> 类的方法 <xref:System.Drawing.Graphics> 。 方法的参数与 <xref:System.Drawing.Graphics.DrawArc%2A> 方法的参数相同 <xref:System.Drawing.Graphics.DrawEllipse%2A> ，不同之处在于 <xref:System.Drawing.Graphics.DrawArc%2A> 需要开始角度和扫描角度。 下面的示例绘制一个弧，其起始角度为30度，扫描角度为180度：  
  
 [!code-csharp[LinesCurvesAndShapes#53](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 下图显示了弧线、椭圆和边框。  
  
 ![省略号和弧形](./media/aboutgdip02-art06.gif "Aboutgdip02_art06")  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [直线、曲线和图形](lines-curves-and-shapes.md)
- [如何：创建用于绘制的 Graphics 对象](how-to-create-graphics-objects-for-drawing.md)
- [如何：创建钢笔](how-to-create-a-pen.md)
- [如何：绘制轮廓形状](how-to-draw-an-outlined-shape.md)
