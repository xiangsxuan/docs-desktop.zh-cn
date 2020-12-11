---
title: 如何：将光标置于 TextBox 控件中的文本的开头或末尾
description: 了解如何将光标置于 Windows Presentation Foundation TextBox 控件的文本内容的开头或结尾。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- positioning cursor [WPF]
- TextBox control [WPF], positioning cursor
- cursor [WPF], positioning
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
ms.openlocfilehash: 32a738c37bac07e660fe84e3707ba4352594928a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973604"
---
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a>如何：将光标置于 TextBox 控件中的文本的开头或末尾
此示例演示如何将光标置于控件文本内容的开头或结尾 <xref:System.Windows.Controls.TextBox> 。  
  
## <a name="example"></a>示例  
 下面的 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 代码描述 <xref:System.Windows.Controls.TextBox> 控件并为其分配一个名称。  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a>示例  
 若要将光标置于控件内容的开头 <xref:System.Windows.Controls.TextBox> ，请调用 <xref:System.Windows.Controls.TextBox.Select%2A> 方法，并指定选择起始位置0，选择长度为0。  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a>示例  
 若要将光标置于控件内容的末尾 <xref:System.Windows.Controls.TextBox> ，请调用 <xref:System.Windows.Controls.TextBox.Select%2A> 方法并指定选定内容的开始位置，该位置等于文本内容的长度，选择长度为0。  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a>另请参阅

- [TextBox 概述](textbox-overview.md)
- [RichTextBox 概述](richtextbox-overview.md)
