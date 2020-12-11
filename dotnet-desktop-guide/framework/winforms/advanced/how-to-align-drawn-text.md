---
title: 如何：对齐绘制的文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
ms.openlocfilehash: 3a569284a1c4b43fa7264e0354934436f95b8dc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970337"
---
# <a name="how-to-align-drawn-text"></a>如何：对齐绘制的文本
执行自定义绘制时，可能经常需要在窗体或控件上居中绘制文本。 您可以 <xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 通过创建正确的格式设置对象并设置相应的格式标志来轻松地对齐使用或方法绘制的文本。  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a>若要用 GDI + (System.drawing.graphics.drawstring 绘制居中文本)   
  
1. 使用 <xref:System.Drawing.StringFormat> 带有相应方法的 <xref:System.Drawing.Graphics.DrawString%2A> 来指定居中文本。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a>用 GDI (DrawText 来绘制居中文本)   
  
1. 使用 <xref:System.Windows.Forms.TextFormatFlags> 枚举进行包装，同时使用适当的方法垂直和水平居中文本 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的代码示例旨在与 Windows 窗体一起使用，并且它们需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，后者是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>另请参阅

- [如何：用 GDI 绘制文本](how-to-draw-text-with-gdi.md)
- [使用字体和文本](using-fonts-and-text.md)
- [如何：构造字体系列和字体](how-to-construct-font-families-and-fonts.md)
