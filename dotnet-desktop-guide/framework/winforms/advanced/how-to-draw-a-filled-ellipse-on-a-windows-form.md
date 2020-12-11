---
title: 如何：在 Windows 窗体上绘制实心椭圆
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- circular shapes
- drawing [Windows Forms], ellipses
- shapes [Windows Forms], drawing
- forms [Windows Forms], drawing ellipses
ms.assetid: 781db806-950d-4c5b-b022-493f7fd0c4a8
ms.openlocfilehash: 2e7be3f2c4c710bb24568dd2e70f6f5cc4706c63
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970306"
---
# <a name="how-to-draw-a-filled-ellipse-on-a-windows-form"></a>如何：在 Windows 窗体上绘制实心椭圆
此示例在窗体上绘制实心椭圆。  
  
## <a name="example"></a>示例  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 不能在事件处理程序中调用此方法 <xref:System.Windows.Forms.Form.Load> 。 如果窗体调整或被其他窗体遮住，则不会重新绘制所绘制的内容。 若要自动重绘内容，应重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法。  
  
## <a name="robust-programming"></a>可靠编程  
 应始终对 <xref:System.IDisposable.Dispose%2A> 使用系统资源的任何对象（如 <xref:System.Drawing.Brush> 和对象）调用 <xref:System.Drawing.Graphics> 。  
  
## <a name="see-also"></a>另请参阅

- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
- [图形编程入门](getting-started-with-graphics-programming.md)
- [Alpha 混合线条和填充](alpha-blending-lines-and-fills.md)
- [使用画笔填充形状](using-a-brush-to-fill-shapes.md)
