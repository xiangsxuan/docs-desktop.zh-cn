---
title: 如何：用交错线图案填充形状
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: b80708f0ce722b1809fe49190639231e7e4c8329
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971701"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a>如何：用交错线图案填充形状
阴影模式是从两种颜色组成的：一个用于背景，另一个用于在背景上形成图案的线条。 若要使用阴影模式填充闭合形状，请使用 <xref:System.Drawing.Drawing2D.HatchBrush> 对象。 下面的示例演示如何使用阴影模式填充椭圆：  
  
## <a name="example"></a>示例  
 <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A>构造函数采用三个参数：阴影样式、阴影线颜色以及背景颜色。 阴影样式参数可以是枚举中的任何值 <xref:System.Drawing.Drawing2D.HatchStyle> 。 枚举中的元素超过50个 <xref:System.Drawing.Drawing2D.HatchStyle> ; 下面的列表中显示了其中的几个元素：  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 下图显示了实心椭圆。  
  
  ![用阴影模式填充的椭圆外观的屏幕截图。](./media/how-to-fill-a-shape-with-a-hatch-pattern/ellipse-filled-hatch.png "hatch1")
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅

- [使用画笔填充形状](using-a-brush-to-fill-shapes.md)
