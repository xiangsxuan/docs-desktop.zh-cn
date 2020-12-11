---
title: 如何：对文本使用抗锯齿效果
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
ms.openlocfilehash: 632ed329173d134495a424b34ca7c71e402607bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971641"
---
# <a name="how-to-use-antialiasing-with-text"></a>如何：对文本使用抗锯齿效果
*消除锯齿* 指的是对绘制的图形和文本的锯齿边缘进行平滑处理，以改善其外观或可读性。 利用托管 GDI + 类，可以呈现高质量的抗锯齿文本，以及较低质量的文本。 通常，高质量渲染比较低质量渲染所用的处理时间更长。 若要设置文本质量级别，请将 <xref:System.Drawing.Graphics.TextRenderingHint%2A> 的属性设置 <xref:System.Drawing.Graphics> 为枚举的元素之一 <xref:System.Drawing.Text.TextRenderingHint>  
  
## <a name="example"></a>示例  
 下面的代码示例用两个不同的质量设置来绘制文本。  
  
 [!code-csharp[System.Drawing.FontsAndText#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  

 下图显示了该示例代码的输出：  
  
 ![显示具有两种不同质量设置的文本的屏幕截图。](./media/how-to-use-antialiasing-with-text/antialiasing-text-quality-settings.png)  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的代码示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，这是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>另请参阅

- [使用字体和文本](using-fonts-and-text.md)
