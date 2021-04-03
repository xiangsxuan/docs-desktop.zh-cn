---
title: 如何：使用触发器为 ListView 中的选定项设置样式
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
ms.openlocfilehash: ad64382b871bae9114a1e63257de3f8595376923
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972988"
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a>如何：使用触发器为 ListView 中的选定项设置样式
此示例演示如何为 <xref:System.Windows.Style.Triggers%2A> <xref:System.Windows.Controls.ListViewItem> 控件定义，以便当的属性值更改时 <xref:System.Windows.Controls.ListViewItem> ， <xref:System.Windows.Style> <xref:System.Windows.Controls.ListViewItem> 响应中的更改。  
  
## <a name="example"></a>示例  
 如果希望更改的以 <xref:System.Windows.Style> <xref:System.Windows.Controls.ListViewItem> 响应属性更改，请定义 <xref:System.Windows.Style.Triggers%2A> <xref:System.Windows.Style> 更改。  
  
 下面的示例定义一个 <xref:System.Windows.Trigger> ，它将 <xref:System.Windows.Controls.Control.Foreground%2A> 属性设置为， <xref:System.Windows.Media.Brushes.Blue%2A> 并将更改 <xref:System.Windows.FrameworkElement.Cursor%2A> 为，以显示 <xref:System.Windows.Input.CursorType.Hand> <xref:System.Windows.UIElement.IsMouseOver%2A> 属性更改为时的 `true` 。  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 下面的示例定义一个 <xref:System.Windows.MultiTrigger> ，它将的 <xref:System.Windows.Controls.Control.Foreground%2A> 属性设置 <xref:System.Windows.Controls.ListViewItem> 为， <xref:System.Windows.Media.Brushes.Yellow%2A> 当 <xref:System.Windows.Controls.ListViewItem> 为选定项并且具有键盘焦点时为。  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [操作指南主题](listview-how-to-topics.md)
- [ListView 概述](listview-overview.md)
- [GridView 概述](gridview-overview.md)
