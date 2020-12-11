---
title: 如何：在屏幕上绘制现有位图
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
ms.openlocfilehash: 90511adf9caffe7952e270d6fe32dd85162a29d7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971472"
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a>如何：在屏幕上绘制现有位图
可以轻松地在屏幕上绘制现有的图像。 首先，需要 <xref:System.Drawing.Bitmap> 使用采用文件名的位图构造函数创建对象 <xref:System.Drawing.Bitmap.%23ctor%28System.String%29> 。 此构造函数接受多种不同文件格式的图像，包括 BMP、GIF、JPEG、PNG 和 TIFF。 创建对象后，将 <xref:System.Drawing.Bitmap> 该 <xref:System.Drawing.Bitmap> 对象传递给对象的 <xref:System.Drawing.Graphics.DrawImage%2A> 方法 <xref:System.Drawing.Graphics> 。  
  
## <a name="example"></a>示例  
 此示例 <xref:System.Drawing.Bitmap> 从 JPEG 文件创建一个对象，然后将该位图的左上角绘制 (60，10) 。  
  
 下图显示了在指定位置绘制的位图：  
  
 ![显示位于指定位置的图像的屏幕截图。](./media/how-to-draw-an-existing-bitmap-to-the-screen/bitmap-specified-position.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅

- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
- [使用图像、位图、图标和图元文件](working-with-images-bitmaps-icons-and-metafiles.md)
