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
# <a name="graphics-paths-in-gdi"></a>GDI+ 中的图形路径
路径通过组合线条、矩形和简单曲线形成。 从 [矢量图形](vector-graphics-overview.md) 中回忆，以下基本构建基块已证明最适用于绘图图片：  
  
- 线条  
  
- 矩形  
  
- 椭圆  
  
- 形成  
  
- Polygon（多边形）  
  
- 基数样条  
  
- 贝塞尔样条  
  
 在 GDI + 中， <xref:System.Drawing.Drawing2D.GraphicsPath> 对象允许您将这些构建基块的序列收集到一个单元中。 然后，可以通过调用类的方法来绘制整个直线、矩形、多边形和曲线序列 <xref:System.Drawing.Graphics.DrawPath%2A> <xref:System.Drawing.Graphics> 。 下图显示了通过组合直线、圆弧、贝塞尔曲线和基数样条创建的路径。  
  
 ![路径](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")  
  
## <a name="using-a-path"></a>使用路径  
 <xref:System.Drawing.Drawing2D.GraphicsPath>类提供以下方法用于创建要绘制的项序列： <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A> 、、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A> <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> 、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A> 、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (用于基数样条) 和 <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A> 。 其中每个方法都是重载的;也就是说，每个方法都支持多个不同的参数列表。 例如，方法的一种变体 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 接收四个整数，而另一种变体 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 方法接收两个 <xref:System.Drawing.Point> 对象。  
  
 向路径添加直线、矩形和贝塞尔样条的方法具有在单个调用中将多个项添加到路径的复数伴随方法： <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A> 、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A> 和 <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A> 。 此外， <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> 和 <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> 方法具有伴随方法 <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> 和 <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A> ，后者将闭合曲线或饼图添加到路径。  
  
 若要绘制路径，需要 <xref:System.Drawing.Graphics> 对象、对象 <xref:System.Drawing.Pen> 和 <xref:System.Drawing.Drawing2D.GraphicsPath> 对象。 <xref:System.Drawing.Graphics>对象提供 <xref:System.Drawing.Graphics.DrawPath%2A> 方法， <xref:System.Drawing.Pen> 对象存储用于呈现路径的线条的属性，例如宽度和颜色。 <xref:System.Drawing.Drawing2D.GraphicsPath>对象存储构成路径的直线和曲线的序列。 <xref:System.Drawing.Pen>对象和 <xref:System.Drawing.Drawing2D.GraphicsPath> 对象作为参数传递给 <xref:System.Drawing.Graphics.DrawPath%2A> 方法。 下面的示例绘制一个由直线、椭圆和贝塞尔样条组成的路径：  
  
 [!code-csharp[LinesCurvesAndShapes#101](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 下图显示了该路径。  
  
 ![路径](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")  
  
 除了向路径添加线条、矩形和曲线外，还可以将路径添加到路径。 这样，便可以将现有路径组合起来以形成大型复杂路径。  
  
 [!code-csharp[LinesCurvesAndShapes#102](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 还有两个可以添加到路径中的项：字符串和饼图。 饼图是椭圆内部的一部分。 下面的示例创建一个路径，从弧形、基数样条、字符串和饼形：  
  
 [!code-csharp[LinesCurvesAndShapes#103](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 下图显示了该路径。 请注意，不需要连接路径;圆弧、基数样条、字符串和饼图是分隔的。  
  
 ![路径](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [直线、曲线和图形](lines-curves-and-shapes.md)
- [如何：创建用于绘制的 Graphics 对象](how-to-create-graphics-objects-for-drawing.md)
- [构造并绘制轨迹](constructing-and-drawing-paths.md)
