---
title: 属性更改事件
ms.date: 03/30/2017
helpviewer_keywords:
- dependency properties [WPF], change events
- property value changes [WPF]
- change events [WPF], property
- events [WPF], change in property values
- creating property triggers [WPF]
- property change events [WPF], types of
- property change events [WPF]
- property triggers [WPF]
- identifying changed property events [WPF]
- property triggers [WPF], definition of
ms.assetid: 0a7989df-9674-4cc1-bc50-5d8ef5d9c055
ms.openlocfilehash: 9b3bfce4765d849e8c3260ac17397d34dac3f1c8
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667117"
---
# <a name="property-change-events"></a>属性更改事件
[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 定义几个为响应属性值的更改而引发的事件。 该属性通常是依赖项属性。 事件本身有时是路由事件，有时是标准公共语言运行时 (CLR) 事件。 事件的定义因具体情况而异，因为有些属性更改更适于通过元素树路由，而其他属性更改则通常只与属性发生更改的对象有关。  
  
## <a name="identifying-a-property-change-event"></a>标识属性更改事件  
 并非所有报告属性更改的事件都通过签名模式或命名模式显式地标识为属性更改事件。 通常，SDK 文档中的事件说明指示事件是否直接绑定到属性值更改，并在属性和事件之间提供交叉引用。  
  
### <a name="routedpropertychanged-events"></a>RoutedPropertyChanged 事件  
 某些事件使用显式用于属性更改事件的事件数据类型和委托。 事件数据类型为 <xref:System.Windows.RoutedPropertyChangedEventArgs%601> ，委托为 <xref:System.Windows.RoutedPropertyChangedEventHandler%601> 。 事件数据和委托都具有用于在定义处理程序时指定更改属性实际类型的泛型类型参数。 事件数据包含两个属性： <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A> 和 <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A> ，它们随后作为事件数据中的类型参数进行传递。  
  
 名称中的“Routed”部分表示属性更改事件注册为路由事件。 路由属性更改事件的好处是，如果子元素（控件的复合部分）上的属性更改了值，控件的顶层可以接收到属性更改事件。 例如，可以创建一个包含控件的控件， <xref:System.Windows.Controls.Primitives.RangeBase> 例如 <xref:System.Windows.Controls.Slider> 。 如果属性的值 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 在滑块部分发生更改，则您可能希望在父控件而不是在部件上处理此更改。  
  
 因为有一个旧值和一个新值，所以很可能使用此事件处理程序作为属性值的验证程序。 但是，这不是大多数属性更改事件的设计意图。 通常，提供这些值是为了能够在代码的其他逻辑领域处理这些值，但实际上，在事件处理程序内更改值并不明智，并且可能导致意外的递归，具体取决于处理程序的实现方式。  
  
 如果您的属性是自定义依赖属性，或者您使用的是您在其中定义了实例化代码的派生类，则可以使用更好的机制来跟踪属性系统中内置的属性更改 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ：属性系统回调 <xref:System.Windows.CoerceValueCallback> 和 <xref:System.Windows.PropertyChangedCallback> 。 若要深入了解如何使用 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 属性系统进行验证和强制转换，请参阅[依赖属性回调和验证](dependency-property-callbacks-and-validation.md)和[自定义依赖属性](custom-dependency-properties.md)。  
  
### <a name="dependencypropertychanged-events"></a>DependencyPropertyChanged 事件  
 作为属性更改事件方案的一部分的另一对类型是 <xref:System.Windows.DependencyPropertyChangedEventArgs> 和 <xref:System.Windows.DependencyPropertyChangedEventHandler> 。 不会路由这些属性更改的事件;它们是标准 CLR 事件。 <xref:System.Windows.DependencyPropertyChangedEventArgs> 是异常的事件数据报告类型，因为它不是从派生的 <xref:System.EventArgs> <xref:System.Windows.DependencyPropertyChangedEventArgs> ，而是结构，而不是类。  
  
 使用 <xref:System.Windows.DependencyPropertyChangedEventArgs> 和的事件 <xref:System.Windows.DependencyPropertyChangedEventHandler> 比事件略有不同 `RoutedPropertyChanged` 。 使用这些类型的事件的一个示例是 <xref:System.Windows.UIElement.IsMouseCapturedChanged> 。  
  
 与类似 <xref:System.Windows.RoutedPropertyChangedEventArgs%601> ， <xref:System.Windows.DependencyPropertyChangedEventArgs> 还报告属性的新旧值。 此外，关于如何处理这些值的注意事项也同样适用；通常不建议为响应事件而尝试在发送方再次更改值。  
  
## <a name="property-triggers"></a>属性触发器  
 与属性更改事件密切相关的一个概念是属性触发器。 属性触发器是在样式或模板内创建的，通过它可以创建基于分配了属性触发器的属性的值的条件行为。  
  
 属性触发器的属性必须是依赖项属性。 它可以是（且通常是）只读依赖项属性。 判断控件公开的依赖项属性是否至少部分设计为属性触发器的一个好方法是查看属性名称是否以“Is”开头。 采用此命名规则的属性通常是只读的布尔依赖项属性，其属性的主要作用是报告可能与实时 UI 具有因果关系的控件状态，因此它是一个属性触发器候选。  
  
 其中一些属性还具有专用属性更改事件。 例如，属性 <xref:System.Windows.UIElement.IsMouseCaptured%2A> 具有属性 changed 事件 <xref:System.Windows.UIElement.IsMouseCapturedChanged> 。 属性本身是只读的，它的值由输入系统调整，并且输入系统 <xref:System.Windows.UIElement.IsMouseCapturedChanged> 在每次实时更改时引发。  
  
 与真正的属性更改事件相比，使用属性触发器来处理属性更改具有一些限制。  
  
 属性触发器通过完全匹配逻辑来工作。 指定一个属性和一个值，该值指示触发器将作用于的特定值。例如： `<Setter Property="IsMouseCaptured" Value="true"> ... </Setter>` 。 由于此限制，大多数属性触发器用法都将针对布尔属性或者采用专用枚举值的属性，其可能值范围是可管理的，足以为每种情况定义一个触发器。 或者属性触发器可能仅仅用于特殊值，例如，当项计数达到零，却没有触发器来处理当属性值再次从零变为其他值（此处可能需要代码事件处理程序，或者当值不为零时再次从触发器状态切换回来的默认行为，而非针对所有情况的触发器）。  
  
 属性触发器语法与编程中的“if”语句类似。 如果触发器条件为 true，将“执行”属性触发器的“主体”。 属性触发器的“主体”是标记，而不是代码。 此标记限制为使用一个或多个 <xref:System.Windows.Setter> 元素设置要应用样式或模板的对象的其他属性。  
  
 若要偏移具有各种可能值的属性触发器的 "if" 条件，通常建议使用将该属性值设置为默认值 <xref:System.Windows.Setter> 。 这样一来， <xref:System.Windows.Trigger> 当触发器条件为 true 时，所包含的资源库将具有优先级，并且 <xref:System.Windows.Setter> <xref:System.Windows.Trigger> 当触发器条件为 false 时，不在中的将优先。  
  
 属性触发器通常适合于一个或多个外观属性应基于同一元素的其他属性的状态而更改的情况。  
  
 若要深入了解属性触发器，请参阅[样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)。  
  
## <a name="see-also"></a>请参阅

- [路由事件概述](routed-events-overview.md)
- [依赖项属性概述](dependency-properties-overview.md)
