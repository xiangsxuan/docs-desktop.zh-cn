---
title: 如何：绘制 B&#233;zier 样条的序列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
ms.openlocfilehash: 976787f5830282a581d05a9c24d1f83dceca4b25
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971478"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a>如何：绘制 B&#233;zier 样条的序列
您可以使用 <xref:System.Drawing.Graphics.DrawBeziers%2A> 类的方法 <xref:System.Drawing.Graphics> 来绘制一系列已连接的贝塞尔曲线。  
  
## <a name="example"></a>示例  
 下面的示例绘制一个曲线，其中包含两个连接的贝塞尔样条。 第一条贝塞尔曲线的端点是第二条贝塞尔曲线的起点。  
  
 下图显示了已连接的曲线以及七个点：  
  
 ![显示连接的曲线以及七个点的图形。](./media/how-to-draw-a-sequence-of-bezier-splines/bezier-spline-seven-points.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅

- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
- [GDI+ 中的贝塞尔自由绘制曲线](bezier-splines-in-gdi.md)
- [构造并绘制曲线](constructing-and-drawing-curves.md)
