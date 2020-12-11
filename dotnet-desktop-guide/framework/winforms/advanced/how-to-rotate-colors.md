---
title: 如何：旋转颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 8d2717dd7b819e963126072279b361fda02188bc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971673"
---
# <a name="how-to-rotate-colors"></a>如何：旋转颜色
在四维颜色空间中，旋转难于可视化。 通过同意使其中一个颜色组件保持固定，我们可以更轻松地可视化旋转。 假设我们同意在 1 (完全不透明的) 保持 alpha 分量固定。 然后，可以使用红色、绿色和蓝色轴直观显示三维颜色空间，如下图所示。  
  
 ![显示用红色、绿色和蓝色轴旋转的插图。](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 颜色可被视为3D 空间中的点。 例如，点 (1，0，0，0) 空间表示红色， (0，1，0) 空间中的点表示绿色。  
  
 下图显示了在 Red-Green 平面中，如何将颜色 (1，0，0) 旋转到60度。 可以将平面中平行于 Red-Green 平面的旋转视为围绕蓝色轴旋转。  
  
 ![显示有关蓝色轴旋转的插图。](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 下图显示了如何初始化颜色矩阵，以便对三个坐标轴 (红、绿、蓝) 的每个轴进行旋转：  
  
 ![初始化颜色矩阵以执行关于三个轴的旋转。](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a>示例  
 下面的示例使用一个图像，该图像是 (1，0，0.6) 的所有颜色，并对蓝色轴应用60度旋转。 旋转角度在平行于 red 绿色平面的平面中进行扫描。  
  
 下图显示左侧的原始图像和右侧的彩色旋转图像：  
  
 ![显示原始图像和彩色旋转图像的插图。](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 下图显示了在以下代码中执行的颜色旋转的可视化效果：
  
 ![显示颜色旋转的可视化效果的图例。](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。 替换 `RotationInput.bmp` 为在系统中有效的图像文件名和路径。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
- [对图像重新着色](recoloring-images.md)
