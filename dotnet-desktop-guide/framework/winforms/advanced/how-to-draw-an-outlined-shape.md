---
title: 如何：绘制轮廓形状
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.DrawEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- drawing [Windows Forms], shapes
- circular shapes
- forms [Windows Forms], drawing circular shapes
- circles
- outlined shapes [Windows Forms], examples
- outlined shapes [Windows Forms], drawing
- drawing [Windows Forms], circular shapes
- shapes [Windows Forms], drawing
ms.assetid: f4f9214c-607e-407d-8cdd-6549f0278451
ms.openlocfilehash: 019bbc19cc4b26c42f8539eccd93ec4ff87fab12
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971473"
---
# <a name="how-to-draw-an-outlined-shape"></a>如何：绘制轮廓形状
此示例在窗体上绘制空心椭圆和矩形。  
  
## <a name="example"></a>示例  
 [!code-cpp[System.Drawing.ConceptualHowTos#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#6)]
 [!code-csharp[System.Drawing.ConceptualHowTos#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#6)]
 [!code-vb[System.Drawing.ConceptualHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a>编译代码  
 不能在事件处理程序中调用此方法 <xref:System.Windows.Forms.Form.Load> 。 如果窗体调整或被其他窗体遮住，则不会重新绘制所绘制的内容。 若要自动重绘内容，应重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法。  
  
## <a name="robust-programming"></a>可靠编程  
 应始终对 <xref:System.IDisposable.Dispose%2A> 使用系统资源的任何对象（如 <xref:System.Drawing.Pen> 和对象）调用 <xref:System.Drawing.Graphics> 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Graphics.DrawEllipse%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Drawing.Graphics.DrawRectangle%2A>
- [图形编程入门](getting-started-with-graphics-programming.md)
- [使用笔绘制线条和形状](using-a-pen-to-draw-lines-and-shapes.md)
- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
