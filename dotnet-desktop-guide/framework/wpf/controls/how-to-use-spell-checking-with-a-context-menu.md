---
title: 如何：使用上下文菜单中的拼写检查功能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
ms.openlocfilehash: 0c2ceb3e4091ee1d98bd0c786f51b3596cdedd08
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970489"
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a>如何：使用上下文菜单中的拼写检查功能
默认情况下，当您在编辑控件（如或）中启用拼写检查时， <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox> 您将获得上下文菜单中的拼写检查选项。 例如，当用户右键单击拼写错误的单词时，它们会获得一组拼写建议或 **忽略所有** 的选项。 但是，当您用您自己的自定义上下文菜单替代默认上下文菜单时，此功能将丢失，您需要编写代码来重新启用上下文菜单中的拼写检查功能。 下面的示例演示如何在上启用此 <xref:System.Windows.Controls.TextBox> 。  
  
## <a name="example"></a>示例  
 下面的示例演示了使用 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] <xref:System.Windows.Controls.TextBox> 一些用于实现上下文菜单的事件创建的。  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a>示例  
 下面的示例演示实现上下文菜单的代码。  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 用于执行此操作的代码 <xref:System.Windows.Controls.RichTextBox> 类似于。 主要区别在于传递给方法的参数 `GetSpellingError` 。 对于 <xref:System.Windows.Controls.TextBox> ，传递插入符号位置的整数索引：  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 对于 <xref:System.Windows.Controls.RichTextBox> ，传递 <xref:System.Windows.Documents.TextPointer> 指定插入符号位置的：  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a>另请参阅

- [TextBox 概述](textbox-overview.md)
- [RichTextBox 概述](richtextbox-overview.md)
- [在文本编辑控件中启用拼写检查](how-to-enable-spell-checking-in-a-text-editing-control.md)
- [将自定义上下文菜单与 TextBox 结合使用](how-to-use-a-custom-context-menu-with-a-textbox.md)
