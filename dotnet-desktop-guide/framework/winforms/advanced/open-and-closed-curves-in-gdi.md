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
# <a name="open-and-closed-curves-in-gdi"></a>GDI+ 中的开放曲线和闭合曲线
下图显示了两条曲线：一个打开，一个闭合。  
  
 ![打开 & 闭合曲线](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")  
  
## <a name="managed-interface-for-curves"></a>用于曲线的托管接口  
 闭合曲线具有内部，因此可以使用画笔进行填充。 <xref:System.Drawing.Graphics>Gdi + 中的类提供以下用于填充闭合形状和曲线的方法： <xref:System.Drawing.Graphics.FillRectangle%2A> 、 <xref:System.Drawing.Graphics.FillEllipse%2A> 、 <xref:System.Drawing.Graphics.FillPie%2A> 、、、 <xref:System.Drawing.Graphics.FillPolygon%2A> <xref:System.Drawing.Graphics.FillClosedCurve%2A> <xref:System.Drawing.Graphics.FillPath%2A> 和 <xref:System.Drawing.Graphics.FillRegion%2A> 。 每次调用其中一个方法时，都必须将 (<xref:System.Drawing.SolidBrush> 、 <xref:System.Drawing.Drawing2D.HatchBrush> 、 <xref:System.Drawing.TextureBrush> 、或) 的特定画笔类型之一 <xref:System.Drawing.Drawing2D.LinearGradientBrush> <xref:System.Drawing.Drawing2D.PathGradientBrush> 作为参数传递。  
  
 <xref:System.Drawing.Graphics.FillPie%2A>方法与方法一起使用 <xref:System.Drawing.Graphics.DrawArc%2A> 。 正如 <xref:System.Drawing.Graphics.DrawArc%2A> 方法绘制椭圆轮廓的一部分一样，该 <xref:System.Drawing.Graphics.FillPie%2A> 方法将填充椭圆的一部分。 下面的示例绘制一段弧线，并填充椭圆内部的相应部分：  
  
 [!code-csharp[LinesCurvesAndShapes#21](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 下图显示了弧线和填充的饼图。  
  
 ![打开 & 闭合曲线](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")  
  
 <xref:System.Drawing.Graphics.FillClosedCurve%2A>方法与方法一起使用 <xref:System.Drawing.Graphics.DrawClosedCurve%2A> 。 这两种方法都通过将结束点连接到起始点来自动闭合曲线。 下面的示例绘制一个曲线，该曲线通过 (0，0) ， (60，20) ， (40，50) 。 然后，通过将 (40，50) 连接到起始点 (0，0) ，并使用纯色填充内部来自动关闭曲线。  
  
 [!code-csharp[LinesCurvesAndShapes#22](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 <xref:System.Drawing.Graphics.FillPath%2A>方法填充路径的各个部分的内部。 如果路径中的某一段不构成闭合曲线或形状，则在填充该路径之前，该 <xref:System.Drawing.Graphics.FillPath%2A> 方法将自动关闭该路径部分。 下面的示例绘制并填充一个路径，该路径包含一个圆弧、一个基数样条、一个字符串和一个扇形：  
  
 [!code-csharp[LinesCurvesAndShapes#23](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 下图显示了具有和没有纯色填充的路径。 请注意，该字符串中的文本带有方法，而不是填充 <xref:System.Drawing.Graphics.DrawPath%2A> 。 这是 <xref:System.Drawing.Graphics.FillPath%2A> 绘制字符串中字符的内部的方法。  
  
 ![路径中的字符串](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [直线、曲线和图形](lines-curves-and-shapes.md)
- [如何：创建用于绘制的 Graphics 对象](how-to-create-graphics-objects-for-drawing.md)
- [构造并绘制轨迹](constructing-and-drawing-paths.md)
