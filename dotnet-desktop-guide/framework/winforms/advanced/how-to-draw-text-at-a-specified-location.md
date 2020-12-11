---
title: 如何：在指定位置绘制文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text at a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
ms.openlocfilehash: 0c36b00e4f6f71f0ecf8042853bb8e99e57854da
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971463"
---
# <a name="how-to-draw-text-at-a-specified-location"></a>如何：在指定位置绘制文本
执行自定义绘制时，可以在从指定点开始的单个水平行中绘制文本。 您可以使用 <xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Drawing.Graphics> 采用或参数的类的重载方法，以这种方式绘制文本 <xref:System.Drawing.Point> <xref:System.Drawing.PointF> 。 <xref:System.Drawing.Graphics.DrawString%2A>方法还需要 <xref:System.Drawing.Brush> 和<xref:System.Drawing.Font>  
  
 你还可以使用的 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 重载方法，该方法 <xref:System.Windows.Forms.TextRenderer> 采用 <xref:System.Drawing.Point> 。 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 还需要 <xref:System.Drawing.Color> 和 <xref:System.Drawing.Font> 。  
  
 下图显示使用重载方法时在指定点绘制的文本的输出 <xref:System.Drawing.Graphics.DrawString%2A> 。  
  
 ![显示指定点文本输出的屏幕截图。](./media/how-to-draw-text-at-a-specified-location/font-text-specified-point.png)  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>使用 GDI + 绘制文本行  
  
1. 使用 <xref:System.Drawing.Graphics.DrawString%2A> 方法，传递所需的文本、、 <xref:System.Drawing.Point> 、 <xref:System.Drawing.PointF> <xref:System.Drawing.Font> 和 <xref:System.Drawing.Brush> 。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>使用 GDI 绘制一行文本  
  
1. 使用 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 方法，传递所需的文本、、 <xref:System.Drawing.Point> <xref:System.Drawing.Font> 和 <xref:System.Drawing.Color> 。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例需要：  
  
- <xref:System.Windows.Forms.PaintEventArgs>  `e`，它是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>另请参阅

- [如何：用 GDI 绘制文本](how-to-draw-text-with-gdi.md)
- [使用字体和文本](using-fonts-and-text.md)
- [如何：构造字体系列和字体](how-to-construct-font-families-and-fonts.md)
- [如何：在矩形中绘制换行文本](how-to-draw-wrapped-text-in-a-rectangle.md)
