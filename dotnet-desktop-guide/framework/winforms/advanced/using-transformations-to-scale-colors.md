---
title: 使用转换来调整颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
ms.openlocfilehash: 81c0ddf5b937d604559a9eb1a8b598885546c97f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971366"
---
# <a name="using-transformations-to-scale-colors"></a>使用转换来调整颜色
缩放变换将四个颜色分量中的一个或多个乘以一个数字。 下表给出了表示缩放的颜色矩阵条目。  
  
|要缩放的组件|矩阵条目|  
|----------------------------|------------------|  
|Red|[0][0]|  
|绿色|[1][1]|  
|蓝色|[2][2]|  
|Alpha|[3][3]|  
  
## <a name="scaling-one-color"></a>缩放一种颜色  
 下面的示例 <xref:System.Drawing.Image> 从文件 ColorBars2.bmp 构造对象。 然后，代码将图像中每个像素的蓝色分量调整2。 原始图像与变换后的图像一起绘制。  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 下图显示左侧的原始图像和右侧缩放后的图像：  
  
 ![比较原始和缩放颜色的屏幕截图。](./media/using-transformations-to-scale-colors/four-bar-scale-one-color.png)  
  
 下表列出了在蓝色缩放前后的四个栏的颜色矢量。 请注意，第四个颜色栏中的蓝色组件从0.8 到0.6。 这是因为 GDI + 只保留结果的小数部分。 例如， (2) # B2 0.8) = 1.6，而1.6 的小数部分是0.6。 仅保留小数部分可确保结果始终在时间间隔 [0，1] 内。  
  
|原始|适当|  
|--------------|------------|  
|(0.4, 0.4, 0.4, 1)|(0.4, 0.4, 0.8, 1)|  
|(0.4, 0.2, 0.2, 1)|(0.4, 0.2, 0.4, 1)|  
|(0.2, 0.4, 0.2, 1)|(0.2, 0.4, 0.4, 1)|  
|(0.4, 0.4, 0.8, 1)|(0.4, 0.4, 0.6, 1)|  
  
## <a name="scaling-multiple-colors"></a>缩放多个颜色  
 下面的示例 <xref:System.Drawing.Image> 从文件 ColorBars2.bmp 构造对象。 然后，代码会在图像中缩放每个像素的红色、绿色和蓝色分量。 红色分量缩小了25%，绿色分量缩小了35%，蓝色分量缩小了50%。  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 下图显示左侧的原始图像和右侧缩放后的图像：  
  
 ![比较原始和缩放颜色的屏幕截图。](./media/using-transformations-to-scale-colors/four-bar-scale-multiple-colors.png)  
  
 下表列出了红色、绿色和蓝色缩放前后的四个线条的颜色矢量。  
  
|原始|适当|  
|--------------|------------|  
|(0.6, 0.6, 0.6, 1)|(0.45, 0.39, 0.3, 1)|  
|(0, 1, 1, 1)|(0, 0.65, 0.5, 1)|  
|(1, 1, 0, 1)|(0.75, 0.65, 0, 1)|  
|(1, 0, 1, 1)|(0.75, 0, 0.5, 1)|  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
- [对图像重新着色](recoloring-images.md)
