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
# <a name="vector-graphics-overview"></a>向量图形概述
GDI + 在坐标系统上绘制线条、矩形和其他形状。 您可以从各种坐标系统中进行选择，但默认坐标系统的原点位于左上角，且 x 轴指向右方，y 轴指向下方。 默认坐标系统中的度量单位是像素。  
  
## <a name="the-building-blocks-of-gdi"></a>GDI + 的构建基块  
 ![矢量图形](./media/aboutgdip02-art01.gif "AboutGdip02_Art01")  
  
 计算机监视器在一组名为图片元素或像素的圆点上创建其显示。 屏幕上显示的像素数因监视器的不同而异，并且单个监视器上显示的像素数通常可以配置为用户的某些范围。  
  
 ![矢量图形](./media/aboutgdip02-art02.gif "AboutGdip02_Art02")  
  
 使用 GDI + 绘制线条、矩形或曲线时，需要提供有关要绘制的项的某些关键信息。 例如，可以通过提供两个点来指定线条，还可以通过提供一个点、高度和宽度来指定矩形。 GDI + 与显示器驱动程序软件结合使用，以确定必须打开哪些像素以显示线条、矩形或曲线。 下图显示了已打开以从点 (4，2) 到点 (12，8) 点的线条。  
  
 ![矢量图形](./media/aboutgdip02-art03.gif "AboutGdip02_Art03")  
  
 随着时间的推移，某些基本构建基块已证明最适用于创建二维图片。 下面的列表中提供了这些构建基块，它们均受 GDI + 支持：  
  
- 线条  
  
- 矩形  
  
- 椭圆  
  
- 形成  
  
- Polygon（多边形）  
  
- 基数样条  
  
- 贝塞尔曲线样条  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a>使用图形对象进行绘制的方法  
 <xref:System.Drawing.Graphics>Gdi + 中的类提供以下方法用于绘制上一列表中的项： <xref:System.Drawing.Graphics.DrawLine%2A> 、 <xref:System.Drawing.Graphics.DrawRectangle%2A> 、 <xref:System.Drawing.Graphics.DrawEllipse%2A> 、 <xref:System.Drawing.Graphics.DrawPolygon%2A> 、 <xref:System.Drawing.Graphics.DrawArc%2A> 、 <xref:System.Drawing.Graphics.DrawCurve%2A> (用于基数样条) 和 <xref:System.Drawing.Graphics.DrawBezier%2A> 。 其中每个方法都是重载的;也就是说，每个方法都支持多个不同的参数列表。 例如，方法的一个变体 <xref:System.Drawing.Graphics.DrawLine%2A> 接收一个 <xref:System.Drawing.Pen> 对象和四个整数，而该方法的另一个变体 <xref:System.Drawing.Graphics.DrawLine%2A> 接收 <xref:System.Drawing.Pen> 对象和两个 <xref:System.Drawing.Point> 对象。  
  
 绘制线条、矩形和贝塞尔样条的方法具有在单个调用中绘制若干项的复数伴生方法： <xref:System.Drawing.Graphics.DrawLines%2A> 、 <xref:System.Drawing.Graphics.DrawRectangles%2A> 和 <xref:System.Drawing.Graphics.DrawBeziers%2A> 。 此外，该 <xref:System.Drawing.Graphics.DrawCurve%2A> 方法还具有一个伴随方法， <xref:System.Drawing.Graphics.DrawClosedCurve%2A> 该方法通过将曲线的结束点连接到起始点来关闭曲线。  
  
 类的所有绘图方法均 <xref:System.Drawing.Graphics> 与对象结合使用 <xref:System.Drawing.Pen> 。 若要绘制任何内容，你必须至少创建两个对象： <xref:System.Drawing.Graphics> 对象和 <xref:System.Drawing.Pen> 对象。 <xref:System.Drawing.Pen>对象存储要绘制的项的属性，如线条宽度和颜色。 <xref:System.Drawing.Pen>对象作为一个自变量传递给绘图方法。 例如，方法的一种变体 <xref:System.Drawing.Graphics.DrawLine%2A> 接收一个 <xref:System.Drawing.Pen> 对象和四个整数，如下面的示例所示，它绘制一个宽度为100的矩形，高度为50，左上角的 (20，10) ：  
  
 [!code-csharp[LinesCurvesAndShapes#11](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [直线、曲线和图形](lines-curves-and-shapes.md)
- [如何：创建用于绘制的 Graphics 对象](how-to-create-graphics-objects-for-drawing.md)
