---
title: 如何：为 ListView 创建自定义视图模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 6c6c8475849354493330105e93316d6424ebe2f3
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604272"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a>如何：为 ListView 创建自定义视图模式

此示例演示如何为控件创建自定义 <xref:System.Windows.Controls.ListView.View%2A> 模式 <xref:System.Windows.Controls.ListView> 。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Controls.ViewBase>为控件创建自定义视图时，必须使用类 <xref:System.Windows.Controls.ListView> 。 下面的示例演示一个名为的视图模式 `PlainView` ，该类派生自 <xref:System.Windows.Controls.ViewBase> 类。  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 若要将样式应用于自定义视图，请使用 <xref:System.Windows.Style> 类。 下面的示例定义 <xref:System.Windows.Style> `PlainView` 视图模式的。 在上面的示例中，此样式设置为 <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> 为定义的属性的值 `PlainView` 。  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 若要在自定义视图模式下定义数据布局，请定义一个 <xref:System.Windows.DataTemplate> 对象。 下面的示例定义一个 <xref:System.Windows.DataTemplate> ，它可用于在 `PlainView` 视图模式下显示数据。  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 下面的示例演示如何为 <xref:System.Windows.ResourceKey> `PlainView` 使用 <xref:System.Windows.DataTemplate> 上一示例中定义的的视图模式定义。  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <xref:System.Windows.Controls.ListView>如果将 <xref:System.Windows.Controls.ListView.View%2A> 属性设置为资源键，则控件可以使用自定义视图。 下面的示例演示如何将指定 `PlainView` 为的查看模式 <xref:System.Windows.Controls.ListView> 。  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 有关完整示例，请参阅 [具有多个视图的 listview (c # ) ](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) 或 [包含多个视图的 listview (Visual Basic) ](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [操作指南主题](listview-how-to-topics.md)
- [ListView 概述](listview-overview.md)
- [GridView 概述](gridview-overview.md)
