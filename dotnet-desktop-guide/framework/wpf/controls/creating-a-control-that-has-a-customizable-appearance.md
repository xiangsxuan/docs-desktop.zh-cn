---
title: 创建具有可自定义外观的控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], customizing
- VisualStateManager [WPF], managing the state of a control
- ControlTemplate [WPF], customizing appearance
- controls [WPF], defining the visual structure and behavior of
- customizing appearance [WPF], ControlTemplate
- managing control states [WPF], VisualStateManager
- VisualStateManager [WPF], best practice
ms.assetid: 9e356d3d-a3d0-4b01-a25f-2d43e4d53fe5
ms.openlocfilehash: 4fc034085e5ed2c05465ec09f028f7ba5dd67164
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104668345"
---
# <a name="creating-a-control-that-has-a-customizable-appearance"></a>创建具有可自定义外观的控件

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 使您能够创建可自定义外观的控件。 例如，你可以通过创建新的来更改的外观，而 <xref:System.Windows.Controls.CheckBox> 不是设置属性将执行的操作 <xref:System.Windows.Controls.ControlTemplate> 。 下图显示了一个 <xref:System.Windows.Controls.CheckBox> ，它使用默认的 <xref:System.Windows.Controls.ControlTemplate> 和 <xref:System.Windows.Controls.CheckBox> 使用自定义的 <xref:System.Windows.Controls.ControlTemplate> 。

