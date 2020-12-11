---
title: 如何：裁剪和缩放图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
ms.openlocfilehash: 4257431881565f9160f45795111d374cc680dedd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970315"
---
# <a name="how-to-crop-and-scale-images"></a>如何：裁剪和缩放图像
<xref:System.Drawing.Graphics>类提供若干 <xref:System.Drawing.Graphics.DrawImage%2A> 方法，其中一些方法具有可用于裁剪和缩放图像的源和目标矩形参数。  
  
## <a name="example"></a>示例  
 下面的示例 <xref:System.Drawing.Image> 从磁盘文件 Apple.gif 构造对象。 此代码以原始大小绘制整个 apple 图像。 然后，该代码调用 <xref:System.Drawing.Graphics.DrawImage%2A> 对象的方法， <xref:System.Drawing.Graphics> 以便在大于原始 apple 图像的目标矩形中绘制 apple 图像的一部分。  
  
 <xref:System.Drawing.Graphics.DrawImage%2A>方法通过查看由第三个、第四个、第五个和第六个参数指定的源矩形来确定要绘制的 apple 部分。 在这种情况下，apple 将裁剪到宽度的75% 和高度的75%。  
  
 <xref:System.Drawing.Graphics.DrawImage%2A>方法通过查看目标矩形（由第二个参数指定），确定要在何处绘制裁剪后的 apple 以及如何进行裁剪。 在这种情况下，目标矩形的宽度为30%，比原始图像高30%。  
  
 下图显示了原始 apple 和经过缩放的已裁剪 apple。  
  
 ![原始图像和已裁剪的相同图像的屏幕截图。](./media/how-to-crop-and-scale-images/original-image-cropped-image.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。 请确保将替换为 `Apple.gif` 在系统中有效的图像文件名和路径。  
  
## <a name="see-also"></a>另请参阅

- [图像、位图和图元文件](images-bitmaps-and-metafiles.md)
- [使用图像、位图、图标和图元文件](working-with-images-bitmaps-icons-and-metafiles.md)
