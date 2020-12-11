---
title: 如何：对渐变应用 gamma 矫正
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: e812e441233c1d29a67dac639048e20a659549f0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970907"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a>如何：对渐变应用 gamma 矫正
可以通过将画笔的属性设置为，为线性渐变画笔启用伽玛更正 <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> `true` 。 您可以通过将属性设置为来禁用伽玛更正 <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> `false` 。 默认情况下禁用伽玛更正。  
  
## <a name="example"></a>示例  

下面的示例是从控件的事件处理程序调用的方法 <xref:System.Windows.Forms.Control.Paint> 。 该示例创建一个线性渐变画笔，并使用该画笔来填充两个矩形。 填充第一个矩形时没有伽玛矫正，第二个矩形用伽玛更正填充。  
  
 下图显示了两个填充的矩形。 没有伽玛矫正的顶部矩形在中间显示为暗。 具有伽玛矫正的底部矩形似乎具有更一致的强度。  
  
 ![两个渐变填充矩形，具有和不带伽玛更正。](./media/how-to-apply-gamma-correction-to-a-gradient/two-rectangles-gamma-gradient.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [使用渐变画笔填充形状](using-a-gradient-brush-to-fill-shapes.md)
