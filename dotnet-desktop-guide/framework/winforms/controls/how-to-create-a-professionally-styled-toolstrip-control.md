---
title: 如何：创建采用专业样式的 ToolStrip 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
ms.openlocfilehash: 4e4e899d583eb87b3ced7161f1fd274c0bcc591c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971872"
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a>如何：创建采用专业样式的 ToolStrip 控件
可以通过编写自己的派生自 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 类型的类，赋予应用程序的 <xref:System.Windows.Forms.ToolStrip> 控件一个专业的外观和行为（外观和感受）。  
  
 Visual Studio 中提供了此功能的广泛支持。  
  
 请参阅[演练：创建具有专业样式的 ToolStrip 控件](walkthrough-creating-a-professionally-styled-toolstrip-control.md)。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何使用 <xref:System.Windows.Forms.ToolStrip> 控件创建一个复合控件，该控件模拟 Microsoft® Outlook®提供的 **导航窗格** 。  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [ToolStrip 控件](toolstrip-control-windows-forms.md)
- [如何：向窗体提供标准菜单项](how-to-provide-standard-menu-items-to-a-form.md)
