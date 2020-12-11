---
title: 如何：使用钢笔绘制线条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
ms.openlocfilehash: 263c0fbda377e64753cd2d607f633117b4b44253
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971644"
---
# <a name="how-to-use-a-pen-to-draw-lines"></a>如何：使用钢笔绘制线条
若要绘制线条，需要 <xref:System.Drawing.Graphics> 对象和 <xref:System.Drawing.Pen> 对象。 <xref:System.Drawing.Graphics>对象提供 <xref:System.Drawing.Graphics.DrawLine%2A> 方法，而 <xref:System.Drawing.Pen> 对象存储行的功能，如颜色和宽度。  
  
## <a name="example"></a>示例  
 下面的示例从 (20，10) 到 (300，100) 绘制一条线。 第一条语句使用 <xref:System.Drawing.Pen.%23ctor%2A> 类构造函数创建黑色笔。 传递给构造函数的一个参数 <xref:System.Drawing.Pen.%23ctor%2A> 是 <xref:System.Drawing.Color> 使用方法创建的对象 <xref:System.Drawing.Color.FromArgb%2A> 。 用于创建对象的值 <xref:System.Drawing.Color> （ (255，0，0，0) ）对应于颜色的 alpha、红色、绿色和蓝色成分。 这些值定义不透明的黑色笔。  
  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Pen>
- [使用笔绘制线条和形状](using-a-pen-to-draw-lines-and-shapes.md)
- [GDI+ 中的笔、直线和矩形](pens-lines-and-rectangles-in-gdi.md)
