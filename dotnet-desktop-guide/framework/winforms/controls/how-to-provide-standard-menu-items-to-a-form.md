---
title: 如何：向窗体提供标准菜单项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- menu items [Windows Forms], standard
- ToolStrip control [Windows Forms]
ms.assetid: 75db9126-e70c-4e81-921d-b83c0a4a9f50
ms.openlocfilehash: a95476ff3d182bf2a56e6527c9ee83c8c56af246
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971144"
---
# <a name="how-to-provide-standard-menu-items-to-a-form"></a>如何：向窗体提供标准菜单项
可使用 <xref:System.Windows.Forms.MenuStrip> 控件向窗体提供标准菜单。  
  
 Visual Studio 中提供了此功能的广泛支持。  
  
 另请参阅[演练：向窗体提供标准菜单项](walkthrough-providing-standard-menu-items-to-a-form.md)。  
  
## <a name="example"></a>示例  
 下面的代码示例演示了如何使用 <xref:System.Windows.Forms.MenuStrip> 控件创建带有标准菜单的窗体。 <xref:System.Windows.Forms.StatusStrip> 控件中将显示菜单项选择。  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [MenuStrip 控件](menustrip-control-windows-forms.md)
