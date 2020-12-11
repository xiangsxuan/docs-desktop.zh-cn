---
title: 如何：向窗体添加 ToolStripContainer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStrip control [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], adding to Windows Forms
ms.assetid: d0f55095-a833-453e-be5a-644906d75d54
ms.openlocfilehash: 3d69bc6ed0cf23da8315ae95565300d151069d51
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970049"
---
# <a name="how-to-add-a-toolstripcontainer-to-a-form"></a>如何：向窗体添加 ToolStripContainer
可以通过编程方式向 Windows 窗体添加 <xref:System.Windows.Forms.ToolStripContainer> 并用控件填充该窗体。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何向 Windows 窗体添加 <xref:System.Windows.Forms.ToolStripContainer> 和 <xref:System.Windows.Forms.ToolStrip>，如何向 <xref:System.Windows.Forms.ToolStrip> 添加项，以及如何向 <xref:System.Windows.Forms.ToolStripContainer> 的 <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> 添加 <xref:System.Windows.Forms.ToolStrip>。  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/cs/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/vb/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此代码示例需要：  
  
- 引用 System.Drawing、System.Text 和 System.Windows.Forms 程序集。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStripContainer>
- [ToolStripContainer 控件](toolstripcontainer-control.md)
- [ToolStrip 控件](toolstrip-control-windows-forms.md)
