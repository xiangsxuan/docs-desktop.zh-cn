---
title: 如何：绘制不透明和半透明的线条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- transparency [Windows Forms], lines
- lines [Windows Forms], drawing alpha blended
- alpha blending [Windows Forms], drawing lines
ms.assetid: 8f2508af-f495-4223-b5cc-646cbbb520eb
ms.openlocfilehash: 547c748451e9f7f91dcbe7595d4418835bac9f67
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971466"
---
# <a name="how-to-draw-opaque-and-semitransparent-lines"></a>如何：绘制不透明和半透明的线条
绘制线条时，必须将 <xref:System.Drawing.Pen> 对象传递给 <xref:System.Drawing.Graphics> 类的 <xref:System.Drawing.Graphics.DrawLine%2A> 方法。 <xref:System.Drawing.Pen.%23ctor%2A> 构造函数的参数之一是 <xref:System.Drawing.Color> 对象。 若要绘制不透明的线条，请将颜色的 alpha 分量设置为 255。 若要绘制半透明的线条，请将 alpha 分量设置为从 1 到 254 的任何值。  
  
 在背景上绘制半透明的线条时，线条的颜色与背景的颜色混合。 alpha 分量指定线条和背景色混合的方式；alpha 值越接近 0，背景颜色的权重越大，alpha 值越接近 255，线条颜色的权重越大。  
  
## <a name="example"></a>示例  
 下面的示例绘制一个位图，然后制使用该位图作为背景绘三条线。 第一条线使用值为 255 的 alpha 分量，因此它是不透明的。 第二条和第三条线使用值为 128 的 alpha 分量，因此它们是半透明的；你可透过线条看到背景图像。 设置 <xref:System.Drawing.Graphics.CompositingQuality%2A> 属性的语句会导致第三条线的混合与 gamma 矫正一起完成。  
  
 [!code-csharp[System.Drawing.AlphaBlending#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.AlphaBlending#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#11)]  
  
 下图显示了以下代码的输出：  
  
 ![显示不透明和半透明输出的插图](./media/how-to-draw-opaque-and-semitransparent-lines/opaque-semitransparent-lines.png)  

## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅

- [Alpha 混合线条和填充](alpha-blending-lines-and-fills.md)
- [如何：使控件拥有透明背景](../controls/how-to-give-your-control-a-transparent-background.md)
- [如何：用不透明和半透明的画笔绘制](how-to-draw-with-opaque-and-semitransparent-brushes.md)
