---
title: 如何：填充开放图形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: 6ecea7d3edb0c3e25fb4e69ff12b88019e530021
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971446"
---
# <a name="how-to-fill-open-figures"></a>如何：填充开放图形
可以通过将对象传递给方法来填充路径 <xref:System.Drawing.Drawing2D.GraphicsPath> <xref:System.Drawing.Graphics.FillPath%2A> 。 <xref:System.Drawing.Graphics.FillPath%2A>方法根据当前为路径设置 (替换或缠绕) 填充模式来填充路径。 如果路径有任何打开的图形，则会像关闭这些图形一样填充路径。 GDI + 通过绘制从其结束点到起始点的直线来关闭一个图形。  
  
## <a name="example"></a>示例  
 下面的示例创建一个路径，该路径具有一个 (弧线) 的闭合图形，另一个闭合图形 (一个椭圆) 。 <xref:System.Drawing.Graphics.FillPath%2A>方法根据默认填充模式填充路径，即 <xref:System.Drawing.Drawing2D.FillMode.Alternate> 。  
  
 下图显示了该示例代码的输出。 请注意，根据) ，路径是根据 <xref:System.Drawing.Drawing2D.FillMode.Alternate> 从其结束点到起始点的直线闭合的闭合图形 (填充的。  
  
 ![显示 FillPath 方法输出的关系图](./media/how-to-fill-open-figures/fill-path-alternate-mode.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [GDI+ 中的图形路径](graphics-paths-in-gdi.md)
