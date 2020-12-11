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
# <a name="how-to-find-the-source-element-in-an-event-handler"></a><span data-ttu-id="75176-102">如何：在事件处理程序中查找源元素</span><span class="sxs-lookup"><span data-stu-id="75176-102">How to: Find the Source Element in an Event Handler</span></span>
<span data-ttu-id="75176-103">此示例演示如何在事件处理程序中查找源元素。</span><span class="sxs-lookup"><span data-stu-id="75176-103">This example shows how to find the source element in an event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75176-104">示例</span><span class="sxs-lookup"><span data-stu-id="75176-104">Example</span></span>  
 <span data-ttu-id="75176-105">下面的示例演示 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 在代码隐藏文件中声明的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="75176-105">The following example shows a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler that is declared in a code-behind file.</span></span> <span data-ttu-id="75176-106">当用户单击处理程序附加到的按钮时，处理程序将更改属性值。</span><span class="sxs-lookup"><span data-stu-id="75176-106">When a user clicks the button that the handler is attached to, the handler changes a property value.</span></span> <span data-ttu-id="75176-107">处理程序代码使用 <xref:System.Windows.RoutedEventArgs.Source%2A> 事件自变量中报告的路由事件数据的属性来更改 <xref:System.Windows.FrameworkElement.Width%2A> 元素上的属性值 <xref:System.Windows.RoutedEventArgs.Source%2A> 。</span><span class="sxs-lookup"><span data-stu-id="75176-107">The handler code uses the <xref:System.Windows.RoutedEventArgs.Source%2A> property of the routed event data that is reported in the event arguments to change the <xref:System.Windows.FrameworkElement.Width%2A> property value on the <xref:System.Windows.RoutedEventArgs.Source%2A> element.</span></span>  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="75176-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75176-108">See also</span></span>

- <xref:System.Windows.RoutedEventArgs>
- [<span data-ttu-id="75176-109">路由事件概述</span><span class="sxs-lookup"><span data-stu-id="75176-109">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="75176-110">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="75176-110">How-to Topics</span></span>](events-how-to-topics.md)
