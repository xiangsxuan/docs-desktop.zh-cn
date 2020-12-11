---
title: 如何：在事件处理程序中查找源元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
ms.openlocfilehash: 9a49878c9ad8313903df4506796998fd43e2e749
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973478"
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a>如何：在事件处理程序中查找源元素
此示例演示如何在事件处理程序中查找源元素。  
  
## <a name="example"></a>示例  
 下面的示例演示 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 在代码隐藏文件中声明的事件处理程序。 当用户单击处理程序附加到的按钮时，处理程序将更改属性值。 处理程序代码使用 <xref:System.Windows.RoutedEventArgs.Source%2A> 事件自变量中报告的路由事件数据的属性来更改 <xref:System.Windows.FrameworkElement.Width%2A> 元素上的属性值 <xref:System.Windows.RoutedEventArgs.Source%2A> 。  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.RoutedEventArgs>
- [路由事件概述](routed-events-overview.md)
- [操作指南主题](events-how-to-topics.md)
