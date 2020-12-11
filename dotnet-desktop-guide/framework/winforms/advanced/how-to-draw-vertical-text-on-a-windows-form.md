---
title: 如何：在 Windows 窗体上绘制垂直文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- StringFormat.FormatFlags
- Graphics.DrawString
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- strings [Windows Forms], drawing vertical
- text [Windows Forms], drawing
- text [Windows Forms], vertical text
ms.assetid: 717a6131-00f6-4373-b574-9894e8317799
ms.openlocfilehash: 660d7abae5463c976e60b7d9caeae8a798d122ca
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971454"
---
# <a name="how-to-draw-vertical-text-on-a-windows-form"></a>如何：在 Windows 窗体上绘制垂直文本
下面的代码示例演示如何使用的方法在窗体上绘制垂直文本 <xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Drawing.Graphics> 。  
  
## <a name="example"></a>示例  
 [!code-cpp[System.Drawing.ConceptualHowTos#8](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#8)]
 [!code-csharp[System.Drawing.ConceptualHowTos#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#8)]
 [!code-vb[System.Drawing.ConceptualHowTos#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#8)]  
  
## <a name="compiling-the-code"></a>编译代码  
 不能在事件处理程序中调用此方法 <xref:System.Windows.Forms.Form.Load> 。 如果窗体调整或被其他窗体遮住，则不会重新绘制所绘制的内容。 若要自动重绘内容，应重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法。  
  
## <a name="robust-programming"></a>可靠编程  
 以下情况可能会导致异常：  
  
- 未安装 Arial 字体。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [图形编程入门](getting-started-with-graphics-programming.md)
- [使用字体和文本](using-fonts-and-text.md)
