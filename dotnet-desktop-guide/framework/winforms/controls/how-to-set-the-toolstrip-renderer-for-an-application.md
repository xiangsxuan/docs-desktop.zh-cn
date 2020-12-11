---
title: 如何：设置应用程序的 ToolStrip 呈现器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Renderer property [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], customizing
ms.assetid: 46acef3e-9844-4ae8-9a2e-3006fe99cadf
ms.openlocfilehash: c9250b723e68ac97d1486a896392bf64c66cdfbc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972662"
---
# <a name="how-to-set-the-toolstrip-renderer-for-an-application"></a>如何：设置应用程序的 ToolStrip 呈现器
可以单独自定义 <xref:System.Windows.Forms.ToolStrip> 控件的外观，或应用程序中所有 <xref:System.Windows.Forms.ToolStrip> 控件的外观。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何有选择地应用自定义呈现器到 <xref:System.Windows.Forms.ToolStrip> 控件和 <xref:System.Windows.Forms.MenuStrip> 控件。  
  
 若要使用此代码示例，请编译并运行该应用程序，然后从 <xref:System.Windows.Forms.ComboBox> 控件中选择自定义呈现的作用域。 单击“应用”设置呈现器。  
  
 若要查看自定义菜单项呈现，请从控件中选择该 <xref:System.Windows.Forms.MenuStrip> 选项 <xref:System.Windows.Forms.ComboBox> ，单击 " **应用**"，然后打开 " **文件** " 菜单项。  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#70)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#70)]  
  
 设置 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 属性，将自定义呈现器应用到你的应用程序中所有的 <xref:System.Windows.Forms.ToolStrip> 控件。  
  
 设置 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 属性，将自定义呈现器应用到单个 <xref:System.Windows.Forms.ToolStrip> 控件。  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System.Design、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- [ToolStrip 控件](toolstrip-control-windows-forms.md)
