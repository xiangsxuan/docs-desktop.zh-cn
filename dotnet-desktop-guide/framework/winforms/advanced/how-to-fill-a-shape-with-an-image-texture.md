---
title: 如何：用图像纹理填充形状
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: 42c456137f84c6fa657ba5a09727eae052a45376
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971702"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a>如何：用图像纹理填充形状
通过使用 <xref:System.Drawing.Image> 类和类，您可以使用纹理填充闭合形状 <xref:System.Drawing.TextureBrush> 。  
  
## <a name="example"></a>示例  
 下面的示例使用图像填充椭圆。 代码构造 <xref:System.Drawing.Image> 对象，然后将该对象的地址 <xref:System.Drawing.Image> 作为参数传递给 <xref:System.Drawing.TextureBrush.%23ctor%2A> 构造函数。 第三个语句缩放图像，第四条语句用缩放图像的重复副本填充椭圆。  
  
 在下面的代码中， <xref:System.Drawing.TextureBrush.Transform%2A> 属性包含在绘制图像之前应用于该图像的转换。 假设原始图像的宽度为640像素，高度为480像素。 该转换通过设置水平和垂直缩放值将图像收缩为75×75。  
  
> [!NOTE]
> 在下面的示例中，图像大小为75×75，椭圆大小为150×250。 由于图像小于它所填充的椭圆，因此椭圆与图像平铺。 平铺意味着在达到形状边界之前，图像将水平和垂直地重复。 有关平铺的详细信息，请参阅 [如何：使用图像平铺形状](how-to-tile-a-shape-with-an-image.md)。  
  
 [!code-csharp[System.Drawing.UsingABrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅

- [使用画笔填充形状](using-a-brush-to-fill-shapes.md)
