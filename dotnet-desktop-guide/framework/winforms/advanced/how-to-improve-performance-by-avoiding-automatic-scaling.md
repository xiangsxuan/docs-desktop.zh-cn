---
title: 如何：通过避免自动缩放来改善性能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic scaling
- images [Windows Forms], improving performance
- images [Windows Forms], using without automatic scaling
- performance [Windows Forms], improving image
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
ms.openlocfilehash: dd1a1545dce33de1ce11938db8495ebf311dadda
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971443"
---
# <a name="how-to-improve-performance-by-avoiding-automatic-scaling"></a>如何：通过避免自动缩放来改善性能
GDI + 可以在绘图时自动缩放图像，这会降低性能。 或者，您可以通过将目标矩形的尺寸传递给方法来控制图像的缩放 <xref:System.Drawing.Graphics.DrawImage%2A> 。  
  
 例如，以下对方法的调用 <xref:System.Drawing.Graphics.DrawImage%2A> 指定 (50，30) 的左上角，但不指定目标矩形。  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 尽管这是最简单的方法版本 <xref:System.Drawing.Graphics.DrawImage%2A> ，但它不一定是最有效的方法。 如果 GDI + 使用的分辨率通常 (每英寸96点) 不同于存储在对象中的分辨率 <xref:System.Drawing.Image> ，则 <xref:System.Drawing.Graphics.DrawImage%2A> 方法将缩放图像。 例如，假设对象的 <xref:System.Drawing.Image> 宽度为216像素，存储的水平分辨率值为每英寸72点。 由于216/72 是3， <xref:System.Drawing.Graphics.DrawImage%2A> 将缩放图像，使其宽度为3英寸，分辨率为每英寸96点。 也就是说， <xref:System.Drawing.Graphics.DrawImage%2A> 将显示宽度为 96x3 = 288 像素的图像。  
  
 即使屏幕分辨率不同于每英寸96点，GDI + 也可能缩放图像，就像屏幕分辨率是每英寸96点。 这是因为 GDI + <xref:System.Drawing.Graphics> 对象与设备上下文相关联，当 GDI + 查询屏幕分辨率的设备上下文时，结果通常为96，而不考虑实际屏幕分辨率。 可以通过在方法中指定目标矩形来避免自动缩放 <xref:System.Drawing.Graphics.DrawImage%2A> 。  
  
## <a name="example"></a>示例  
 下面的示例将同一图像绘制两次。 在第一种情况下，不指定目标矩形的宽度和高度，并且自动缩放图像。 在第二种情况下，将目标矩形) 的宽度和高度 (指定为与原始图像的宽度和高度相同。 下图显示了呈现两次的图像：  
  
 ![显示具有缩放纹理的图像的屏幕截图。](./media/how-to-improve-performance-by-avoiding-automatic-scaling/two-scaled-texture-images.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。 将 Texture.jpg 替换为在系统中有效的映像名称和路径。  
  
## <a name="see-also"></a>另请参阅

- [图像、位图和图元文件](images-bitmaps-and-metafiles.md)
- [使用图像、位图、图标和图元文件](working-with-images-bitmaps-icons-and-metafiles.md)
