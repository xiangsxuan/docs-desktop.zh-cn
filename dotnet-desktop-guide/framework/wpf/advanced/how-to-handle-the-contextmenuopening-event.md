---
title: 如何：处理 ContextMenuOpening 事件
ms.date: 03/30/2017
helpviewer_keywords:
- ContextMenuOpening properties [WPF]
ms.assetid: 789652fb-1951-4217-934a-7843e355adf4
ms.openlocfilehash: b3d0f5c77ebf8527e4854d4edf12d6fa8a4b5f0c
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972585"
---
# <a name="how-to-handle-the-contextmenuopening-event"></a>如何：处理 ContextMenuOpening 事件
<xref:System.Windows.FrameworkElement.ContextMenuOpening>可以在应用程序中处理事件，以在显示之前调整现有上下文菜单，或通过 <xref:System.Windows.RoutedEventArgs.Handled%2A> `true` 在事件数据中将属性设置为来禁止显示菜单。 <xref:System.Windows.RoutedEventArgs.Handled%2A>在事件数据中设置为的典型原因 `true` 是将菜单完全替换为新的 <xref:System.Windows.Controls.ContextMenu> 对象，这有时需要取消操作并启动新的。 如果为事件编写处理程序 <xref:System.Windows.FrameworkElement.ContextMenuOpening> ，则应注意控件和服务之间的计时问题， <xref:System.Windows.Controls.ContextMenu> 这些问题通常负责打开和定位控件的上下文菜单。 本主题演示了用于各种上下文菜单打开方案的一些代码技巧，并阐释了计时问题的播放案例。  
  
 处理事件的方案有多种 <xref:System.Windows.FrameworkElement.ContextMenuOpening> ：  
  
- 在显示之前调整菜单项。  
  
- 在显示前替换整个菜单。  
  
- 完全禁止显示任何现有上下文菜单并不显示上下文菜单。  
  
## <a name="example"></a>示例  
  
