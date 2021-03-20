---
title: 如何：创建自定义路由事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], creating
- events [WPF], routing
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
ms.openlocfilehash: 21466bda8403bde30499ace62c0f70c9c22120e5
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665947"
---
# <a name="how-to-create-a-custom-routed-event"></a>如何：创建自定义路由事件
若要使自定义事件支持事件路由，需要 <xref:System.Windows.RoutedEvent> 使用 <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> 方法注册。 本示例演示了创建自定义路由事件的基本原理。  
  
## <a name="example"></a>示例  
 如下面的示例中所示，您首先 <xref:System.Windows.RoutedEvent> 使用方法注册 <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> 。 按照约定， <xref:System.Windows.RoutedEvent> 静态字段名称应以后缀 ***事件*** 结束。 在此示例中，事件的名称为 `Tap` ，事件的路由策略是 <xref:System.Windows.RoutingStrategy.Bubble> 。 注册调用后，可以为事件提供添加和删除公共语言运行时 (CLR) 事件访问器。  
  
 请注意，尽管事件在此特定示例中是通过 `OnTap` 虚拟方法引发的，但引发事件的方式或事件响应更改的方式取决于你的需要。  
  
 另请注意，此示例基本上实现了的整个子类 <xref:System.Windows.Controls.Button> ; 该子类构建为单独的程序集，然后在单独的页上实例化为自定义类 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。 这是为了说明这样一个概念：子类化的控件可以插入到由其他控件组成的树中，在这种情况下，这些控件上的自定义事件具有与任何固有 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 元素完全相同的事件路由功能。  
  
 [!code-csharp[RoutedEventCustom#CustomClass](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 隧道事件是以相同方式创建的，但 <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> <xref:System.Windows.RoutingStrategy.Tunnel> 在注册调用中设置为。 按照约定，[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 中的隧道事件以单词“Preview”开头。  
  
 若要查看浮升事件的工作原理示例，请参阅[处理路由事件](how-to-handle-a-routed-event.md)。  
  
## <a name="see-also"></a>请参阅

- [路由事件概述](routed-events-overview.md)
- [输入概述](input-overview.md)
- [控件创作概述](../controls/control-authoring-overview.md)
