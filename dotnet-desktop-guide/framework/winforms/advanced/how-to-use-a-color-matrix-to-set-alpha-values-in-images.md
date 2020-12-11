---
title: 如何：使用颜色矩阵设置图像中的 Alpha 值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
ms.openlocfilehash: 73e820845d040856a0ae367da8b9371ad6afa142
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971397"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a>如何：使用颜色矩阵设置图像中的 Alpha 值
<xref:System.Drawing.Bitmap>类 (，该类继承自 <xref:System.Drawing.Image> 类) ， <xref:System.Drawing.Imaging.ImageAttributes> 类提供用于获取和设置像素值的功能。 您可以使用 <xref:System.Drawing.Imaging.ImageAttributes> 类修改整个图像的 alpha 值，也可以调用 <xref:System.Drawing.Bitmap.SetPixel%2A> 类的方法 <xref:System.Drawing.Bitmap> 来修改单个像素值。  
  
## <a name="example"></a>示例  
 <xref:System.Drawing.Imaging.ImageAttributes>类具有许多可用于在呈现过程中修改图像的属性。 在下面的示例中， <xref:System.Drawing.Imaging.ImageAttributes> 对象用于将所有 alpha 值设置为80% 的值。 这是通过初始化颜色矩阵并将矩阵中的 alpha 缩放值设置为0.8 来完成的。 颜色矩阵的地址将传递给 <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> 对象的方法 <xref:System.Drawing.Imaging.ImageAttributes> ，对象将传递给对象的 <xref:System.Drawing.Imaging.ImageAttributes> <xref:System.Drawing.Graphics.DrawString%2A> 方法 <xref:System.Drawing.Graphics> 。  
  
 在呈现过程中，位图中的 alpha 值将转换为它们的80%。 这会导致图像与背景混合。 如下图所示，位图图像看起来是透明的;您可以看到它的实心黑色直线。  
  
 ![使用矩阵进行 alpha 混合的屏幕截图。](./media/how-to-use-a-color-matrix-to-set-alpha-values-in-images/alpha-blending-matrix.png "image2")  
  
 如果图像位于背景的空白部分，则图像已与白色颜色混合。 如果图像与黑色线条交叉，图像会与黑色混合。  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，这是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>另请参阅

- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
- [Alpha 混合线条和填充](alpha-blending-lines-and-fills.md)
