---
title: 在 GDI+ 中裁切和缩放图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, scaling images
- GDI+, cropping images
- images [Windows Forms], cropping
- compressing data [Windows Forms], images
- images [Windows Forms], expansion
- images [Windows Forms], scaling
- rectangles [Windows Forms], source
- rectangles [Windows Forms], destination
- images [Windows Forms], compression
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
ms.openlocfilehash: c3cdb06e99770808461f9266fb5f07df9074149b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970678"
---
# <a name="cropping-and-scaling-images-in-gdi"></a>在 GDI+ 中裁切和缩放图像
可以使用类的 <xref:System.Drawing.Graphics.DrawImage%2A> 方法 <xref:System.Drawing.Graphics> 来绘制和定位矢量图像和光栅图像。 <xref:System.Drawing.Graphics.DrawImage%2A> 是一种重载方法，因此可以通过多种方式为其提供参数。  
  
## <a name="drawimage-variations"></a>DrawImage 变体  
 方法的一个变体 <xref:System.Drawing.Graphics.DrawImage%2A> 接收 <xref:System.Drawing.Bitmap> 和一个 <xref:System.Drawing.Rectangle> 。 该矩形指定绘制操作的目标;也就是说，它指定要在其中绘制图像的矩形。 如果目标矩形的大小与原始图像的大小不同，则对图像进行缩放以适合目标矩形。 下面的代码示例演示如何绘制三次同一图像：一次不进行缩放，一次使用扩展，一次使用压缩：  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 下图显示了三个图片。  
  
 ![缩放](./media/aboutgdip03-art06.gif "AboutGdip03_Art06")  
  
 此方法的某些变体 <xref:System.Drawing.Graphics.DrawImage%2A> 具有源矩形参数和目标矩形参数。 源矩形参数指定要绘制的原始图像部分。 目标矩形指定要在其中绘制图像的一部分的矩形。 如果目标矩形的大小不同于源矩形的大小，则会缩放图片以适应目标矩形。  
  
 下面的代码示例演示如何 <xref:System.Drawing.Bitmap> 从文件 Runner.jpg 构造。 在 (0，0) 绘制整个图像而不进行缩放。 然后，图像的一小部分绘制两次：一次使用压缩，一次使用扩展。  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 下图显示了未缩放的图像，以及压缩和扩展的图像部分。  
  
 ![裁剪和缩放](./media/aboutgdip03-art07.gif "AboutGdip03_Art07")  
  
## <a name="see-also"></a>另请参阅

- [图像、位图和图元文件](images-bitmaps-and-metafiles.md)
- [使用图像、位图、图标和图元文件](working-with-images-bitmaps-icons-and-metafiles.md)
