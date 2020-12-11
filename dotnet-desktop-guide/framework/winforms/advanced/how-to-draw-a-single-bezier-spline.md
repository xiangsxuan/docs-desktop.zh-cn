---
title: 如何：绘制单个 B&#233;zier 样条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: ebb53e7df979a553ed4a44deba34345c9ecac772
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971477"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a>如何：绘制单个 B&#233;zier 样条
贝塞尔样条由四个点定义：一个开始点、两个控制点和一个终结点。  
  
## <a name="example"></a>示例  
 下面的示例使用开始点 (10、100) 和终结点 (200，100) 绘制贝塞尔样条。 控制点为 (100、10)  (150、150) 。  
  
 下图显示了生成的贝塞尔曲线及其起点、控制点和端点。 该图还显示样条的凸球面，这是通过将四个点与直线连接而形成的多边形。  
  
 ![贝塞尔曲线的插图。](./media/how-to-draw-a-single-bezier-spline/bezier-spline-illustration.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [GDI+ 中的贝塞尔自由绘制曲线](bezier-splines-in-gdi.md)
- [如何：绘制一系列贝塞尔自由绘制曲线](how-to-draw-a-sequence-of-bezier-splines.md)
