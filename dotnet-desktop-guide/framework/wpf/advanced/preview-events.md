---
title: 预览事件
ms.date: 03/30/2017
helpviewer_keywords:
- Preview events [WPF]
- suppressing events [WPF]
- events [WPF], Preview
- events [WPF], suppressing
ms.assetid: b5032308-aa9c-4d02-af11-630ecec8df7e
ms.openlocfilehash: 3eb60e40ed4bb5ec9cc9bc1aa9f18a4aec8bca31
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667130"
---
# <a name="preview-events"></a>预览事件
预览事件，也称为隧道事件，是路由事件，其中路由的方向从应用程序根传到引发事件的元素，并在事件数据中报告为源。 并非所有事件方案都支持或要求预览事件;本主题介绍预览事件存在的情况，应用程序或组件应如何处理这些事件，以及在自定义组件或类中创建预览事件的情况可能是合适的。  
  
## <a name="preview-events-and-input"></a>预览事件和输入  
 通常在处理预览事件时，请注意在事件数据中标记已处理的事件。 在引发它的元素之外的任何元素上处理预览事件 (在事件数据) 中报告为源的元素，这会使元素无法提供处理它所源自的事件的机会。 有时，这是所需的结果，尤其是在控件的组合内的关系中存在相关元素时。  
  
 特别是对于输入事件，预览事件还会将事件数据实例与等效的冒泡事件共享。 如果使用预览版事件类处理程序将输入事件标记为已处理，则将不会调用冒泡 input 事件类处理程序。 或者，如果使用预览版事件实例处理程序将事件标记为已处理，则通常不会调用冒泡事件的处理程序。 类处理程序或实例处理程序可以通过调用的选项进行注册或附加，即使该事件标记为已处理，但这种方法并不常用。  
  
 有关类处理以及它如何与预览事件相关的详细信息，请参阅将 [路由事件标记为 "已处理" 和 "类处理"](marking-routed-events-as-handled-and-class-handling.md)。  
  
### <a name="working-around-event-suppression-by-controls"></a>通过控件解决事件禁止问题  
 通常使用预览事件的一种情况是对输入事件的复合控件处理。 有时，控件的作者会禁止某个事件从其控件发出，这可能是为了替换携带详细信息或表示更具体的行为的组件定义的事件。 例如， [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> <xref:System.Windows.UIElement.MouseLeftButtonDown> <xref:System.Windows.UIElement.MouseRightButtonDown> 由或其复合元素引发的禁止显示和冒泡事件， <xref:System.Windows.Controls.Button> 以捕获鼠标并引发 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 始终由自身引发的事件 <xref:System.Windows.Controls.Button> 。 事件及其数据仍沿路由继续，但由于将 <xref:System.Windows.Controls.Button> 事件数据标记为 <xref:System.Windows.RoutedEventArgs.Handled%2A> ，因此只会调用专门指示它们应在事例中操作的事件的处理程序 `handledEventsToo` 。  如果应用程序根的其他元素仍希望有机会处理控制抑制的事件，另一种方法是将处理程序附加到 `handledEventsToo` 指定为的代码中 `true` 。 但通常，一种更简单的方法是将所处理的路由方向更改为与输入事件等效的预览。 例如，如果控件禁止显示 <xref:System.Windows.UIElement.MouseLeftButtonDown> ，请改为尝试附加处理程序 <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> 。 此方法仅适用于基元素输入事件，例如 <xref:System.Windows.UIElement.MouseLeftButtonDown> 。 这些输入事件使用隧道/冒泡对，引发这两个事件，并共享事件数据。  
  
 上述每种方法都有副作用或限制。 处理预览事件的副作用是，在该点处理事件可能会禁用预期处理冒泡事件的处理程序，因此限制是在事件仍处于路由的预览部分时将事件标记为已处理是不是很好的做法。 此方法的限制 `handledEventsToo` 是，您不能 `handledEventsToo` 在中指定处理程序 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 作为属性，您必须在获取对要附加处理程序的元素的对象引用后，在代码中注册事件处理程序。  
  
## <a name="see-also"></a>请参阅

- [将路由事件标记为“已处理”和“类处理”](marking-routed-events-as-handled-and-class-handling.md)
- [路由事件概述](routed-events-overview.md)
