---
title: 如何：在 ToolStrip 应用程序中自定义颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], customizing colors
- colors [Windows Forms], customizing in ToolStrip controls [Windows Forms]
- ToolStrip control [Windows Forms], custom colors
ms.assetid: e2752fe2-1afb-489e-ab96-b7805acd96bc
ms.openlocfilehash: 6719156d0ab6d1e53cd0bd8f16f306577589fb40
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971217"
---
# <a name="how-to-customize-colors-in-toolstrip-applications"></a>如何：在 ToolStrip 应用程序中自定义颜色
可借助 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 类使用自定义颜色来自定义 <xref:System.Windows.Forms.ToolStrip> 的外观。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何使用 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 在运行时定义自定义颜色。  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System.Design、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.ProfessionalColorTable>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
