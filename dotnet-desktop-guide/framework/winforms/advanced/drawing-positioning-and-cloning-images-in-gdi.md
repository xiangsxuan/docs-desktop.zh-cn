---
title: 在 GDI+ 中绘制、定位和克隆图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- raster images [Windows Forms]
- images [Windows Forms], positioning
- drawing [Windows Forms], images
- drawing [Windows Forms], raster images
- images [Windows Forms], cloning
- images [Windows Forms], drawing
- GDI+, drawing images
- GDI+, cloning images
- GDI+, positioning images
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
ms.openlocfilehash: b5f98e7bdef9ff8ed0a4cd0e040cb92a31f30503
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970826"
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a>在 GDI+ 中绘制、定位和克隆图像
可以使用 <xref:System.Drawing.Bitmap> 类来加载和显示光栅图像，还可以使用 <xref:System.Drawing.Imaging.Metafile> 类加载和显示矢量图像。 <xref:System.Drawing.Bitmap>和 <xref:System.Drawing.Imaging.Metafile> 类继承自 <xref:System.Drawing.Image> 类。 若要显示矢量图像，需要 <xref:System.Drawing.Graphics> 类和的实例 <xref:System.Drawing.Imaging.Metafile> 。 若要显示光栅图像，需要 <xref:System.Drawing.Graphics> 类和的实例 <xref:System.Drawing.Bitmap> 。 类的实例 <xref:System.Drawing.Graphics> 提供了 <xref:System.Drawing.Graphics.DrawImage%2A> 方法，该方法将 <xref:System.Drawing.Imaging.Metafile> 或 <xref:System.Drawing.Bitmap> 作为参数接收。  
  
## <a name="file-types-and-cloning"></a>文件类型和克隆  
 下面的代码示例演示如何 <xref:System.Drawing.Bitmap> 从文件 Climber.jpg 构造，并显示位图。 在第二个和第三个参数中指定了图像的左上角的目标点， (10，10) 。  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 下图显示了该图像。  
  
 ![图像示例](./media/aboutgdip03-art04.gif "AboutGdip03_Art04")  
  
 可以 <xref:System.Drawing.Bitmap> 从各种图形文件格式构造对象： BMP、GIF、JPEG、EXIF、PNG、TIFF 和图标。  
  
 下面的代码示例演示如何 <xref:System.Drawing.Bitmap> 从各种文件类型构造对象，然后显示位图。  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 <xref:System.Drawing.Bitmap>类提供了一个 <xref:System.Drawing.Bitmap.Clone%2A> 方法，您可以使用该方法创建现有的副本 <xref:System.Drawing.Bitmap> 。 <xref:System.Drawing.Bitmap.Clone%2A>方法具有一个源矩形参数，可用于指定要复制的原始位图部分。 下面的代码示例演示如何 <xref:System.Drawing.Bitmap> 通过克隆现有的上半部分来创建 <xref:System.Drawing.Bitmap> 。 然后绘制两个图像。  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 下图显示了这两个图像。  
  
 ![裁剪](./media/aboutgdip03-art05.gif "AboutGdip03_Art05")  
  
## <a name="see-also"></a>另请参阅

- [图像、位图和图元文件](images-bitmaps-and-metafiles.md)
- [如何：创建用于绘制的 Graphics 对象](how-to-create-graphics-objects-for-drawing.md)
- [使用图像、位图、图标和图元文件](working-with-images-bitmaps-icons-and-metafiles.md)
