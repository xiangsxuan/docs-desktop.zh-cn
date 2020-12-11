---
title: 如何：在矩形中绘制换行文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: ace79e45737a3ce26d8bdcd603e923c1e6040d4d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971451"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a>如何：在矩形中绘制换行文本
您可以使用 <xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Drawing.Graphics> 采用或参数的类的重载方法在矩形中绘制换行文本 <xref:System.Drawing.Rectangle> <xref:System.Drawing.RectangleF> 。 你还将使用 <xref:System.Drawing.Brush> 和 <xref:System.Drawing.Font> 。  
  
 你还可以使用 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> <xref:System.Windows.Forms.TextRenderer> 采用和参数的的重载方法在矩形中绘制换行文本 <xref:System.Drawing.Rectangle> <xref:System.Windows.Forms.TextFormatFlags> 。 你还将使用 <xref:System.Drawing.Color> 和 <xref:System.Drawing.Font> 。  
  
 下图显示使用方法时在矩形中绘制的文本的输出 <xref:System.Drawing.Graphics.DrawString%2A> ：
  
 ![使用 System.drawing.graphics.drawstring 方法时显示输出的屏幕截图。](./media/how-to-draw-wrapped-text-in-a-rectangle/drawstring-method-font-text.png)  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>使用 GDI + 在矩形中绘制换行文本  
  
1. 使用 <xref:System.Drawing.Graphics.DrawString%2A> 重载的方法，传递所需的文本、 <xref:System.Drawing.Rectangle> 或 <xref:System.Drawing.RectangleF> <xref:System.Drawing.Font> <xref:System.Drawing.Brush> 。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>使用 GDI 在矩形中绘制换行文本  
  
1. 使用 <xref:System.Windows.Forms.TextFormatFlags> 枚举值指定应使用 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 重载方法包装文本，传递所需的文本、 <xref:System.Drawing.Rectangle> <xref:System.Drawing.Font> 和 <xref:System.Drawing.Color> 。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例需要：  
  
- <xref:System.Windows.Forms.PaintEventArgs>`e`，它是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>另请参阅

- [如何：用 GDI 绘制文本](how-to-draw-text-with-gdi.md)
- [使用字体和文本](using-fonts-and-text.md)
- [如何：构造字体系列和字体](how-to-construct-font-families-and-fonts.md)
- [如何：在指定位置绘制文本](how-to-draw-text-at-a-specified-location.md)
