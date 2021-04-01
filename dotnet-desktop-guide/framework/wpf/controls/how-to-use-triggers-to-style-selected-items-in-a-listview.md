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
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a><span data-ttu-id="8b5c5-102">如何：使用触发器为 ListView 中的选定项设置样式</span><span class="sxs-lookup"><span data-stu-id="8b5c5-102">How to: Use Triggers to Style Selected Items in a ListView</span></span>
<span data-ttu-id="8b5c5-103">此示例演示如何为 <xref:System.Windows.Style.Triggers%2A> <xref:System.Windows.Controls.ListViewItem> 控件定义，以便当的属性值更改时 <xref:System.Windows.Controls.ListViewItem> ， <xref:System.Windows.Style> <xref:System.Windows.Controls.ListViewItem> 响应中的更改。</span><span class="sxs-lookup"><span data-stu-id="8b5c5-103">This example shows how to define <xref:System.Windows.Style.Triggers%2A> for a <xref:System.Windows.Controls.ListViewItem> control so that when a property value of a <xref:System.Windows.Controls.ListViewItem> changes, the <xref:System.Windows.Style> of the <xref:System.Windows.Controls.ListViewItem> changes in response.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b5c5-104">示例</span><span class="sxs-lookup"><span data-stu-id="8b5c5-104">Example</span></span>  
 <span data-ttu-id="8b5c5-105">如果希望更改的以 <xref:System.Windows.Style> <xref:System.Windows.Controls.ListViewItem> 响应属性更改，请定义 <xref:System.Windows.Style.Triggers%2A> <xref:System.Windows.Style> 更改。</span><span class="sxs-lookup"><span data-stu-id="8b5c5-105">If you want the <xref:System.Windows.Style> of a <xref:System.Windows.Controls.ListViewItem> to change in response to property changes, define <xref:System.Windows.Style.Triggers%2A> for the <xref:System.Windows.Style> change.</span></span>  
  
 <span data-ttu-id="8b5c5-106">下面的示例定义一个 <xref:System.Windows.Trigger> ，它将 <xref:System.Windows.Controls.Control.Foreground%2A> 属性设置为， <xref:System.Windows.Media.Brushes.Blue%2A> 并将更改 <xref:System.Windows.FrameworkElement.Cursor%2A> 为，以显示 <xref:System.Windows.Input.CursorType.Hand> <xref:System.Windows.UIElement.IsMouseOver%2A> 属性更改为时的 `true` 。</span><span class="sxs-lookup"><span data-stu-id="8b5c5-106">The following example defines a <xref:System.Windows.Trigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property to <xref:System.Windows.Media.Brushes.Blue%2A> and changes the <xref:System.Windows.FrameworkElement.Cursor%2A> to display a <xref:System.Windows.Input.CursorType.Hand> when the <xref:System.Windows.UIElement.IsMouseOver%2A> property changes to `true`.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 <span data-ttu-id="8b5c5-107">下面的示例定义一个 <xref:System.Windows.MultiTrigger> ，它将的 <xref:System.Windows.Controls.Control.Foreground%2A> 属性设置 <xref:System.Windows.Controls.ListViewItem> 为， <xref:System.Windows.Media.Brushes.Yellow%2A> 当 <xref:System.Windows.Controls.ListViewItem> 为选定项并且具有键盘焦点时为。</span><span class="sxs-lookup"><span data-stu-id="8b5c5-107">The following example defines a <xref:System.Windows.MultiTrigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.ListViewItem> to <xref:System.Windows.Media.Brushes.Yellow%2A> when the <xref:System.Windows.Controls.ListViewItem> is the selected item and has keyboard focus.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a><span data-ttu-id="8b5c5-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b5c5-108">See also</span></span>

- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="8b5c5-109">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="8b5c5-109">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="8b5c5-110">ListView 概述</span><span class="sxs-lookup"><span data-stu-id="8b5c5-110">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="8b5c5-111">GridView 概述</span><span class="sxs-lookup"><span data-stu-id="8b5c5-111">GridView Overview</span></span>](gridview-overview.md)
