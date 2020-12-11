---
title: 如何：切变颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: 825e5a90ebb0d9df3b894ce7bd353e917b676939
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971412"
---
# <a name="how-to-shear-colors"></a>如何：切变颜色
切变按与其他颜色组件成比例的比例增加或减少颜色成分。 例如，请考虑一个转换，其中红色组件会增加蓝色分量值的一半。 在这种转换下，0.2、0.5、1) 的颜色 ( (0.7，0.5，1) 。 新的红色分量为 0.2 + (1/2) # B2 1) = 0.7。  
  
## <a name="example"></a>示例  
 下面的示例 <xref:System.Drawing.Image> 从文件 ColorBars4.bmp 构造对象。 然后，该代码将上一段中所述的切变转换应用于图像中的每个像素。  
  
 下图显示左侧的原始图像和右侧剪切的图像：
  
 ![具有彩色条带线的两个正方形，用于说明原始图像和剪切图像。](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 下表列出了切变转换前后四个条形的颜色矢量。  
  
|原始|剪切|  
|--------------|-------------|  
|(0, 0, 1, 1)|(0.5, 0, 1, 1)|  
|(0.5, 1, 0.5, 1)|(0.75, 1, 0.5, 1)|  
|(1, 1, 0, 1)|(1, 1, 0, 1)|  
|(0.4, 0.4, 0.4, 1)|(0.6, 0.4, 0.4, 1)|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。 替换 `ColorBars.bmp` 为在系统中有效的图像名称和路径。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
- [对图像重新着色](recoloring-images.md)
