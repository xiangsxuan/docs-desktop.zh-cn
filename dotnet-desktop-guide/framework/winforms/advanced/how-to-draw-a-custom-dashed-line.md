---
title: 如何：绘制自定义虚线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
ms.openlocfilehash: d2184a8d7d7f24b8f631818608ab4bcdb89857c7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970310"
---
# <a name="how-to-draw-a-custom-dashed-line"></a>如何：绘制自定义虚线
GDI + 提供了在枚举中列出的若干虚线样式 <xref:System.Drawing.Drawing2D.DashStyle> 。 如果这些标准虚线样式不能满足您的需要，则可以创建自定义破折号模式。  
  
## <a name="example"></a>示例  
 若要绘制自定义虚线，请将短划线和空格的长度置于数组中，并将该数组指定为对象的 <xref:System.Drawing.Pen.DashPattern%2A> 属性的值 <xref:System.Drawing.Pen> 。 下面的示例根据数组绘制自定义虚线 `{5, 2, 15, 4}` 。 如果将数组的元素乘以笔宽度5，则会获得 `{25, 10, 75, 20}` 。 显示的短划线替换长度介于25到75之间，空格备用的长度为10到20。  
  
 下图显示了生成的虚线。 请注意，最后一个短划线的长度必须小于25个单位，以便该行可以 (405，5) 结束。  
  
 ![显示虚线的插图。](./media/how-to-draw-a-custom-dashed-line/dashed-line-illustration.gif "pens6")  
  
 [!code-csharp[System.Drawing.UsingAPen#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>编译代码  
 创建 Windows 窗体并处理窗体的 <xref:System.Windows.Forms.Control.Paint> 事件。 将前面的代码粘贴到 <xref:System.Windows.Forms.Control.Paint> 事件处理程序中。  
  
## <a name="see-also"></a>另请参阅

- [使用笔绘制线条和形状](using-a-pen-to-draw-lines-and-shapes.md)
