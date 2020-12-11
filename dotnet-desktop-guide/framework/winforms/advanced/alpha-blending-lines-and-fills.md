---
title: Alpha 混合线条和填充
ms.date: 03/30/2017
helpviewer_keywords:
- lines [Windows Forms], adding transparency
- examples [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with lines
- alpha blending
- lines [Windows Forms], alpha blending
- fills [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with fills
- shapes [Windows Forms], adding transparency
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
ms.openlocfilehash: 66061341ee6539e2172c537a0b2a6ec9ff87565c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970614"
---
# <a name="alpha-blending-lines-and-fills"></a>Alpha 混合线条和填充
在 GDI + 中，颜色是一个32位值，其中每个字母分别为 alpha、红色、绿色和蓝色。 Alpha 值指示颜色的透明度—颜色与背景色混合的程度。 Alpha 值的范围为0到255，其中0表示完全透明的颜色，255表示完全不透明的颜色。  
  
 Alpha 混合是源和背景色数据的逐像素混合。 对于给定的源颜色，三个组件中的每个 (红、绿、蓝) 根据以下公式与背景色的相应组件混合：  
  
 displayColor = sourceColor × alpha/255 + backgroundColor x (255 – alpha) /255  
  
 例如，假设源颜色的红色分量为150，背景色的红色分量为100。 如果 alpha 值为200，则生成的颜色的红色分量按如下方式计算：  
  
 150 × 200 / 255 + 100 × (255 – 200) / 255 = 139  
  
## <a name="in-this-section"></a>本节内容  
 [如何：绘制不透明和半透明的线条](how-to-draw-opaque-and-semitransparent-lines.md)  
 演示如何绘制 alpha 混合线条。  
  
 [如何：用不透明和半透明的画笔绘制](how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 说明如何与画笔混合。  
  
 [如何：使用复合模式控制 alpha 值混合处理](how-to-use-compositing-mode-to-control-alpha-blending.md)  
 描述如何使用控制 alpha 混合 <xref:System.Drawing.Drawing2D.CompositingMode> 。  
  
 [如何：使用颜色矩阵设置图像中的 Alpha 值](how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 说明如何使用 <xref:System.Drawing.Imaging.ColorMatrix> 对象控制 alpha 混合。
