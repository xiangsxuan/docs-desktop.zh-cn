---
title: 为控件中的焦点设置样式以及 FocusVisualStyle
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard focus [WPF]
- focus [WPF], visual styling
- styles [WPF], focus visual style
ms.assetid: 786ac576-011b-4d72-913b-558deccb9b35
ms.openlocfilehash: 3d038f0e1687efb0c2516602e8d5cbf24a60b36c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973388"
---
# <a name="styling-for-focus-in-controls-and-focusvisualstyle"></a>为控件中的焦点设置样式以及 FocusVisualStyle
[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 提供两种用于在控件接收键盘焦点时更改其视觉外观的并行机制。 第一种机制是对 <xref:System.Windows.UIElement.IsKeyboardFocused%2A> 应用于控件的样式或模板中的属性使用属性 setter。 第二种机制是提供单独的样式作为属性的值 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> ; "焦点视觉样式" 为在控件顶部绘制的装饰器创建单独的可视化树，而不是通过替换控件或其他 UI 元素来更改它的可视化树。 本主题讨论上述每一种机制的适用情况。  

<a name="Purpose"></a>
## <a name="the-purpose-of-focus-visual-style"></a>焦点视觉样式的用途  
 焦点视觉样式功能提供一种通用“对象模型”，用于基于任何 UI 元素的键盘导航来引入视觉用户反馈。 即使未向控件应用新模板，或者不知道具体的模板组合，这也是可能的。  
  
 但是，正因为焦点视觉样式功能可以在不知道控件模板的情况下工作，所以必须限制可针对使用焦点视觉样式的控件显示的视觉反馈。 此功能实际执行的操作是在控件通过模板进行呈现来创建可视化树时在其上覆盖另一可视化树（装饰器）。 使用填充属性的样式定义此单独的可视化树 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 。  
  
<a name="Default"></a>
## <a name="default-focus-visual-style-behavior"></a>默认焦点视觉样式行为  
 焦点视觉样式仅在焦点操作由键盘启动时才起作用。 任何鼠标操作或者通过编程实现的焦点更改都会禁用焦点视觉样式模式。 有关焦点模式间区别的详细信息，请参阅[焦点概述](focus-overview.md)。  
  
 控件的主题包括默认焦点视觉样式行为，该焦点视觉样式成为主题中所有控件的焦点视觉样式。 此主题样式由静态键的值标识 <xref:System.Windows.SystemParameters.FocusVisualStyleKey%2A> 。 当在应用程序级声明自己的焦点视觉样式时，将替换主题中的这一默认样式行为。 或者，如果要定义整个主题，那么应同样使用这个键来为整个主题的默认行为定义样式。  
  
 在主题中，默认焦点视觉样式通常非常简单。 下面是一个近似的焦点视觉样式：  
  
```xaml  
<Style x:Key="{x:Static SystemParameters.FocusVisualStyleKey}">  
  <Setter Property="Control.Template">  
    <Setter.Value>  
      <ControlTemplate>  
        <Rectangle StrokeThickness="1"  
          Stroke="Black"  
          StrokeDashArray="1 2"  
          SnapsToDevicePixels="true"/>  
      </ControlTemplate>  
    </Setter.Value>  
  </Setter>  
</Style>  
```  
  
<a name="When"></a>
## <a name="when-to-use-focus-visual-styles"></a>何时使用焦点视觉样式  
 从概念上来说，应用于控件的焦点视觉样式的外观在所有控件上应该是一致的。 确保一致性的一种方法是仅在创作整个主题时才更改焦点视觉样式，这样主题中定义的每个控件都要么获得完全相同的焦点视觉样式，要么获得在视觉上与控件具有相关性的某一样式的变体。 或者，可能使用相同的样式（或类似的样式）来设置页面或 UI 中每个可通过键盘获得焦点的元素的样式。  
  
 不 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 属于主题的单独控件样式的设置并不是焦点视觉样式的预期用法。 这是因为控件间的不一致视觉行为会使用户对键盘焦点产生混乱的感觉。 如果要为键盘焦点设计特定于控件的行为，而这些行为在主题中特意不连贯，更好的方法是使用各个输入状态属性（如或）的样式中的触发器 <xref:System.Windows.UIElement.IsFocused%2A> <xref:System.Windows.UIElement.IsKeyboardFocused%2A> 。  
  
 焦点视觉样式专门作用于键盘焦点。 就其本身而言，焦点视觉样式是一种辅助功能。 如果希望针对任何类型的焦点来更改 UI（无论是通过鼠标、键盘还是编程方式），那么不应使用焦点视觉样式，而应在样式或模板中使用 setter 和触发器，它们根据常规焦点属性（如 <xref:System.Windows.UIElement.IsFocused%2A> 或 <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>）的值发生作用。  
  
<a name="How"></a>
## <a name="how-to-create-a-focus-visual-style"></a>如何创建焦点视觉样式  
 为焦点视觉样式创建的样式应始终具有 <xref:System.Windows.Style.TargetType%2A> 的 <xref:System.Windows.Controls.Control> 。 样式应主要包括 <xref:System.Windows.Controls.ControlTemplate> 。 不要将目标类型指定为将焦点视觉样式分配给的类型 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 。  
  
 由于目标类型始终为 <xref:System.Windows.Controls.Control> ，因此你必须使用所有控件共有的属性来进行样式， (使用类的属性 <xref:System.Windows.Controls.Control> 及其基类) 。 应创建将正确地用作 UI 元素的覆盖层、且不会隐藏控件的功能区域的模板。 通常，这意味着视觉反馈应显示在控件边距之外，或者显示为临时的或不显眼的效果（这样就不会阻止应用焦点视觉样式的控件上的命中测试）。 可在模板绑定中使用的属性，这些属性可用于确定覆盖模板的大小和位置 <xref:System.Windows.FrameworkElement.ActualHeight%2A> （包括、 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 、和） <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.Control.Padding%2A> 。  
  
<a name="Alternatives"></a>
## <a name="alternatives-to-using-a-focus-visual-style"></a>使用焦点视觉样式的替代方法  
 对于不适合使用焦点视觉样式的情况（因为仅设置单个控件的样式或希望对控件模板有更多的控制），存在许多其他可用的属性和技术，可用来创建响应焦点更改的视觉行为。  
  
 [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)中对触发器、setter 以及事件 setter 进行了详细介绍。 [路由事件概述](routed-events-overview.md)中对路由事件处理进行了介绍。  
  
### <a name="iskeyboardfocused"></a>IsKeyboardFocused  
 如果对键盘焦点特别感兴趣，则 <xref:System.Windows.UIElement.IsKeyboardFocused%2A> 可将依赖属性用于属性 <xref:System.Windows.Trigger> 。 对于定义专用于单个控件且可能与其他控件的键盘焦点行为在视觉上不匹配的键盘焦点行为，一个更适合的方法是使用样式或模板中的属性触发器。  
  
 另一个类似的依赖项属性是 <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> ，如果想要直观地调出键盘焦点位于控件内或控件的功能区域内的某个位置，则可能适合使用这种属性。 例如，你可能会放置 <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> 一个触发器，以便对多个控件进行分组的面板显示方式不同，即使键盘焦点可能更精确地位于该面板内的单个元素上。  
  
 你还可以使用事件 <xref:System.Windows.UIElement.GotKeyboardFocus> 和 <xref:System.Windows.UIElement.LostKeyboardFocus> (及其预览等效) 。 可以将这些事件用作的基础 <xref:System.Windows.EventSetter> ，也可以在代码隐藏中编写事件的处理程序。  
  
### <a name="other-focus-properties"></a>其他焦点属性  
 如果希望更改焦点以生成可视行为的所有可能原因，则应基于 <xref:System.Windows.UIElement.IsFocused%2A> 依赖项属性或 <xref:System.Windows.UIElement.GotFocus> 或用于的或 <xref:System.Windows.UIElement.LostFocus> 事件来构建资源库或触发器 <xref:System.Windows.EventSetter> 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [焦点概述](focus-overview.md)
- [输入概述](input-overview.md)
