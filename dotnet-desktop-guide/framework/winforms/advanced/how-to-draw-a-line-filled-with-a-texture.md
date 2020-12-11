---
title: 如何：绘制填充有纹理的线条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
ms.openlocfilehash: c0f90c298f48aeb96893bb09241faddc08d8a49d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971490"
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a>如何：绘制填充有纹理的线条
您可以绘制带有纹理的线条，而不是使用纯色绘制线条。 若要绘制带有纹理的直线和曲线，请创建一个 <xref:System.Drawing.TextureBrush> 对象，并将该 <xref:System.Drawing.TextureBrush> 对象传递给 <xref:System.Drawing.Pen.%23ctor%2A> 构造函数。 与纹理画笔关联的位图用于平铺 (以不可见的方式) ，笔绘制直线或曲线时，笔的笔划会发现平铺纹理的特定像素。  
  
## <a name="example"></a>示例  
 下面的示例 <xref:System.Drawing.Bitmap> 从文件创建对象 `Texture1.jpg` 。 该位图用于构造 <xref:System.Drawing.TextureBrush> 对象，该 <xref:System.Drawing.TextureBrush> 对象用于构造 <xref:System.Drawing.Pen> 对象。 对的调用在 <xref:System.Drawing.Graphics.DrawImage%2A> (0，0) 的左上角绘制位图。 对的调用 <xref:System.Drawing.Graphics.DrawEllipse%2A> 使用 <xref:System.Drawing.Pen> 对象绘制纹理纹理。  
  
 下图显示位图和纹理纹理：  
  
 ![显示位图和纹理椭圆的屏幕截图。](./media/how-to-draw-a-line-filled-with-a-texture/bitmap-textured-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingAPen#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>编译代码  
 创建 Windows 窗体并处理窗体的 <xref:System.Windows.Forms.Control.Paint> 事件。 将前面的代码粘贴到 <xref:System.Windows.Forms.Control.Paint> 事件处理程序中。 替换 `Texture.jpg` 为系统上的有效图像。  
  
## <a name="see-also"></a>另请参阅

- [使用笔绘制线条和形状](using-a-pen-to-draw-lines-and-shapes.md)
- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
