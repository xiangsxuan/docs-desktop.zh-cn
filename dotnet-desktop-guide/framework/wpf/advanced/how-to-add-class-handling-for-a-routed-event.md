---
title: 如何：为路由事件添加类处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], class handlers
- task_core_add_class_handling_routed_properties [WPF]
- class handlers [WPF], routed events
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
ms.openlocfilehash: 7b897954cbdab461dc0305c6290e67c1af5282c3
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972474"
---
# <a name="how-to-add-class-handling-for-a-routed-event"></a>如何：为路由事件添加类处理
路由事件可以通过类处理程序或路由中任何给定节点上的实例处理程序来处理。 首先调用类处理程序，类实现可使用这些处理程序来取消实例处理中的事件，或对由基类拥有的事件引入其他特定于事件的行为。 此示例阐释了实现类处理程序的两个紧密相关的技术。  
  
## <a name="example"></a>示例  
 此示例使用基于面板的自定义类 <xref:System.Windows.Controls.Canvas> 。 应用程序的基本前提是自定义类在其子元素上引入了行为，包括截获鼠标左键单击并标记其处理，然后才会调用子元素类或其上的任何实例处理程序。  
  
 <xref:System.Windows.UIElement>类公开了一个虚拟方法，该方法 <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> 通过只重写事件对事件启用类处理。 如果类的层次结构中的某个位置有此类处理方法，则这是实现类处理的最简单方法。 下面的代码演示了 <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> 从派生的 "MyEditContainer" 中的实现 <xref:System.Windows.Controls.Canvas> 。 实现会将事件标记为已在参数中处理，然后添加一些代码，使源元素成为基本的可见更改。  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 如果基类或该特定方法中没有可用的虚拟，则可以使用类的实用工具方法直接添加类处理 <xref:System.Windows.EventManager> <xref:System.Windows.EventManager.RegisterClassHandler%2A> 。 只应在添加类处理的类的静态初始化中调用此方法。 此示例为添加了另一个处理程序 <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> ，在这种情况下，已注册的类为自定义类。 相反，当使用虚方法时，已注册的类实际上是 <xref:System.Windows.UIElement> 基类。 如果基类和子类都注册了类处理，则首先调用子类处理程序。 应用程序中的行为是：首先，此处理程序会显示其消息框，然后将显示虚方法的处理程序中的可视更改。  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.EventManager>
- [将路由事件标记为“已处理”和“类处理”](marking-routed-events-as-handled-and-class-handling.md)
- [处理路由事件](how-to-handle-a-routed-event.md)
- [路由事件概述](routed-events-overview.md)
