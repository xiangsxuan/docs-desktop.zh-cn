---
title: 如何：使用颜色矩阵对单色进行转换
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image colors [Windows Forms], transforming
- color matrices [Windows Forms], using
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
ms.openlocfilehash: 2df74e022b842f7e5c9ff80f6aeddfce51af5eab
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971652"
---
# <a name="how-to-use-a-color-matrix-to-transform-a-single-color"></a>如何：使用颜色矩阵对单色进行转换
GDI + 提供 <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> 用于存储和操作图像的和类。 <xref:System.Drawing.Image> 和 <xref:System.Drawing.Bitmap> 对象将每个像素的颜色存储为32位数字：对于红色、绿色、蓝色和 alpha 分别使用8位。 这四个组件都是0到255之间的一个数字，0表示没有强度，255表示完全强度。 Alpha 分量指定颜色的透明度：0表示完全透明，255表示完全不透明。  
  
 颜色矢量是 (红、绿、蓝、alpha) 形式的4元组。 例如，颜色向量 (0，255，0，255) 表示不透明的颜色，该颜色没有红色或蓝色，但以完全强度显示绿色。  
  
 表示颜色的另一种约定使用数字1来表示完全强度。 使用该约定，上一段中所述的颜色将由向量 (0，1，0，1) 表示。 GDI + 执行颜色转换时，使用1作为完整强度的约定。  
  
 您可以通过将颜色向量与4×4矩阵相乘，将线性转换 (旋转、缩放和 like) 应用于颜色矢量。 但是，不能使用4×4矩阵 (非线性) 执行转换。 如果添加了一个虚拟的第五个坐标 (例如，数字 1) 每个颜色向量，则可以使用5×5矩阵应用线性转换和转换的任意组合。 由线性转换后跟平移的转换称为仿射转换。  
  
 例如，假设你想要从 (0.2、0.0、0.4、1.0) 的颜色开始，并应用以下转换：  
  
1. 双红色分量  
  
2. 向红色、绿色和蓝色分量添加0。2  
  
 下面的矩阵乘法将按列出的顺序执行转换对。  
  
 ![转换乘法矩阵的屏幕截图。](./media/how-to-use-a-color-matrix-to-transform-a-single-color/multiplication-color-matrix.gif)
  
 颜色矩阵的元素按行和 then 列索引 (从零开始) 。 例如，matrix M 的第五行和第三列中的条目由 M [4] [2] 表示。  
  
 下) 图中显示的5×5恒等矩阵 (，其中每个对角线都为1，而其他位置为0。 如果用恒等矩阵乘以颜色向量，则颜色矢量不会改变。 形成颜色转换的矩阵的一种简便方法是从标识矩阵开始，并进行少量的更改，以生成所需的转换。  
  
 ![颜色转换的5x5 标识矩阵的屏幕截图。](./media/how-to-use-a-color-matrix-to-transform-a-single-color/5x5-identity-matrix-color-transformation.gif)  
  
 有关矩阵和转换的更多详细讨论，请参阅 [坐标系统和转换](coordinate-systems-and-transformations.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用一个图像，该图像的颜色为0.2、0.0、0.4、1.0)  (，并应用上述段落中描述的转换。  
  
 下图显示左侧的原始图像和右侧的变换后的图像。  
  
 ![左侧的紫色方块和右侧的 fuchsia 方块。](./media/how-to-use-a-color-matrix-to-transform-a-single-color/color-transformation.png)  
  
 以下示例中的代码使用以下步骤来执行重新着色：  
  
1. 初始化 <xref:System.Drawing.Imaging.ColorMatrix> 对象。  
  
2. 创建一个 <xref:System.Drawing.Imaging.ImageAttributes> 对象，并将该 <xref:System.Drawing.Imaging.ColorMatrix> 对象传递给 <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> 对象的方法 <xref:System.Drawing.Imaging.ImageAttributes> 。  
  
3. 将 <xref:System.Drawing.Imaging.ImageAttributes> 对象传递给 <xref:System.Drawing.Graphics.DrawImage%2A> 对象的方法 <xref:System.Drawing.Graphics> 。  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅

- [对图像重新着色](recoloring-images.md)
- [坐标系和坐标转换](coordinate-systems-and-transformations.md)
