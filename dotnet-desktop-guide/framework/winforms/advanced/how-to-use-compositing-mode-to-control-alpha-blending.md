---
title: 如何：使用复合模式控制 alpha 值混合处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: 6863e59efa25323f80933bf8ab595316b430ef53
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971638"
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a>如何：使用复合模式控制 alpha 值混合处理
有时可能需要创建具有以下特征的非屏幕位图：  
  
- 颜色的 alpha 值小于255。  
  
- 创建位图时，颜色不会混合在一起。  
  
- 显示已完成的位图后，位图中的颜色与显示设备上的背景色混合了 alpha。  
  
 若要创建此类位图，请构造一个空白 <xref:System.Drawing.Bitmap> 对象，然后根据 <xref:System.Drawing.Graphics> 该位图构造对象。 将对象的合成模式设置 <xref:System.Drawing.Graphics> 为 <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType> 。  
  
## <a name="example"></a>示例  
 下面的示例 <xref:System.Drawing.Graphics> 基于对象创建对象 <xref:System.Drawing.Bitmap> 。 该代码使用 <xref:System.Drawing.Graphics> 对象和两个半透明画笔 (alpha = 160) 在位图上绘制。 此代码使用半透明画笔填充红色椭圆和绿色椭圆。 绿色椭圆与红色椭圆重叠，但绿色不与红色混合，因为对象的合成模式 <xref:System.Drawing.Graphics> 设置为 <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy> 。  
  
 此代码将在屏幕上绘制位图两次：一次在白色背景上，一次在颜色背景上。 位图中属于两个椭圆的像素的 alpha 分量为160，因此椭圆与屏幕上的背景颜色混合。  
  
 下图显示了代码示例的输出。 请注意，椭圆与背景混合在一起，但它们彼此之间并不混合。  
  
 ![显示与背景混合的省略号的关系图，而不是彼此混合的关系图。](./media/how-to-use-compositing-mode-to-control-alpha-blending/ellipses-blended-background.png)  
  
 此代码示例包含以下语句：  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 如果希望省略号与其他椭圆以及背景混合，请将该语句更改为以下内容：  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 下图显示了修改后的代码的输出。  
  
 ![显示混合在一起并带有背景的省略号的关系图。](./media/how-to-use-compositing-mode-to-control-alpha-blending/blend-ellipses-background.png)  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，这是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Color.FromArgb%2A>
- [Alpha 混合线条和填充](alpha-blending-lines-and-fills.md)