## <a name="adjusting-the-menu-items-before-display"></a>在显示之前调整菜单项  
 调整现有菜单项相当简单，可能是最常见的方案。 您可以这样做，以便添加或减去上下文菜单选项，以响应应用程序中的当前状态信息，或者作为在请求上下文菜单的对象上提供的特定状态信息。  
  
 一般方法是获取事件的源，该事件是右键单击的特定控件，并 <xref:System.Windows.FrameworkElement.ContextMenu%2A> 从中获取属性。 您通常需要检查 <xref:System.Windows.Controls.ItemsControl.Items%2A> 集合以查看菜单中已经存在的上下文菜单项，然后在集合中添加或移除适当的新 <xref:System.Windows.Controls.MenuItem> 项。  
  
 [!code-csharp[ContextMenuOpeningHandlers#AddItemNoHandle](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#additemnohandle)]  
  
## <a name="replacing-the-entire-menu-before-display"></a>在显示前替换整个菜单  
 另一种情况是，如果要替换整个上下文菜单。 当然，您还可以使用上述代码的变体来删除现有上下文菜单的每个项，并添加从项零开始的新项。 但替换上下文菜单中的所有项的更直观方法是创建一个新的 <xref:System.Windows.Controls.ContextMenu> ，使用项填充该项，然后将 <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> 控件的属性设置为新的 <xref:System.Windows.Controls.ContextMenu> 。  
  
 下面是用于替换的简单处理程序代码 <xref:System.Windows.Controls.ContextMenu> 。 此代码引用自定义 `BuildMenu` 方法，该方法被分隔，因为它由多个示例处理程序调用。  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceNoReopen](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacenoreopen)]  
  
 [!code-csharp[ContextMenuOpeningHandlers#BuildMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#buildmenu)]  
  
 但是，如果你将此样式的处理程序用于 <xref:System.Windows.FrameworkElement.ContextMenuOpening> ，则如果你要设置的对象没有 <xref:System.Windows.Controls.ContextMenu> 预先存在的上下文菜单，则可能会公开计时问题。 当用户右键单击控件时， <xref:System.Windows.FrameworkElement.ContextMenuOpening> 即使现有的为空或为 null，也会引发 <xref:System.Windows.Controls.ContextMenu> 。 但在这种情况下，在源元素上设置的任何新内容都 <xref:System.Windows.Controls.ContextMenu> 无法显示。 此外，如果用户第二次再次右键单击，这一次出现新的情况 <xref:System.Windows.Controls.ContextMenu> ，则值为非 null，处理程序将正确地替换并在处理程序再次运行时显示菜单。 这会建议两个可能的解决方法：  
  
1. 确保 <xref:System.Windows.FrameworkElement.ContextMenuOpening> 处理程序始终针对至少具有占位符的控件运行 <xref:System.Windows.Controls.ContextMenu> ，您打算将其替换为处理程序代码。 在这种情况下，你仍可以使用前面示例中所示的处理程序，但通常需要 <xref:System.Windows.Controls.ContextMenu> 在初始标记中分配一个占位符：  
  
     [!code-xaml[ContextMenuOpeningHandlers#XAMLWithInitCM](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml#xamlwithinitcm)]  
  
2. 根据 <xref:System.Windows.Controls.ContextMenu> 某些初步逻辑，假设初始值可能为 null。 可以检查 <xref:System.Windows.Controls.ContextMenu> 是否存在 null，或在代码中使用标志来检查处理程序是否已至少运行一次。 由于假定将 <xref:System.Windows.Controls.ContextMenu> 显示，因此处理程序将 <xref:System.Windows.RoutedEventArgs.Handled%2A> `true` 在事件数据中将设置为。 <xref:System.Windows.Controls.ContextMenuService>对于负责上下文菜单显示的， `true` <xref:System.Windows.RoutedEventArgs.Handled%2A> 事件数据中的值表示一个为引发事件的上下文菜单/控件组合取消显示的请求。  
  
 现在，你已取消可能可疑的上下文菜单，下一步就是提供一个新的，然后显示它。 设置新的是与上一个处理程序基本相同的操作：生成新的 <xref:System.Windows.Controls.ContextMenu> 并使用它设置控件源的 <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> 属性。 附加步骤是，您现在必须强制显示上下文菜单，因为您已取消第一次尝试。 若要强制显示，请在 <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A?displayProperty=nameWithType> 处理程序中将属性设置为 `true` 。 执行此操作时请小心，因为在处理程序中打开上下文菜单将再次引发该 <xref:System.Windows.FrameworkElement.ContextMenuOpening> 事件。 如果重新输入处理程序，则它将变得无限递归。 这就是您在 `null` 从 <xref:System.Windows.FrameworkElement.ContextMenuOpening> 事件处理程序中打开上下文菜单时始终需要检查或使用标志的原因。  
  
## <a name="suppressing-any-existing-context-menu-and-displaying-no-context-menu"></a>禁止显示任何现有上下文菜单并不显示上下文菜单  
 最后一个方案是编写一个完全禁止显示菜单的处理程序，这种情况并不常见。 如果某个给定控件不应显示上下文菜单，则可以通过更适当的方式来确保这一点，而不是在用户请求该菜单时将其取消。 但是，如果您想要使用该处理程序来禁止显示上下文菜单而不显示任何内容，则您 <xref:System.Windows.RoutedEventArgs.Handled%2A> 的处理程序 `true` 在事件数据中应简单地设置为。 <xref:System.Windows.Controls.ContextMenuService>负责显示上下文菜单的将检查控件上引发的事件的事件数据。 如果在路由中的任何位置标记该事件，则将 <xref:System.Windows.RoutedEventArgs.Handled%2A> 取消启动该事件的上下文菜单 "打开" 操作。  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceReopen](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacereopen)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType>
- [基元素概述](base-elements-overview.md)
- [ContextMenu 概述](../controls/contextmenu-overview.md)
