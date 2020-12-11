---
title: 如何：创建垂直文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- Windows Forms, drawing vertical text
- strings [Windows Forms], drawing vertical
- vertical text [Windows Forms], drawing
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
ms.openlocfilehash: 86401342625f593945b801f7619ef9ca9681317c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970316"
---
# <a name="how-to-create-vertical-text"></a>如何：创建垂直文本
可以使用 <xref:System.Drawing.StringFormat> 对象指定垂直绘制文本，而不是水平绘制。  
  
## <a name="example"></a>示例  
 下面的示例将值分配 <xref:System.Drawing.StringFormatFlags.DirectionVertical> 给 <xref:System.Drawing.StringFormat.FormatFlags%2A> 对象的属性 <xref:System.Drawing.StringFormat> 。 该 <xref:System.Drawing.StringFormat> 对象传递给类的 <xref:System.Drawing.Graphics.DrawString%2A> 方法 <xref:System.Drawing.Graphics> 。 值 <xref:System.Drawing.StringFormatFlags.DirectionVertical> 是枚举的成员 <xref:System.Drawing.StringFormatFlags> 。  
  
 下图显示了垂直文本：
  
 ![显示垂直字体文本的图形。](./media/how-to-create-vertical-text/vertical-font-text-graphic.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>编译代码  
  
- 前面的示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，这是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>另请参阅

- [如何：用 GDI 绘制文本](how-to-draw-text-with-gdi.md)
