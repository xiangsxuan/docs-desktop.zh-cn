---
title: 如何：设置钢笔的宽度和对齐方式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
ms.openlocfilehash: 1f1ea6e8ef0b94aa46a4bf8177d59e59297d6e3f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971664"
---
# <a name="how-to-set-pen-width-and-alignment"></a>如何：设置钢笔的宽度和对齐方式
创建时 <xref:System.Drawing.Pen> ，可以将笔宽度作为参数的一个参数提供给构造函数。 还可以通过类的属性来更改笔的宽度 <xref:System.Drawing.Pen.Width%2A> <xref:System.Drawing.Pen> 。  
  
 理论线条的宽度为0。 绘制线条宽度为1个像素时，这些像素将在理论线条上居中。 如果绘制的线条宽度超过一个像素，则这些像素将在理论线条上居中，或显示在理论线条的一侧。 您可以设置的 "笔对齐" 属性 <xref:System.Drawing.Pen> ，以确定使用该笔绘制的像素相对于理论线条的位置。  
  
 <xref:System.Drawing.Drawing2D.PenAlignment.Center> <xref:System.Drawing.Drawing2D.PenAlignment.Outset> <xref:System.Drawing.Drawing2D.PenAlignment.Inset> 下面的代码示例中显示的值是枚举的成员 <xref:System.Drawing.Drawing2D.PenAlignment> 。  
  
 下面的代码示例绘制两次两次：一次使用宽度为1的黑色钢笔，一次使用宽度为10的绿色钢笔。  
  
### <a name="to-vary-the-width-of-a-pen"></a>改变笔的宽度  
  
- 将属性的值设置 <xref:System.Drawing.Pen.Alignment%2A> 为 <xref:System.Drawing.Drawing2D.PenAlignment.Center> (默认) ，以指定用绿色钢笔绘制的像素将在理论线条上居中。 下图显示了生成的行。  
  
     ![带有绿色突出显示的黑色细线。](./media/how-to-set-pen-width-and-alignment/green-pixels-centered-line.gif)  
  
     下面的代码示例绘制两次矩形：一次使用宽度为1的黑色钢笔，一次使用宽度为10的绿色钢笔。  
  
     [!code-csharp[System.Drawing.UsingAPen#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a>更改笔的对齐方式  
  
- 将属性的值设置 <xref:System.Drawing.Pen.Alignment%2A> 为， <xref:System.Drawing.Drawing2D.PenAlignment.Center> 以指定用绿色笔绘制的像素将在矩形边界上居中。  
  
     下图显示了生成的矩形：
  
     ![使用带有绿色突出显示的黑色细线条绘制的矩形。](./media/how-to-set-pen-width-and-alignment/green-pixels-centered-rectangle.gif)  
  
     [!code-csharp[System.Drawing.UsingAPen#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a>创建嵌入笔  
  
- 通过修改上述代码示例中的第三条语句来更改绿色画笔的对齐方式，如下所示：  
  
     [!code-csharp[System.Drawing.UsingAPen#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     现在，在矩形的内部显示宽绿色线条中的像素，如下图所示：
  
     ![用黑色线条绘制的矩形，其中包含宽绿色线条。](./media/how-to-set-pen-width-and-alignment/green-pixels-inside-rectangle.gif)  
  
## <a name="see-also"></a>另请参阅

- [使用笔绘制线条和形状](using-a-pen-to-draw-lines-and-shapes.md)
- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
