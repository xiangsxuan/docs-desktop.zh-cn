---
title: 如何：联接线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
ms.openlocfilehash: 362ce0c701d6e5f640fecd143a60cf471045629c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971692"
---
# <a name="how-to-join-lines"></a>如何：联接线
行联接是由两行构成的通用区域，它们的结束时间都达到或重叠。 GDI + 提供三个线条联接样式：斜接、凹凸和圆形。 行联接样式是类的属性 <xref:System.Drawing.Pen> 。 为对象指定线条联接样式时 <xref:System.Drawing.Pen> ，该联接样式将应用于 <xref:System.Drawing.Drawing2D.GraphicsPath> 使用该钢笔绘制的任何对象中的所有连接行。  
  
 下图显示了斜切行联接示例的结果。  
  
 ![显示联接线的插图。](./media/how-to-join-lines/joined-beveled-lines.gif)  
  
## <a name="example"></a>示例  
 您可以通过使用类的属性指定行联接样式 <xref:System.Drawing.Pen.LineJoin%2A> <xref:System.Drawing.Pen> 。 该示例演示了水平线和竖线之间的斜切线条联接。 在下面的代码中，赋给属性的值 <xref:System.Drawing.Drawing2D.LineJoin.Bevel> <xref:System.Drawing.Pen.LineJoin%2A> 是枚举的成员 <xref:System.Drawing.Drawing2D.LineJoin> 。 枚举的其他成员 <xref:System.Drawing.Drawing2D.LineJoin> 为 <xref:System.Drawing.Drawing2D.LineJoin.Miter> 和 <xref:System.Drawing.Drawing2D.LineJoin.Round> 。  
  
 [!code-csharp[System.Drawing.UsingAPen#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅

- [使用笔绘制线条和形状](using-a-pen-to-draw-lines-and-shapes.md)
