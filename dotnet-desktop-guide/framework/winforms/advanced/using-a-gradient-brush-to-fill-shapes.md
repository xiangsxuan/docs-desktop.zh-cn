---
title: 使用渐变画笔填充形状
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 7ff555ba4fd81e9123e5f9e9feed38a0ec9d0a08
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971580"
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a>使用渐变画笔填充形状
您可以使用渐变画笔来填充渐变颜色的形状。 例如，您可以使用水平渐变填充具有颜色的形状，该颜色在从形状的左边缘向右边缘移动时逐渐变化。 假设有一个矩形，左边缘为黑色 (由红色、绿色和蓝色分量0、0、0) 和右边缘表示， (由255，0，0) 表示。 如果矩形为256像素宽，则给定像素的红色分量将比它左侧像素的红色分量大1。 行中最左边的像素具有颜色分量 (0，0，0) ，第二个像素 (1，0，0) ，第三个像素具有 (2，0，0) ，依此类推，直到到达最右边的像素，其中颜色分量 (255，0，0) 。 这些插值颜色值构成了颜色渐变。  
  
 当水平、垂直或平行于指定的斜线时，线性渐变会改变颜色。 移动路径的内部和边界时，路径渐变会改变颜色。 您可以自定义路径渐变以实现各种效果。  
  
 下图显示了使用线性渐变画笔填充的矩形，并使用路径渐变画笔填充了椭圆：  
  
 ![使用带有椭圆的渐变画笔填充的矩形。](./media/using-a-gradient-brush-to-fill-shapes/rectangle-ellipse-gradient-brush.png)  
  
## <a name="in-this-section"></a>本节内容  
 [如何：创建线性渐变](how-to-create-a-linear-gradient.md)  
 演示如何使用类创建线性渐变 <xref:System.Drawing.Drawing2D.LinearGradientBrush> 。  
  
 [如何：创建路径渐变](how-to-create-a-path-gradient.md)  
 描述如何使用类创建路径渐变 <xref:System.Drawing.Drawing2D.PathGradientBrush> 。  
  
 [如何：对渐变应用 gamma 矫正](how-to-apply-gamma-correction-to-a-gradient.md)  
 说明如何对渐变画笔使用伽玛更正。  
  
## <a name="reference"></a>参考  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 包含此类的说明，并提供指向其所有成员的链接。  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 包含此类的说明，并提供指向其所有成员的链接。
