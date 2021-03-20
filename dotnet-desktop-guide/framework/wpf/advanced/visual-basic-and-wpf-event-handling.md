---
title: 处理中的事件 Visual Basic
ms.date: 03/30/2017
helpviewer_keywords:
- Visual Basic [WPF], event handlers
- event handlers [WPF], Visual Basic
ms.assetid: ad4eb9aa-3afc-4a71-8cf6-add3fbea54a1
ms.openlocfilehash: f367fa5625cc0ef4dfc2a0d84fff13ac39c27074
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664075"
---
# <a name="visual-basic-and-wpf-event-handling"></a>Visual Basic 和 WPF 事件处理
具体而言，对于 Microsoft Visual Basic .NET 语言，可以使用特定于语言的 `Handles` 关键字将事件处理程序与实例关联，而不是将事件处理程序附加到特性或使用 <xref:System.Windows.UIElement.AddHandler%2A> 方法。 但是，用于将处理程序附加到实例的 `Handles` 技术存在一些限制，因为 `Handles` 语法不支持 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 事件系统的某些特定路由事件功能。  
  
## <a name="using-handles-in-a-wpf-application"></a>在 WPF 应用程序中使用“Handles”  
 通过 `Handles` 连接到实例和事件的事件处理程序必须全部在实例的分部类声明中定义，此要求也适用于通过元素上的特性值进行分配的事件处理程序。 只能 `Handles` 为页上的元素指定，该元素的 <xref:System.Windows.FrameworkContentElement.Name%2A> 属性值 (或) 声明了 [x：Name 指令](/dotnet/desktop-wpf/xaml-services/xname-directive) 。 这是因为中的会 <xref:System.Windows.FrameworkContentElement.Name%2A> [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 创建支持实例所必需的实例引用 *。* 语法所需的事件引用格式 `Handles` 。 无需引用即可使用的唯一元素 `Handles` 是用于 <xref:System.Windows.FrameworkContentElement.Name%2A> 定义分部类的根元素实例。  
  
 可以通过使用逗号分隔 `Handles` 后面的 Instance.Event 引用，向多个元素分配相同的处理程序。  
  
 可以使用 `Handles` 将多个处理程序分配给同一 Instance.Event 引用。 请勿对 `Handles` 引用中特定处理程序的提供顺序赋予任何重要性；应假定可按任何顺序调用处理相同事件的处理程序。  
  
 若要删除在声明中添加的处理程序 `Handles` ，可以调用 <xref:System.Windows.UIElement.RemoveHandler%2A> 。  
  
 如果要将处理程序附加到实例成员表中用于定义要处理的事件的实例，可使用 `Handles` 附加路由事件的处理程序。 对于路由事件，附加了的处理程序 `Handles` 遵循的路由规则与作为特性附加的处理程序 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 或的公共签名相同 <xref:System.Windows.UIElement.AddHandler%2A> 。 这意味着，如果事件已标记为已处理 (<xref:System.Windows.RoutedEventArgs.Handled%2A> 事件数据) 中的属性 `True` ，则不会调用附加的处理程序 `Handles` 来响应该事件实例。 可通过路由中另一个元素上的实例处理程序，或通过在路由中当前元素或更早元素上进行类处理，将事件标记为已处理。 对于可支持成对的隧道事件/冒泡事件的输入事件，隧道路由可能已将事件对标记为已处理。 有关路由事件的详细信息，请参阅[路由事件概述](routed-events-overview.md)。  
  
## <a name="limitations-of-handles-for-adding-handlers"></a>添加处理程序时的“Handles”限制  
 `Handles` 无法引用附加事件的处理程序。 必须对该附加事件使用 `add` 访问方法，或使用 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中的 typename.eventname 事件特性。 有关详细信息，请参阅[路由事件概述](routed-events-overview.md)。  
  
 对于路由事件，只能使用 `Handles` 为实例成员表中存在该事件的实例分配处理程序。 但是，对于一般的路由事件，父元素可以是来自子元素的事件的侦听器，即使该父元素的成员表中没有此事件也是如此。 在特性语法中，这可以通过 typename.membername 特性形式来指定，此形式限定哪种类型实际定义要处理的事件。 例如， `Page` 未定义任何事件) 的父 (`Click` 可以通过在窗体中分配属性处理程序来侦听按钮单击事件 `Button.Click` 。 但 `Handles` 不支持 typename.membername 形式，因为它必须支持与该形式冲突的 Instance.Event 形式。 有关详细信息，请参阅[路由事件概述](routed-events-overview.md)。  
  
 `Handles` 无法附加针对标记为已处理的事件而调用的处理程序。 相反，您必须使用代码并调用的 `handledEventsToo` 重载 <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> 。  
  
> [!NOTE]
> 在 `Handles` XAML 中为同一事件指定事件处理程序时，请不要在 Visual Basic 代码中使用语法。 在这种情况下，将调用事件处理程序两次。  
  
## <a name="how-wpf-implements-handles-functionality"></a>WPF 如何实现“Handles”功能  
 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)]编译页面时，中间文件将声明 `Friend` `WithEvents` 对页面上的每个元素的引用，该 <xref:System.Windows.FrameworkContentElement.Name%2A> 属性集的属性设置 (或) 声明了[x：Name 指令](/dotnet/desktop-wpf/xaml-services/xname-directive)。 每个命名实例都可能是可通过 `Handles` 分配给处理程序的元素。  
  
> [!NOTE]
> 在 Visual Studio 中，IntelliSense 可以显示已完成的元素，可用于 `Handles` 页面中的引用。 但是，这可能需要执行一个编译传递，以便中间文件可以填充所有 `Friends` 引用。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.UIElement.AddHandler%2A>
- [将路由事件标记为“已处理”和“类处理”](marking-routed-events-as-handled-and-class-handling.md)
- [路由事件概述](routed-events-overview.md)
- [XAML 概述 (WPF)](/dotnet/desktop-wpf/fundamentals/xaml)
