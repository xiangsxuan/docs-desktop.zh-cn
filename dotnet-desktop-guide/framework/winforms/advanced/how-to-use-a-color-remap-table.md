---
title: 如何：使用颜色重新映射表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: 360ec30563ee5001d784dc7c4ccdb50563867c29
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971395"
---
# <a name="how-to-use-a-color-remap-table"></a>如何：使用颜色重新映射表
重新映射是指根据颜色重新映射表转换图像中的颜色的过程。 颜色重新映射表是对象的数组 <xref:System.Drawing.Imaging.ColorMap> 。 <xref:System.Drawing.Imaging.ColorMap>数组中的每个对象都有一个 <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> 属性和一个 <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> 属性。  
  
 当 GDI + 绘制图像时，图像的每个像素都将与旧颜色数组进行比较。 如果像素的颜色与旧颜色匹配，则其颜色将更改为相应的新颜色。 仅为呈现更改颜色，在或对象) 中存储的图像本身 (颜色值 <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> 不会更改。  
  
 若要绘制重映射的图像，请初始化 <xref:System.Drawing.Imaging.ColorMap> 对象的数组。 将该数组传递给 <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> 对象的方法 <xref:System.Drawing.Imaging.ImageAttributes> ，然后将该对象传递 <xref:System.Drawing.Imaging.ImageAttributes> 给对象的 <xref:System.Drawing.Graphics.DrawImage%2A> 方法 <xref:System.Drawing.Graphics> 。  
  
## <a name="example"></a>示例  
 下面的示例 <xref:System.Drawing.Image> 从文件 RemapInput.bmp 创建对象。 此代码创建由单个对象组成的颜色重新映射表 <xref:System.Drawing.Imaging.ColorMap> 。 <xref:System.Drawing.Imaging.ColorMap.OldColor%2A>对象的属性 `ColorRemap` 为红色， <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> 属性为蓝色。 此图像绘制一次，无需重新映射，一次是重新映射。 重新映射过程会将所有红色像素变为蓝色。  
  
 下图显示左侧的原始图像和右侧重新映射后的图像。  
  
 ![显示原始图像和重新映射映像的屏幕截图。](./media/how-to-use-a-color-remap-table/original-image-remap-colors.png)  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅

- [对图像重新着色](recoloring-images.md)
- [图像、位图和图元文件](images-bitmaps-and-metafiles.md)
