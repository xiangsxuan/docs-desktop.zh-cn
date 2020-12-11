---
title: 如何：创建缩略图图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: 786a92d99f5e7a0c27f502efa9a5fe617ac4d4d6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970321"
---
# <a name="how-to-create-thumbnail-images"></a>如何：创建缩略图图像
缩略图是图像的小型版本。 可以通过调用对象的方法来创建缩略图 <xref:System.Drawing.Image.GetThumbnailImage%2A> <xref:System.Drawing.Image> 。  
  
## <a name="example"></a>示例  
 下面的示例 <xref:System.Drawing.Image> 从 JPG 文件构造对象。 原始图像的宽度为640像素，高度为479像素。 此代码创建一个宽度为100像素、高度为100像素的缩略图。  
  
 下图显示了缩略图：  
  
 ![显示输出缩略图的屏幕截图。](./media/how-to-create-thumbnail-images/construct-thumbnail-image.png)  
  
> [!NOTE]
> 在此示例中，声明了回调方法，但从未使用过。 这支持所有版本的 GDI +。  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。 若要运行该示例，请执行以下步骤：  
  
1. 创建新的 Windows 窗体应用程序。  
  
2. 将示例代码添加到窗体。  
  
3. 为窗体事件创建处理程序 <xref:System.Windows.Forms.Control.Paint>  
  
4. 在 <xref:System.Windows.Forms.Control.Paint> 处理程序中，调用 `GetThumbnail` 方法并传递 `e` <xref:System.Windows.Forms.PaintEventArgs> 。  
  
5. 查找要建立缩略图的图像文件。  
  
6. 在 `GetThumbnail` 方法中，指定映像的路径和文件名。  
  
7. 按 F5 运行该示例。  
  
     窗体上将显示 100 x 100 缩略图图像。  
  
## <a name="see-also"></a>另请参阅

- [图像、位图和图元文件](images-bitmaps-and-metafiles.md)
- [使用图像、位图、图标和图元文件](working-with-images-bitmaps-icons-and-metafiles.md)
