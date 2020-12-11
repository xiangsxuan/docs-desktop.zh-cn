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
# <a name="pens-lines-and-rectangles-in-gdi"></a>GDI+ 中的笔、直线和矩形
若要使用 GDI + 绘制线条，需要创建 <xref:System.Drawing.Graphics> 对象和 <xref:System.Drawing.Pen> 对象。 <xref:System.Drawing.Graphics>对象提供实际执行绘图的方法， <xref:System.Drawing.Pen> 对象存储属性，如线条颜色、宽度和样式。  
  
## <a name="drawing-a-line"></a>绘制线条  
 若要绘制线条，请调用 <xref:System.Drawing.Graphics.DrawLine%2A> 对象的方法 <xref:System.Drawing.Graphics> 。 <xref:System.Drawing.Pen>对象作为参数之一传递给 <xref:System.Drawing.Graphics.DrawLine%2A> 方法。 下面的示例从点 (4，2) 绘制一条直线， (12，6) ：  
  
 [!code-csharp[LinesCurvesAndShapes#41](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <xref:System.Drawing.Graphics.DrawLine%2A> 是类的重载方法 <xref:System.Drawing.Graphics> ，因此可以通过多种方式为其提供参数。 例如，可以构造两个 <xref:System.Drawing.Point> 对象，并将 <xref:System.Drawing.Point> 对象作为参数传递给 <xref:System.Drawing.Graphics.DrawLine%2A> 方法：  
  
 [!code-csharp[LinesCurvesAndShapes#42](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a>构造笔  
 构造对象时，可以指定某些属性 <xref:System.Drawing.Pen> 。 例如，通过一个 `Pen` 构造函数可以指定颜色和宽度。 下面的示例将 (0，0) 中的蓝色线条绘制到 (60，30) ：  
  
 [!code-csharp[LinesCurvesAndShapes#43](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a>虚线和行帽  
 <xref:System.Drawing.Pen>对象还公开了 <xref:System.Drawing.Pen.DashStyle%2A> 可用于指定线条功能的属性，例如。 下面的示例从 (100，50) 绘制虚线到 (300，80) ：  
  
 [!code-csharp[LinesCurvesAndShapes#44](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 可以使用对象的属性 <xref:System.Drawing.Pen> 来设置行的更多属性。 <xref:System.Drawing.Pen.StartCap%2A>和 <xref:System.Drawing.Pen.EndCap%2A> 属性指定线条的端点的外观; 端点可以为平面、方形、圆角、三角或自定义形状。 <xref:System.Drawing.Pen.LineJoin%2A>通过属性，您可以指定连接的线是否 (联接) 、凹凸、圆形或剪裁的尖角。 下图显示了具有各种大写字母和联接样式的行。  
  
 ![行](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")  
  
## <a name="drawing-a-rectangle"></a>绘制矩形  
 用 GDI + 绘制矩形类似于绘制线条。 若要绘制矩形，需要 <xref:System.Drawing.Graphics> 对象和 <xref:System.Drawing.Pen> 对象。 <xref:System.Drawing.Graphics>对象提供 <xref:System.Drawing.Graphics.DrawRectangle%2A> 方法， <xref:System.Drawing.Pen> 对象存储属性，如线条宽度和颜色。 <xref:System.Drawing.Pen>对象作为参数之一传递给 <xref:System.Drawing.Graphics.DrawRectangle%2A> 方法。 下面的示例绘制一个矩形，其左上角位于 (100，50) ，宽度为80，高度为40：  
  
 [!code-csharp[LinesCurvesAndShapes#45](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <xref:System.Drawing.Graphics.DrawRectangle%2A> 是类的重载方法 <xref:System.Drawing.Graphics> ，因此可以通过多种方式为其提供参数。 例如，您可以构造一个 <xref:System.Drawing.Rectangle> 对象并将该 <xref:System.Drawing.Rectangle> 对象作为参数传递给该 <xref:System.Drawing.Graphics.DrawRectangle%2A> 方法：  
  
 [!code-csharp[LinesCurvesAndShapes#46](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 <xref:System.Drawing.Rectangle>对象具有用于处理和收集有关矩形的信息的方法和属性。 例如， <xref:System.Drawing.Rectangle.Inflate%2A> 和 <xref:System.Drawing.Rectangle.Offset%2A> 方法更改矩形的大小和位置。 <xref:System.Drawing.Rectangle.IntersectsWith%2A>方法会告诉您矩形是否与另一个给定矩形相交， <xref:System.Drawing.Rectangle.Contains%2A> 方法会告诉您给定点是否位于该矩形内。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- [如何：创建钢笔](how-to-create-a-pen.md)
- [如何：在 Windows 窗体上绘制直线](how-to-draw-a-line-on-a-windows-form.md)
- [如何：绘制轮廓形状](how-to-draw-an-outlined-shape.md)