![一个具有默认控件模板的复选框。](./media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")
一个具有默认控件模板的复选框

![一个具有自定义控件模板的复选框。](./media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")
一个具有自定义控件模板的复选框

如果在创建控件时遵循 "部件" 和 "状态" 模型，则可自定义控件的外观。 设计器工具（如 Blend for Visual Studio）支持部件和状态模型，因此，在遵循此模型时，可以在这些类型的应用程序中自定义控件。  本主题讨论了部件和状态模型，以及如何在创建自己的控件时执行该操作。 本主题使用自定义控件的一个示例 `NumericUpDown` 来说明此模型的原理。  `NumericUpDown`控件显示一个数值，用户可以通过单击控件的按钮来增加或减少该值。  下图显示了 `NumericUpDown` 本主题中讨论的控件。

![NumericUpDown 自定义控件。](./media/ndp-numericupdown.png "NDP_NumericUPDown")
自定义 NumericUpDown 控件

本主题包含以下各节：

- [必备条件](#prerequisites)

- [部件和状态模型](#parts_and_states_model)

- [定义 System.windows.controls.controltemplate> 中控件的可视结构和可视行为](#defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate)

- [在代码中使用部分 System.windows.controls.controltemplate>](#using_parts_of_the_controltemplate_in_code)

- [提供控件协定](#providing_the_control_contract)

- [完整示例](#complete_example)

<a name="prerequisites"></a>

## <a name="prerequisites"></a>必备条件

本主题假设你知道如何为现有控件创建新 <xref:System.Windows.Controls.ControlTemplate> 的，熟悉控件协定上的元素，并了解为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)中所述的概念。

> [!NOTE]
> 若要创建可自定义其外观的控件，您必须创建一个继承自的 <xref:System.Windows.Controls.Control> 类或其子类之一的控件 <xref:System.Windows.Controls.UserControl> 。  从继承的控件 <xref:System.Windows.Controls.UserControl> 是可快速创建的控件，但不使用， <xref:System.Windows.Controls.ControlTemplate> 并且您无法自定义其外观。

<a name="parts_and_states_model"></a>

## <a name="parts-and-states-model"></a>部件和状态模型

部件和状态模型指定如何定义控件的可视结构和可视行为。 若要遵循 "部件" 和 "状态" 模型，应执行以下操作：

- 定义控件的中的可视结构和可视行为 <xref:System.Windows.Controls.ControlTemplate> 。

- 当控件的逻辑与控件模板的各个部分进行交互时，请遵循某些最佳实践。

- 提供控件协定以指定应包含在中的内容 <xref:System.Windows.Controls.ControlTemplate> 。

当你在控件的中定义可视结构和可视行为时 <xref:System.Windows.Controls.ControlTemplate> ，应用程序作者可以通过创建新的 <xref:System.Windows.Controls.ControlTemplate> 而不是编写代码来更改控件的可视结构和视觉行为。   您必须提供一个控件协定，用于告知应用程序作者 <xref:System.Windows.FrameworkElement> 应在中定义哪些对象和状态 <xref:System.Windows.Controls.ControlTemplate> 。 当与中的部分进行交互时，应遵循一些最佳做法， <xref:System.Windows.Controls.ControlTemplate> 以便控件正确地处理不完整的 <xref:System.Windows.Controls.ControlTemplate> 。  如果遵循这三个原则，应用程序作者可以像对附带的 <xref:System.Windows.Controls.ControlTemplate> 控件一样轻松地为控件创建 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  以下部分详细说明每个建议。

<a name="defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate"></a>

## <a name="defining-the-visual-structure-and-visual-behavior-of-a-control-in-a-controltemplate"></a>定义 System.windows.controls.controltemplate> 中控件的可视结构和可视行为

使用 "部件" 和 "状态" 模型创建自定义控件时，可以在其逻辑中定义控件的可视结构和可视行为， <xref:System.Windows.Controls.ControlTemplate> 而不是定义其逻辑。  控件的可视结构是 <xref:System.Windows.FrameworkElement> 构成控件的对象的组合。  视觉对象行为是控件在处于某种状态时的显示方式。   有关创建一个 <xref:System.Windows.Controls.ControlTemplate> 指定控件的可视结构和可视行为的详细信息，请参阅为 [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)。

在控件的示例中 `NumericUpDown` ，可视结构包括两个 <xref:System.Windows.Controls.Primitives.RepeatButton> 控件和一个 <xref:System.Windows.Controls.TextBlock> 。  如果在控件的代码中添加这些控件 `NumericUpDown` -在其构造函数中，例如，这些控件的位置将为方式更改。  你应在中定义控件的可视结构和可视行为，而不是在其代码中定义它 <xref:System.Windows.Controls.ControlTemplate> 。  然后，应用程序开发人员可以自定义按钮的位置， <xref:System.Windows.Controls.TextBlock> 并指定当为负时所发生的行为， `Value` 因为 <xref:System.Windows.Controls.ControlTemplate> 可以被替换。

下面的示例演示了控件的可视结构 `NumericUpDown` ，其中包括 <xref:System.Windows.Controls.Primitives.RepeatButton> 要增加的 `Value` 、 <xref:System.Windows.Controls.Primitives.RepeatButton> 要减小的 `Value` 以及 <xref:System.Windows.Controls.TextBlock> 要显示的 `Value` 。

[!code-xaml[VSMCustomControl#VisualStructure](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#visualstructure)]

控件的可视行为 `NumericUpDown` 是：如果该值为负数，则该值为红色字体。  如果在 <xref:System.Windows.Controls.TextBlock.Foreground%2A> <xref:System.Windows.Controls.TextBlock> 为负时在代码中更改的 `Value` ， `NumericUpDown` 将始终显示一个红色的负值。 <xref:System.Windows.Controls.ControlTemplate>通过将对象添加到，可以在中指定控件的可视行为 <xref:System.Windows.VisualState> <xref:System.Windows.Controls.ControlTemplate> 。  下面的示例演示了 <xref:System.Windows.VisualState> `Positive` 和状态的对象 `Negative` 。  `Positive` 与 `Negative` 互斥 (控件始终只是两个) 中的一种，因此该示例将 <xref:System.Windows.VisualState> 对象置于单个中 <xref:System.Windows.VisualStateGroup> 。  当控件进入 `Negative` 状态时，的将 <xref:System.Windows.Controls.TextBlock.Foreground%2A> <xref:System.Windows.Controls.TextBlock> 变为红色。  当控件处于 `Positive` 状态时，将 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 返回到其原始值。  为 <xref:System.Windows.VisualState> <xref:System.Windows.Controls.ControlTemplate> [控件创建模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)中进一步讨论了在中定义对象。

> [!NOTE]
> 请确保设置 <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> 的根的附加属性 <xref:System.Windows.FrameworkElement> <xref:System.Windows.Controls.ControlTemplate> 。

[!code-xaml[VSMCustomControl#ValueStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]

<a name="using_parts_of_the_controltemplate_in_code"></a>

## <a name="using-parts-of-the-controltemplate-in-code"></a>在代码中使用部分 System.windows.controls.controltemplate>

<xref:System.Windows.Controls.ControlTemplate>作者可能会忽略 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.VisualState> 对象，无论是有意还是错误，但您的控件的逻辑可能需要这些部件才能正常工作。 "部件" 和 "状态" 模型指定控件应能复原 <xref:System.Windows.Controls.ControlTemplate> 缺少的 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.VisualState> 对象。  如果中 <xref:System.Windows.FrameworkElement> 缺少、或，则控件不应引发异常，也不会报告错误 <xref:System.Windows.VisualState> <xref:System.Windows.VisualStateGroup> <xref:System.Windows.Controls.ControlTemplate> 。 本部分介绍与 <xref:System.Windows.FrameworkElement> 对象和管理状态交互的建议做法。

### <a name="anticipate-missing-frameworkelement-objects"></a>预计缺少 FrameworkElement 对象

当你在 <xref:System.Windows.FrameworkElement> 中定义对象时 <xref:System.Windows.Controls.ControlTemplate> ，控件的逻辑可能需要与其中一些对象进行交互。  例如， `NumericUpDown` 控件订阅按钮的 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件以增大或减小 `Value` ，并将的 <xref:System.Windows.Controls.TextBlock.Text%2A> 属性设置 <xref:System.Windows.Controls.TextBlock> 为 `Value` 。 如果自定义 <xref:System.Windows.Controls.ControlTemplate> 省略了 <xref:System.Windows.Controls.TextBlock> 或按钮，则控件可以接受其一些功能，但应确保控件不会导致错误。 例如，如果不 <xref:System.Windows.Controls.ControlTemplate> 包含要更改的按钮 `Value` ，则 `NumericUpDown` 会丢失该功能，但使用的应用程序 <xref:System.Windows.Controls.ControlTemplate> 将继续运行。

以下做法可确保控件正确响应缺少的 <xref:System.Windows.FrameworkElement> 对象：

1. `x:Name`为 <xref:System.Windows.FrameworkElement> 需要在代码中引用的每个设置属性。

2. 定义要与之交互的每个的专用属性 <xref:System.Windows.FrameworkElement> 。

3. 订阅和取消订阅控件在 <xref:System.Windows.FrameworkElement> 属性的 set 访问器中处理的任何事件。

4. <xref:System.Windows.FrameworkElement>在方法中设置在步骤2中定义的属性 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> 。 这是 <xref:System.Windows.FrameworkElement> 中的可用于控件的最早的 <xref:System.Windows.Controls.ControlTemplate> 。 使用的 `x:Name` <xref:System.Windows.FrameworkElement> 可从获取 <xref:System.Windows.Controls.ControlTemplate> 。

5. 在 <xref:System.Windows.FrameworkElement> `null` 访问其成员之前，请检查是否没有。  如果是 `null` ，则不报告错误。

下面的示例演示控件如何 `NumericUpDown` <xref:System.Windows.FrameworkElement> 根据前面列表中的建议与对象交互。

在定义中的控件的可视结构的示例中 `NumericUpDown` <xref:System.Windows.Controls.ControlTemplate> ， <xref:System.Windows.Controls.Primitives.RepeatButton> 增加了 `Value` 其 `x:Name` 特性设置为的 `UpButton` 。  下面的示例声明一个名为 `UpButtonElement` 的属性，该属性表示 <xref:System.Windows.Controls.Primitives.RepeatButton> 在中声明的 <xref:System.Windows.Controls.ControlTemplate> 。 `set`如果不是，则访问器首先取消订阅按钮的 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件 `UpDownElement` `null` ，然后设置属性，然后订阅该 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件。 还有一个已定义的属性，但在此为另一个属性（ <xref:System.Windows.Controls.Primitives.RepeatButton> 称为） `DownButtonElement` 。

[!code-csharp[VSMCustomControl#UpButtonProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#upbuttonproperty)]
[!code-vb[VSMCustomControl#UpButtonProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#upbuttonproperty)]

下面的示例演示 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> `NumericUpDown` 控件的。  该示例使用 <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> 方法来获取中的 <xref:System.Windows.FrameworkElement> 对象 <xref:System.Windows.Controls.ControlTemplate> 。  请注意，该示例在 <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> 查找 <xref:System.Windows.FrameworkElement> 具有指定名称的的情况下，该名称不是预期类型。 这也是一种最佳做法，是忽略具有指定 `x:Name` 但类型不正确的元素。

[!code-csharp[VSMCustomControl#ApplyTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
[!code-vb[VSMCustomControl#ApplyTemplate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]

按照前面示例中所示的做法，确保当缺少时，控件将继续运行 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.FrameworkElement> 。

### <a name="use-the-visualstatemanager-to-manage-states"></a>使用 VisualStateManager 管理状态

<xref:System.Windows.VisualStateManager>跟踪控件的状态，并执行在状态之间转换所需的逻辑。 向添加 <xref:System.Windows.VisualState> 对象时 <xref:System.Windows.Controls.ControlTemplate> ，请将它们添加到 <xref:System.Windows.VisualStateGroup> 并将添加 <xref:System.Windows.VisualStateGroup> 到 <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> 附加属性，以便能够 <xref:System.Windows.VisualStateManager> 访问这些对象。

下面的示例重复了前面的示例，该示例显示与 <xref:System.Windows.VisualState> 控件的 `Positive` 和状态相对应的对象 `Negative` 。 <xref:System.Windows.Media.Animation.Storyboard>中的会 `Negative` <xref:System.Windows.VisualState> 打开 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 红色的 <xref:System.Windows.Controls.TextBlock> 。   当 `NumericUpDown` 控件处于状态时，将 `Negative` 开始状态下的情节提要 `Negative` 。  <xref:System.Windows.Media.Animation.Storyboard> `Negative` 当控件返回到状态时，处于状态的将停止 `Positive` 。  不 `Positive` <xref:System.Windows.VisualState> 需要包含 <xref:System.Windows.Media.Animation.Storyboard> ，因为当的 <xref:System.Windows.Media.Animation.Storyboard> 停止时 `Negative` ，将 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 返回到其原始颜色。

[!code-xaml[VSMCustomControl#ValueStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]

请注意，将为 <xref:System.Windows.Controls.TextBlock> 指定一个名称，但不 <xref:System.Windows.Controls.TextBlock> 在控制协定中， `NumericUpDown` 因为控件的逻辑从不引用 <xref:System.Windows.Controls.TextBlock> 。  中引用的元素 <xref:System.Windows.Controls.ControlTemplate> 具有名称，但不需要是控件协定的一部分，因为控件的新 <xref:System.Windows.Controls.ControlTemplate> 可能无需引用该元素。  例如，创建新 <xref:System.Windows.Controls.ControlTemplate> 的的 `NumericUpDown` 可能决定不通过更改来指示该为 `Value` 负数 <xref:System.Windows.Controls.Control.Foreground%2A> 。  在这种情况下，代码和都不会 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.TextBlock> 按名称引用。

控件的逻辑负责更改控件的状态。 下面的示例演示当大于 `NumericUpDown` <xref:System.Windows.VisualStateManager.GoToState%2A> 0 时，控件将调用方法进入 `Positive` 状态 `Value` ，并在 `Negative` `Value` 小于0时进入状态。

[!code-csharp[VSMCustomControl#ValueStateChange](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#valuestatechange)]
[!code-vb[VSMCustomControl#ValueStateChange](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#valuestatechange)]

<xref:System.Windows.VisualStateManager.GoToState%2A>方法执行相应的启动和停止演示图板所需的逻辑。 当控件调用 <xref:System.Windows.VisualStateManager.GoToState%2A> 更改其状态时，将 <xref:System.Windows.VisualStateManager> 执行以下操作：

- 如果 <xref:System.Windows.VisualState> 控件将具有，则会 <xref:System.Windows.Media.Animation.Storyboard> 开始使用情节提要。 然后，如果 <xref:System.Windows.VisualState> 控件所来自的具有，则 <xref:System.Windows.Media.Animation.Storyboard> 情节提要将结束。

- 如果控件已经处于指定的状态，则 <xref:System.Windows.VisualStateManager.GoToState%2A> 不会执行任何操作，将返回 `true` 。

- 如果指定的状态在的中不存在 <xref:System.Windows.Controls.ControlTemplate> `control` ，则 <xref:System.Windows.VisualStateManager.GoToState%2A> 不会执行任何操作，将返回 `false` 。

#### <a name="best-practices-for-working-with-the-visualstatemanager"></a>使用 VisualStateManager 的最佳做法

建议您执行以下操作来维护控件的状态：

- 使用属性跟踪其状态。

- 创建用于在状态间转换的帮助器方法。

`NumericUpDown`控件使用其 `Value` 属性来跟踪它是否处于 `Positive` 或 `Negative` 状态。  该 `NumericUpDown` 控件还定义 `Focused` 和 `UnFocused` 状态，以跟踪 <xref:System.Windows.UIElement.IsFocused%2A> 属性。 如果使用的状态并不自然对应于控件的属性，则可以定义一个私有属性来跟踪状态。

更新所有状态的单个方法会将调用集中在一起 <xref:System.Windows.VisualStateManager> ，并使你的代码易于管理。 下面的示例显示 `NumericUpDown` 控件的帮助器方法 `UpdateStates` 。 当 `Value` 大于或等于0时， <xref:System.Windows.Controls.Control> 处于 `Positive` 状态。  当 `Value` 小于0时，控件处于 `Negative` 状态。  当 <xref:System.Windows.UIElement.IsFocused%2A> 为时 `true` ，控件处于 `Focused` 状态; 否则为 `Unfocused` 状态。  `UpdateStates`无论什么状态发生变化，控件都可以在需要更改状态时调用。

[!code-csharp[VSMCustomControl#UpdateStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#updatestates)]
[!code-vb[VSMCustomControl#UpdateStates](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#updatestates)]

如果将状态名称传递到 <xref:System.Windows.VisualStateManager.GoToState%2A> 控件已经处于该状态的时间，则 <xref:System.Windows.VisualStateManager.GoToState%2A> 不会执行任何操作，因此不需要检查控件的当前状态。  例如，如果 `Value` 从一个负数更改为另一个负数，则状态的情节提要 `Negative` 不会中断，用户将看不到控件中的更改。

<xref:System.Windows.VisualStateManager>使用 <xref:System.Windows.VisualStateGroup> 对象确定在调用时要退出的状态 <xref:System.Windows.VisualStateManager.GoToState%2A> 。 对于在其上定义的每个，该控件始终处于一种状态 <xref:System.Windows.VisualStateGroup> <xref:System.Windows.Controls.ControlTemplate> ，并且仅当进入相同的另一状态时才会离开状态 <xref:System.Windows.VisualStateGroup> 。 例如，控件的将 <xref:System.Windows.Controls.ControlTemplate> `NumericUpDown` 定义 `Positive` 一个中的和对象，并定义另一个 `Negative` <xref:System.Windows.VisualState> <xref:System.Windows.VisualStateGroup> `Focused` 中的和 `Unfocused` <xref:System.Windows.VisualState> 对象。  (你可以在 `Focused` `Unfocused` <xref:System.Windows.VisualState> 本主题的 "[完整示例](#complete_example)" 部分中看到和定义，当控件从 `Positive` 状态 `Negative` 转换到状态时，或反之，控件将保留为 `Focused` 或 `Unfocused` 状态。

有三个典型位置，控件的状态可能会发生更改：

- 当应用于时 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Control> 。

- 当属性发生更改时。

- 事件发生时。

下面的示例演示如何 `NumericUpDown` 在这些情况下更新控件的状态。

应在方法中更新控件的状态， <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> 以便在应用时控件显示为正确的状态 <xref:System.Windows.Controls.ControlTemplate> 。 下面的示例 `UpdateStates` 在中调用 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> ，以确保控件处于适当的状态。  例如，假设您创建一个 `NumericUpDown` 控件，然后将其设置 <xref:System.Windows.Controls.Control.Foreground%2A> 为绿色和 `Value` -5。  如果在将应用于 `UpdateStates` 控件时不调用 <xref:System.Windows.Controls.ControlTemplate> ，则 `NumericUpDown` 控件不处于 `Negative` 状态，并且值为绿色而不是红色。  您必须调用 `UpdateStates` 以将控件置于 `Negative` 状态。

[!code-csharp[VSMCustomControl#ApplyTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
[!code-vb[VSMCustomControl#ApplyTemplate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]

当属性更改时，通常需要更新控件的状态。 下面的示例演示了整个 `ValueChangedCallback` 方法。 由于在 `ValueChangedCallback` `Value` 发生更改时调用，因此，方法会调用， `UpdateStates` 以防 `Value` 从正值变为负，反之亦然。 `UpdateStates`如果 `Value` 在这种情况下，它可以调用，而不会更改为正面或负数，因为在这种情况下，控件将不会更改状态。

[!code-csharp[VSMCustomControl#EntireValueChangedCallback](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#entirevaluechangedcallback)]
[!code-vb[VSMCustomControl#EntireValueChangedCallback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#entirevaluechangedcallback)]

可能还需要在发生事件时更新状态。 下面的示例演示对 `NumericUpDown` 的调用， `UpdateStates` <xref:System.Windows.Controls.Control> 以处理 <xref:System.Windows.UIElement.GotFocus> 事件。

[!code-csharp[VSMCustomControl#OnGotFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#ongotfocus)]
[!code-vb[VSMCustomControl#OnGotFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#ongotfocus)]

<xref:System.Windows.VisualStateManager>可帮助你管理控件的状态。 通过使用 <xref:System.Windows.VisualStateManager> ，可以确保控件正确地在状态之间转换。  如果按照此部分中所述的建议使用来使用 <xref:System.Windows.VisualStateManager> ，则控件的代码将保持可读和可维护性。

<a name="providing_the_control_contract"></a>

## <a name="providing-the-control-contract"></a>提供控件协定

提供控件协定，使 <xref:System.Windows.Controls.ControlTemplate> 作者知道要在模板中放置的内容。 控件协定具有三个元素：

- 控件逻辑使用的可视元素。

- 控件状态和每种状态所属的组。

- 以可视方式影响控件的公共属性。

创建新的用户 <xref:System.Windows.Controls.ControlTemplate> 需要知道 <xref:System.Windows.FrameworkElement> 控件的逻辑使用的对象、每个对象的类型以及其名称。 <xref:System.Windows.Controls.ControlTemplate>作者还需要知道控件可处于的状态，以及该状态所处的状态 <xref:System.Windows.VisualStateGroup> 。

返回到 `NumericUpDown` 示例后，控件要求 <xref:System.Windows.Controls.ControlTemplate> 具有以下 <xref:System.Windows.FrameworkElement> 对象：

- 一个 <xref:System.Windows.Controls.Primitives.RepeatButton> 名为的 `UpButton` 。

- 一个 <xref:System.Windows.Controls.Primitives.RepeatButton> 名为 `DownButton.`

 控件可以处于以下状态：

- 在 `ValueStates`<xref:System.Windows.VisualStateGroup>

  - `Positive`

  - `Negative`

- 在 `FocusStates`<xref:System.Windows.VisualStateGroup>

  - `Focused`

  - `Unfocused`

若要指定 <xref:System.Windows.FrameworkElement> 控件需要的对象，请使用 <xref:System.Windows.TemplatePartAttribute> ，它指定预期元素的名称和类型。  若要指定控件的可能状态，请使用，它 <xref:System.Windows.TemplateVisualStateAttribute> 指定状态的名称和所属的名称 <xref:System.Windows.VisualStateGroup> 。  将 <xref:System.Windows.TemplatePartAttribute> 和放置 <xref:System.Windows.TemplateVisualStateAttribute> 在控件的类定义上。

任何影响控件外观的公共属性也属于控件协定。

下面的示例指定 <xref:System.Windows.FrameworkElement> 控件的对象和状态 `NumericUpDown` 。

[!code-csharp[VSMCustomControl#ControlContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controlcontract)]
[!code-vb[VSMCustomControl#ControlContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controlcontract)]

<a name="complete_example"></a>

## <a name="complete-example"></a>完整的示例

下面的示例是控件的整个 <xref:System.Windows.Controls.ControlTemplate> `NumericUpDown` 。

[!code-xaml[VSMCustomControl#NUDTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/themes/generic.xaml#nudtemplate)]

下面的示例演示了的逻辑 `NumericUpDown` 。

[!code-csharp[VSMCustomControl#ControlLogic](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controllogic)]
[!code-vb[VSMCustomControl#ControlLogic](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controllogic)]

## <a name="see-also"></a>请参阅

- [创建控件模板](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
- [控件自定义](control-customization.md)
