---
title: 如何：转换图像颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: fb9ec30c06740214b8dc6b65d32eba4e2920c89b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971647"
---
# <a name="how-to-translate-image-colors"></a>如何：转换图像颜色
翻译会将一个值添加到四个颜色组件中的一个或多个。 下表给出了表示翻译的颜色矩阵条目。  
  
|要转换的组件|矩阵条目|  
|--------------------------------|------------------|  
|Red|[4][0]|  
|绿色|[4][1]|  
|蓝色|[4][2]|  
|Alpha|[4][3]|  
  
## <a name="example"></a>示例  
 下面的示例 <xref:System.Drawing.Image> 从文件 ColorBars.bmp 构造对象。 然后，代码将0.75 添加到图像中每个像素的红色部分。 原始图像与变换后的图像一起绘制。  
  
 下图显示左侧的原始图像和右侧已转换的图像：  
  
 ![原始图像和转换图像的屏幕截图。](./media/how-to-translate-image-colors/original-image-translate-colors.png)  
  
 下表列出了红色转换前后四个条形的颜色矢量。 请注意，由于颜色分量的最大值为1，第二行中的红色部分不会更改。  (同样，颜色分量的最小值为0。 )   
  
|原始|已转换|  
|--------------|----------------|  
|黑色 (0，0，0，1) |(0.75, 0, 0, 1)|  
|红色 (1，0，0，1) |(1, 0, 0, 1)|  
|绿色 (0，1，0，1) |(0.75, 1, 0, 1)|  
|Blue (0，0，1，1) |(0.75, 0, 1, 1)|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。 替换 `ColorBars.bmp` 为在系统中有效的图像文件名和路径。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
- [对图像重新着色](recoloring-images.md)
