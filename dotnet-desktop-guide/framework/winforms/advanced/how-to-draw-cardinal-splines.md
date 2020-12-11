---
title: 如何：绘制基数自由绘制曲线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
ms.openlocfilehash: 12e938567d529b33ead93e081d380a650a803f23
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971467"
---
# <a name="how-to-draw-cardinal-splines"></a>如何：绘制基数自由绘制曲线
基数样条是通过一组给定的点平滑传递的曲线。 若要绘制基数样条，请创建一个 <xref:System.Drawing.Graphics> 对象并将一个点数组的地址传递给该 <xref:System.Drawing.Graphics.DrawCurve%2A> 方法。  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a>绘制 Bell-Shaped 基数样条  
  
- 下面的示例绘制一个通过五个指定点的钟形基数样条。 下图显示了曲线和五个点。  
  
     ![显示钟形基数样条的关系图。](./media/how-to-draw-cardinal-splines/bell-shaped-cardinal-spline.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a>绘制闭合基数样条  
  
- 使用 <xref:System.Drawing.Graphics.DrawClosedCurve%2A> 类的方法 <xref:System.Drawing.Graphics> 绘制闭合基数样条。 在闭合基数样条曲线中，曲线继续经过数组中的最后一个点，并与数组中的第一个点相连。 下面的示例绘制经过六个指定点的闭合基数样条。 下图显示了闭合样条以及六个点：  
  
 ![显示闭合基数样条的关系图。](./media/how-to-draw-cardinal-splines/closed-cardinal-spine.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a>更改基数样条曲线的弯曲  
  
- 通过向方法传递张力参数来更改基数样条曲线的弯曲方式 <xref:System.Drawing.Graphics.DrawCurve%2A> 。 下面的示例绘制三个通过同一组点的基数样条。 下图显示了三条曲线及其张力值。 请注意，当张力为0时，点由直线连接。  
  
 ![显示三个基数样条的关系图。](./media/how-to-draw-cardinal-splines/three-cardinal-splines.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它们需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅

- [直线、曲线和图形](lines-curves-and-shapes.md)
- [构造并绘制曲线](constructing-and-drawing-curves.md)
