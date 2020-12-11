---
title: 如何：使用钢笔绘制矩形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
ms.openlocfilehash: cd5d965f8b92d15cdeb3049330d9b3cc0de893b2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971391"
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a>如何：使用钢笔绘制矩形
若要绘制矩形，需要 <xref:System.Drawing.Graphics> 对象和 <xref:System.Drawing.Pen> 对象。 <xref:System.Drawing.Graphics>对象提供 <xref:System.Drawing.Graphics.DrawRectangle%2A> 方法，而 <xref:System.Drawing.Pen> 对象存储行的功能，如颜色和宽度。  
  
## <a name="example"></a>示例  
 下面的示例在 (10，10) 绘制其左上角的矩形。 矩形的宽度为100，高度为50。 传递给构造函数的第二个参数 <xref:System.Drawing.Pen.%23ctor%2A> 指示钢笔宽度为5像素。  
  
 绘制矩形时，笔位于矩形边界上。 由于笔宽度为5，矩形的边将绘制5个像素宽，这样，在边界本身绘制1个像素，在内部绘制2个像素，在外部绘制2个像素。 有关笔对齐的详细信息，请参阅 [如何：设置笔宽度和对齐方式](how-to-set-pen-width-and-alignment.md)。  
  
 下图显示了生成的矩形。 虚线显示画笔的宽度为1个像素时应绘制的矩形的位置。 矩形左上角的放大视图显示黑色黑色线条在这些点线上居中。  
  
 ![显示带有黑色和虚线的绘制矩形的屏幕截图。](./media/how-to-use-a-pen-to-draw-rectangles/drawn-rectangle-black-lines-dotted-lines.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅

- [使用笔绘制线条和形状](using-a-pen-to-draw-lines-and-shapes.md)
