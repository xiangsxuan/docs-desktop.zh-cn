---
title: B&#233;GDI + 中的 zier 样条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
ms.openlocfilehash: ff4e9eb18610b70c88e057d3d44020321bbb9f4f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970366"
---
# <a name="b233zier-splines-in-gdi"></a>B&#233;GDI + 中的 zier 样条
贝塞尔样条是由四个点指定的曲线：两个端点 (p1 和 p2) ，两个控制点 (C1 和 c2) 。 曲线从 p1 开始，到 p2 结束。 曲线不通过控制点，但控制点作为磁体，在某些方向上拉动曲线并影响曲线弯曲的方式。 下图显示了一条贝塞尔曲线及其终结点和控制点。  
  
 ![贝塞尔曲线](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")  
  
 曲线从 p1 开始向控制点 c1 方向移动。 P1 上曲线的切线是从 p1 绘制到 c1 的直线。 终结点 p2 处的切线是从 c2 到 p2 的直线。  
  
## <a name="drawing-bzier-splines"></a>绘制贝塞尔样条  
 若要绘制贝塞尔曲线，需要 <xref:System.Drawing.Graphics> 类和的实例 <xref:System.Drawing.Pen> 。 类的实例 <xref:System.Drawing.Graphics> 提供 <xref:System.Drawing.Graphics.DrawBezier%2A> 方法，并 <xref:System.Drawing.Pen> 存储用于呈现曲线的线条的属性，例如宽度和颜色。 <xref:System.Drawing.Pen>作为参数之一传递给 <xref:System.Drawing.Graphics.DrawBezier%2A> 方法。 传递给方法的其余参数 <xref:System.Drawing.Graphics.DrawBezier%2A> 是终结点和控制点。 下面的示例使用起点 (0，0) ，控制点 (40，20) ， (80、150) 和结束点 (100，10) 绘制贝塞尔样条：  
  
 [!code-csharp[LinesCurvesAndShapes#71](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 下图显示了曲线、控制点和两条切线。  
  
 ![贝塞尔曲线](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")  
  
 贝塞尔样条最初由圣皮埃尔 Bezier 开发，以实现汽车行业的设计。 由于它们已经过验证，可在多种类型的计算机辅助设计中使用，并且还用于定义字体的轮廓。 贝塞尔样条可以产生各种形状，下图显示了其中的一部分。  
  
 ![路径](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [直线、曲线和图形](lines-curves-and-shapes.md)
- [构造并绘制曲线](constructing-and-drawing-curves.md)
- [如何：创建用于绘制的 Graphics 对象](how-to-create-graphics-objects-for-drawing.md)
- [如何：创建钢笔](how-to-create-a-pen.md)
