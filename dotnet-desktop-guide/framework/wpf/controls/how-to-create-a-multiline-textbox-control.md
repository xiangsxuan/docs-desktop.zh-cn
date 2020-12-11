---
title: 如何：创建多行 TextBox 控件
description: 了解如何使用 XAML 定义文本框控件，该控件可扩展以容纳 Windows Presentation Foundation 应用程序中的多个文本行。
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: 5e6c58e8c06ae84ef4b811e1ff07f9dce65e0230
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973973"
---
# <a name="how-to-create-a-multiline-textbox-control"></a>如何：创建多行 TextBox 控件
此示例演示如何使用 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 来定义一个 <xref:System.Windows.Controls.TextBox> 控件，该控件将自动展开以容纳多个文本行。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Controls.TextBox.TextWrapping%2A>如果将属性设置为 "**换** 行"，则在到达控件边缘时，输入的文本会换行到新行 <xref:System.Windows.Controls.TextBox> ， <xref:System.Windows.Controls.TextBox> 如有必要，将自动展开控件以包含新行的空间。  
  
 如果将 <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> 属性设置为 **true** ，则在按下 RETURN 键时将插入一个新行，并在必要时再次自动展开 <xref:System.Windows.Controls.TextBox> 以包含新行的空间。  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A>特性可向添加滚动条 <xref:System.Windows.Controls.TextBox> ，因此，如果的内容 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBox> 超出环绕它的框架或窗口的大小，则可以滚动。  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.TextWrapping>
- [TextBox 概述](textbox-overview.md)
- [RichTextBox 概述](richtextbox-overview.md)
