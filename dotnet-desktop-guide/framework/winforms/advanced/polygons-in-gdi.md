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
# <a name="polygons-in-gdi"></a>GDI+ 中的多边形
多边形是具有三个或更多直线的闭合形状。 例如，三角形是具有三个边的多边形，矩形是具有四个边的多边形，而五边是具有五个边的多边形。 下图显示了多个多边形。  
  
 ![Polygon（多边形）](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")  
  
## <a name="drawing-a-polygon"></a>绘制多边形  
 若要绘制多边形，需要 <xref:System.Drawing.Graphics> 对象、 <xref:System.Drawing.Pen> 对象以及 <xref:System.Drawing.Point> (或 <xref:System.Drawing.PointF>) 对象的数组。 <xref:System.Drawing.Graphics>对象提供 <xref:System.Drawing.Graphics.DrawPolygon%2A> 方法。 <xref:System.Drawing.Pen>对象存储用于呈现多边形的线条的属性，例如宽度和颜色，对象的数组 <xref:System.Drawing.Point> 存储要通过直线连接的点。 <xref:System.Drawing.Pen>对象和 <xref:System.Drawing.Point> 对象数组作为参数传递给 <xref:System.Drawing.Graphics.DrawPolygon%2A> 方法。 下面的示例绘制一个三边多边形。 请注意，只有三个点 `myPointArray` ： (0，0) ， (50，30) ， (30，60) 。 <xref:System.Drawing.Graphics.DrawPolygon%2A>方法通过绘制一条从 (30，60) 返回到起始点 (0，0) 来自动关闭多边形。  
  
 [!code-csharp[LinesCurvesAndShapes#111](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 下图显示了多边形。  
  
 ![多边形](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [直线、曲线和图形](lines-curves-and-shapes.md)
- [如何：创建钢笔](how-to-create-a-pen.md)
