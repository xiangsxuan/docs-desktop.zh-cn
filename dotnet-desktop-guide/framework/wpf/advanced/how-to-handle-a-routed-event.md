---
title: 如何：处理路由事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], handling
- bubbling events [WPF]
ms.assetid: 157787b4-f469-4047-8777-5b034145f32e
ms.openlocfilehash: 3be6cdc6af28469f316ba1b5c8cf7c2e076ca6b7
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665921"
---
# <a name="how-to-handle-a-routed-event"></a>如何：处理路由事件
本示例演示了浮升事件的工作原理，以及如何编写可处理路由事件数据的处理程序。  
  
## <a name="example"></a>示例  
 在 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 中，元素以元素树结构形式排列。 父元素可以参与处理最初由元素树中的子元素引发的事件。 这都是因为事件路由。  
  
 路由事件通常遵循以下两个路由策略之一：浮升和隧道。 此示例重点介绍冒泡事件，并使用 <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=nameWithType> 事件来显示路由的工作原理。  
  
 下面的示例创建两个 <xref:System.Windows.Controls.Button> 控件，并使用 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 特性语法将事件处理程序附加到公共父元素，在此示例中为 <xref:System.Windows.Controls.StackPanel> 。 <xref:System.Windows.Controls.Button>该示例使用特性语法将事件处理程序附加到父元素，而不是为每个子元素附加单独的事件处理程序 <xref:System.Windows.Controls.StackPanel> 。 此事件处理模式展示了如何使用事件路由技术来减少附加处理程序的元素数。 每个 <xref:System.Windows.Controls.Button> 路由通过父元素的所有冒泡事件。  
  
 请注意，在父 <xref:System.Windows.Controls.StackPanel> 元素上， <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 指定为属性的事件名称是通过命名类进行部分限定的 <xref:System.Windows.Controls.Button> 。 <xref:System.Windows.Controls.Button>类是 <xref:System.Windows.Controls.Primitives.ButtonBase> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 在其成员列表中具有事件的派生类。 如果要处理的事件不在附加路由事件处理程序的元素的成员列表中，则有必要使用这种部分限定技术来附加事件处理程序。  
  
 [!code-xaml[RoutedEventHandle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml#xaml)]  
  
 下面的示例处理 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件。  该示例会报告哪个元素处理事件以及哪个元素引发事件。 用户单击任一按钮时都将执行事件处理程序。  
  
 [!code-csharp[RoutedEventHandle#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventHandle#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventHandle/VisualBasic/MainWindow.xaml.vb#handler)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.RoutedEvent>
- [输入概述](input-overview.md)
- [路由事件概述](routed-events-overview.md)
- [操作指南主题](events-how-to-topics.md)
- [XAML 语法详述](xaml-syntax-in-detail.md)
