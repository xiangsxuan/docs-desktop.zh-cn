---
title: 如何：在缩放期间使用内插模式控制图像质量
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: ab0ff93b3ee26467c0de448efd31b698167f95c2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971637"
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a>如何：在缩放期间使用内插模式控制图像质量
对象的内插模式 <xref:System.Drawing.Graphics> 影响 GDI + 缩放 (拉伸和收缩) 图像的方式。 <xref:System.Drawing.Drawing2D.InterpolationMode>枚举定义了几种内插模式，其中的一些模式显示在下面的列表中：  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 若要拉伸图像，必须将原始图像中的每个像素映射到较大图像中的一组像素。 若要收缩图像，必须将原始图像中的像素组映射到较小图像中的单个像素。 执行这些映射的算法的有效性决定了缩放图像的质量。 生成高质量缩放图像的算法往往需要更长的处理时间。 在上面的列表中，是最高 <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> 质量的模式，并且 <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> 是最高质量的模式。  
  
 若要设置内插模式，请将枚举的一个成员分配 <xref:System.Drawing.Drawing2D.InterpolationMode> 给 <xref:System.Drawing.Graphics.InterpolationMode%2A> 对象的属性 <xref:System.Drawing.Graphics> 。  
  
## <a name="example"></a>示例  
 下面的示例绘制一个图像，然后使用三个不同的内插模式缩小图像。  
  
 下图显示了原始图像和三个较小的图像。  
  
 ![显示带有各种内插设置的图像的屏幕截图。](./media/how-to-use-interpolation-mode-to-control-image-quality-during-scaling/varied-interpolation-settings.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅

- [图像、位图和图元文件](images-bitmaps-and-metafiles.md)
- [使用图像、位图、图标和图元文件](working-with-images-bitmaps-icons-and-metafiles.md)
