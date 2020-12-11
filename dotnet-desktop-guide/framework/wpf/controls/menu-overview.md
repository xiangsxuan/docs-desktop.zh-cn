---
title: 菜单概述
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: 53bc8f10e61b6e4e9e1f3b9a484340d9e2ec2a85
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974006"
---
# <a name="menu-overview"></a>菜单概述
<xref:System.Windows.Controls.Menu>类使你能够按层次结构的顺序组织与命令和事件处理程序关联的元素。 每个 <xref:System.Windows.Controls.Menu> 元素都包含一个 <xref:System.Windows.Controls.MenuItem> 元素集合。  

<a name="menu_control"></a>
## <a name="menu-control"></a>Menu 控件  
 <xref:System.Windows.Controls.Menu>控件提供了一个项列表，这些项指定了应用程序的命令或选项。 通常，单击 <xref:System.Windows.Controls.MenuItem> 打开子菜单或使应用程序执行命令。  
  
<a name="creating_menus"></a>
## <a name="creating-menus"></a>创建菜单  
 下面的示例创建一个 <xref:System.Windows.Controls.Menu> 来操作中的文本 <xref:System.Windows.Controls.TextBox> 。 <xref:System.Windows.Controls.Menu>包含 <xref:System.Windows.Controls.MenuItem> 使用 <xref:System.Windows.Controls.MenuItem.Command%2A> 、 <xref:System.Windows.Controls.MenuItem.IsCheckable%2A> 和 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 属性以及 <xref:System.Windows.Controls.MenuItem.Checked> 、和 <xref:System.Windows.Controls.MenuItem.Unchecked> <xref:System.Windows.Controls.MenuItem.Click> 事件的对象。  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>
## <a name="menuitems-with-keyboard-shortcuts"></a>使用键盘快捷方式的菜单项  
 键盘快捷方式是可通过键盘输入来调用命令的字符组合 <xref:System.Windows.Controls.Menu> 。 例如，“复制”的快捷方式是 CTRL+C。 有两个用于键盘快捷方式和菜单项（或）的属性 <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> <xref:System.Windows.Controls.MenuItem.Command%2A> 。  
  
<a name="menus_inputgesturetext"></a>
### <a name="inputgesturetext"></a>InputGestureText  
 下面的示例演示如何使用 <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> 属性将键盘快捷方式文本分配给 <xref:System.Windows.Controls.MenuItem> 控件。 这仅将键盘快捷方式放置在菜单项中。  它不会将命令与相关联 <xref:System.Windows.Controls.MenuItem> 。 应用程序必须处理用户的输入才能执行操作。  
  
 [!code-xaml[MenuEvent#6](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>
### <a name="command"></a>命令  
 下面的示例演示如何使用 <xref:System.Windows.Controls.MenuItem.Command%2A> 属性将 " **打开** " 和 " **保存** " 命令与 <xref:System.Windows.Controls.MenuItem> 控件相关联。 命令属性不仅会将命令与关联 <xref:System.Windows.Controls.MenuItem> ，还会提供要用作快捷方式的输入笔势文本。  
  
 [!code-xaml[MenuEvent#8](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 <xref:System.Windows.Controls.MenuItem>类还具有一个 <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> 属性，该属性指定发生命令的元素。 如果 <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> 未设置，则具有键盘焦点的元素将接收命令。 有关命令的详细信息，请参阅[命令概述](../advanced/commanding-overview.md)。  
  
<a name="menu_styling"></a>
## <a name="menu-styling"></a>菜单样式设置  
 使用控件样式，可以显著更改控件的外观和行为， <xref:System.Windows.Controls.Menu> 而无需编写自定义控件。 除了设置视觉对象属性之外，您还可以将应用于 <xref:System.Windows.Style> 控件的各个部分，通过属性更改控件部件的行为，或添加其他部分或更改控件的布局。 下面的示例演示了向控件添加的几种方法 <xref:System.Windows.Style> <xref:System.Windows.Controls.Menu> 。  
  
 第一个代码示例定义一个 <xref:System.Windows.Style> 名为 `Simple` 的，该示例演示如何在样式中使用当前系统设置。 代码将 `MenuHighlightBrush` 的颜色分配为菜单的背景色，将 `MenuTextBrush` 分配为菜单的前景色。 请注意，使用资源键分配画笔。  
  
 [!code-xaml[MenuStylesSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 下面的示例使用 <xref:System.Windows.Trigger> 元素，这些元素使你可以更改的外观，以 <xref:System.Windows.Controls.MenuItem> 响应中发生的事件 <xref:System.Windows.Controls.Menu> 。 将鼠标移到上时 <xref:System.Windows.Controls.Menu> ，菜单项的前景色和字体特征会改变。  
  
 [!code-xaml[MenuStylesSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>另请参阅

- [WPF 控件库示例](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
