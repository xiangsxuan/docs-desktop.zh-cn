---
title: 如何：加载和显示图元文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 6c17e0b2d023ccf80b0d32301b7ee6765edcae9f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971438"
---
# <a name="how-to-load-and-display-metafiles"></a>如何：加载和显示图元文件
<xref:System.Drawing.Imaging.Metafile>类继承自 <xref:System.Drawing.Image> 类，提供用于记录、显示和检查矢量图像的方法。  
  
## <a name="example"></a>示例  
 若要在屏幕上显示矢量图像 (图元文件) ，需要 <xref:System.Drawing.Imaging.Metafile> 对象和 <xref:System.Drawing.Graphics> 对象。 将 (或) 流的文件名称传递到 <xref:System.Drawing.Imaging.Metafile> 构造函数。 创建 <xref:System.Drawing.Imaging.Metafile> 对象后， <xref:System.Drawing.Imaging.Metafile> 将该对象传递给对象的 <xref:System.Drawing.Graphics.DrawImage%2A> 方法 <xref:System.Drawing.Graphics> 。  
  
 该示例 <xref:System.Drawing.Imaging.Metafile> 从 EMF (增强型图元文件) 文件创建一个对象，然后在 (60，10) 的左上角绘制图像。  
  
 下图显示了在指定位置绘制的图元文件。  
  
 ![显示图像位置的屏幕截图。](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅

- [使用图像、位图、图标和图元文件](working-with-images-bitmaps-icons-and-metafiles.md)
