---
title: ContextMenu 概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ContextMenu
- ContextMenu controls [WPF], about ContextMenu controls
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
ms.openlocfilehash: c9e63efb37c8847f27ca4b3616f6f1b5323ac3e5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973245"
---
# <a name="contextmenu-overview"></a>ContextMenu 概述
<xref:System.Windows.Controls.ContextMenu>类表示使用特定于上下文的功能公开功能的元素 <xref:System.Windows.Controls.Menu> 。 通常，用户 <xref:System.Windows.Controls.ContextMenu> [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 通过右键单击鼠标按钮公开中的。 本主题介绍 <xref:System.Windows.Controls.ContextMenu> 元素，并提供有关如何在和代码中使用它的示例 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。  

<a name="contextmenu_control"></a>
## <a name="contextmenu-control"></a>ContextMenu 控件  
 <xref:System.Windows.Controls.ContextMenu>附加到特定控件。 <xref:System.Windows.Controls.ContextMenu>元素使用户能够向用户显示一个项列表，这些项指定与特定控件关联的命令或选项，例如 <xref:System.Windows.Controls.Button> 。 用户通过右键单击控件来显示菜单。 通常，单击 <xref:System.Windows.Controls.MenuItem> 打开子菜单或使应用程序执行命令。  
  
<a name="creating_contextmenus"></a>
## <a name="creating-contextmenus"></a>创建 ContextMenus  
 下面的示例演示如何 <xref:System.Windows.Controls.ContextMenu> 使用子菜单创建。 <xref:System.Windows.Controls.ContextMenu>控件附加到按钮控件。  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>
## <a name="applying-styles-to-a-contextmenu"></a>将样式应用于 ContextMenu  
 通过使用控件 <xref:System.Windows.Style> ，可以在 <xref:System.Windows.Controls.ContextMenu> 不编写自定义控件的情况下，显著更改的外观和行为。 除了设置可视化属性以外，还可以将样式应用于控件的各个部分。 例如，你可以通过使用属性来更改控件部件的行为，也可以向添加部分或更改的布局 <xref:System.Windows.Controls.ContextMenu> 。 下面的示例演示了将样式添加到控件的几种方法 <xref:System.Windows.Controls.ContextMenu> 。  
  
 第一个示例定义一个名为 `SimpleSysResources` 的样式，它演示如何在样式中使用当前的系统设置。 该示例将指定 <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> 为 <xref:System.Windows.Controls.Control.Background%2A> 颜色，并将指定为的 <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> <xref:System.Windows.Controls.Control.Foreground%2A> 颜色 <xref:System.Windows.Controls.ContextMenu> 。  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 下面的示例使用 <xref:System.Windows.Trigger> 元素更改的外观，以 <xref:System.Windows.Controls.Menu> 响应中引发的事件 <xref:System.Windows.Controls.ContextMenu> 。 当用户将鼠标移动到菜单上时，项的外观会 <xref:System.Windows.Controls.ContextMenu> 更改。  
  
```xaml  
<Style x:Key="Triggers" TargetType="{x:Type MenuItem}">  
  <Style.Triggers>  
    <Trigger Property="MenuItem.IsMouseOver" Value="true">  
      <Setter Property = "FontSize" Value="16"/>  
      <Setter Property = "FontStyle" Value="Italic"/>  
      <Setter Property = "Foreground" Value="Red"/>  
    </Trigger>  
  </Style.Triggers>  
</Style>  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [ContextMenu](contextmenu.md)
- [ContextMenu 样式和模板](contextmenu-styles-and-templates.md)
- [WPF 控件库示例](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
