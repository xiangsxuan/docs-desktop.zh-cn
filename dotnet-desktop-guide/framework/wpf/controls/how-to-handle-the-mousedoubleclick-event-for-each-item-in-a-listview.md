---
title: 如何：处理 ListView 中每一项的 MouseDoubleClick 事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 58c17697c5053be267893834e8364c531c1db4de
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973682"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>如何：处理 ListView 中每一项的 MouseDoubleClick 事件
若要在中处理项的事件 <xref:System.Windows.Controls.ListView> ，需要向每个中添加一个事件处理程序 <xref:System.Windows.Controls.ListViewItem> 。 当 <xref:System.Windows.Controls.ListView> 绑定到数据源时，您不会显式创建 <xref:System.Windows.Controls.ListViewItem> ，但您可以通过将添加到的样式来处理每个项的事件 <xref:System.Windows.EventSetter> <xref:System.Windows.Controls.ListViewItem> 。  
  
## <a name="example"></a>示例  
 下面的示例创建一个数据绑定 <xref:System.Windows.Controls.ListView> ，并创建一个 <xref:System.Windows.Style> 来向每个中添加一个事件处理程序 <xref:System.Windows.Controls.ListViewItem> 。  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 下面的示例处理 <xref:System.Windows.Controls.Control.MouseDoubleClick> 事件。  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> 虽然将绑定 <xref:System.Windows.Controls.ListView> 到数据源最常见，但你可以使用样式将事件处理程序添加到 <xref:System.Windows.Controls.ListViewItem> 非数据绑定中的每个， <xref:System.Windows.Controls.ListView> 无论你是否显式创建 <xref:System.Windows.Controls.ListViewItem> 。  有关显式和隐式创建的控件的详细信息 <xref:System.Windows.Controls.ListViewItem> ，请参阅 <xref:System.Windows.Controls.ItemsControl> 。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Xml.XmlElement>
- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [ListView 概述](listview-overview.md)
