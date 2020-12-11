---
title: 如何：在 StatusStrip 中以交互方式使用 Spring 属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
- status bars [Windows Forms], examples
- Spring property [Windows Forms]
ms.assetid: 18bde842-a93c-48dd-9db3-15738a1775ce
ms.openlocfilehash: 8750c48d08161260a1dba6ab69098980f25a5d55
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971117"
---
# <a name="how-to-use-the-spring-property-interactively-in-a-statusstrip"></a>如何：在 StatusStrip 中以交互方式使用 Spring 属性
可以使用 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 属性来定位 <xref:System.Windows.Forms.StatusStrip> 控件中的 <xref:System.Windows.Forms.ToolStripStatusLabel> 控件。 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 属性确定 <xref:System.Windows.Forms.ToolStripStatusLabel> 控件是否自动填充 <xref:System.Windows.Forms.StatusStrip> 控件中的可用空间。  
  
## <a name="example"></a>示例  
 下面的代码示例演示了如何使用 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 属性定位 <xref:System.Windows.Forms.StatusStrip> 控件中的 <xref:System.Windows.Forms.ToolStripStatusLabel> 控件。 <xref:System.Windows.Forms.ToolStripItem.Click> 事件处理程序执行异或 (XOR) 运算，以便切换 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 属性的值。  
  
 若要使用此代码示例，请编译并运行应用程序，然后单击控件上的 " **中间 (弹簧)** <xref:System.Windows.Forms.StatusStrip> 以切换属性的值 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 。  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#50)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#50)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System.Design、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [ToolStrip 控件](toolstrip-control-windows-forms.md)
