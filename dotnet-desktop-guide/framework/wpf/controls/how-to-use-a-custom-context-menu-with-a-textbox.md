---
title: 如何：通过 TextBox 使用自定义上下文菜单
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [WPF], custom
- menus [WPF], custom
- custom context menus [WPF]
- TextBox control [WPF], custom content menus
ms.assetid: 842d3cd5-6fa0-4be4-8d90-6c7466213b1c
ms.openlocfilehash: 93ee6d44e9e5703d70d0583b759330a9e52f60b9
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972529"
---
# <a name="how-to-use-a-custom-context-menu-with-a-textbox"></a>如何：通过 TextBox 使用自定义上下文菜单
此示例演示如何定义和实现的简单自定义上下文菜单 <xref:System.Windows.Controls.TextBox> 。  
  
## <a name="example"></a>示例  
 下面的 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 示例定义了一个 <xref:System.Windows.Controls.TextBox> 包含自定义上下文菜单的控件。  
  
 使用元素定义上下文菜单 <xref:System.Windows.Controls.ContextMenu> 。  上下文菜单本身由一系列 <xref:System.Windows.Controls.MenuItem> 元素和 <xref:System.Windows.Controls.Separator> 元素组成。  每个 <xref:System.Windows.Controls.MenuItem> 元素定义上下文菜单中的一个命令; <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 属性定义菜单命令的显示文本，而 <xref:System.Windows.Controls.MenuItem.Click> 属性指定每个菜单项的处理程序方法。  <xref:System.Windows.Controls.Separator>元素只是导致在之前和之后的菜单项之间呈现分隔行。  
  
 [!code-xaml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## <a name="example"></a>示例  
 下面的示例演示前面的上下文菜单定义的实现代码，以及启用和禁用上下文菜单的代码。  <xref:System.Windows.Controls.ContextMenu.Opened>事件用于动态启用或禁用某些命令，具体取决于的当前状态 <xref:System.Windows.Controls.TextBox> 。  
  
 若要还原默认上下文菜单，请使用 <xref:System.Windows.DependencyObject.ClearValue%2A> 方法清除属性的值 <xref:System.Windows.FrameworkElement.ContextMenu%2A> 。  若要完全禁用上下文菜单，请 <xref:System.Windows.FrameworkElement.ContextMenu%2A> `Nothing` 在 Visual Basic) 中将属性设置为 null 引用 (。  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## <a name="see-also"></a>另请参阅

- [将拼写检查功能与上下文菜单结合使用](how-to-use-spell-checking-with-a-context-menu.md)
- [TextBox 概述](textbox-overview.md)
- [RichTextBox 概述](richtextbox-overview.md)
