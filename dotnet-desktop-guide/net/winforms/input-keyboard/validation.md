---
title: 用户输入验证
description: 了解使用 Windows 窗体验证应用程序中的用户输入的多种方法。
ms.date: 10/26/2020
ms.topic: overview
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.openlocfilehash: 16db8a1048c5f342f942f88a91a764d6b2a57f35
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941905"
---
# <a name="overview-of-how-to-validate-user-input-windows-forms-net"></a>如何验证用户输入（Windows 窗体 .NET）概述

用户在应用程序中输入数据后，建议在应用程序使用数据之前验证数据是否有效。 可以要求某些文本字段的长度不能为零，字段应设置为电话号码格式，或者字符串中不得包含无效字符。 Windows 窗体提供了多种方式来验证应用程序中的输入。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="maskedtextbox-control"></a>MaskedTextBox 控件

如果需要用户以明确定义的格式输入数据，例如电话号码或零件编号，则可以使用 <xref:System.Windows.Forms.MaskedTextBox> 控件以最少的代码快速实现此目的。 掩码是由掩码语言中的字符组成的字符串，用于指定可在文本框中的任何特定位置输入的字符。 控件向用户显示一组提示。 如果用户键入错误条目（例如，用户在需要输入数字时键入字母），则控件将自动拒绝输入。

<xref:System.Windows.Forms.MaskedTextBox> 使用的掩码语言是灵活的。 它允许指定必填字符、可选字符、文本字符（例如连字符和括号）、货币字符和日期分隔符。 控件绑定到数据源时也可以正常工作。 可使用数据绑定上的 <xref:System.Windows.Forms.Binding.Format> 事件重新格式化输入数据以符合掩码，可使用 <xref:System.Windows.Forms.Binding.Parse> 事件重新格式化输出数据以符合数据字段的规范。

<!-- TODO
For more information, see [MaskedTextBox Control](./controls/maskedtextbox-control-windows-forms.md).-->

## <a name="event-driven-validation"></a>事件驱动的验证

如果要获得对验证的完全编程控制，或者需要复杂的验证检查，则应使用大多数 Windows 窗体控件中内置的验证事件。 每个接受自由格式用户输入的控件都有 <xref:System.Windows.Forms.Control.Validating> 事件，并且控件需要数据验证时会发生该事件。 在 <xref:System.Windows.Forms.Control.Validating> 事件处理方法中，可以通过多种方式验证用户输入。 例如，如果文本框必须包含邮政编码，则可以通过以下方式进行验证：

- 如果邮政编码必须属于特定的邮政编码组，则可以对输入进行字符串比较，以验证用户输入的数据。 例如，如果邮政编码必须属于集合 `{10001, 10002, 10003}`，则可以进行字符串比较来验证数据。

- 如果邮政编码必须采用特定格式，则可以使用正则表达式来验证用户输入的数据。 例如，若要验证格式 `#####` 或 `#####-####`，可以使用正则表达式 `^(\d{5})(-\d{4})?$`。 若要验证格式 `A#A #A#`，可以使用正则表达式 `[A-Z]\d[A-Z] \d[A-Z]\d`。 有关正则表达式的详细信息，请参阅 [.NET 正则表达式](/dotnet/standard/base-types/regular-expressions)和[正则表达式示例](/dotnet/standard/base-types/regular-expression-example-scanning-for-hrefs)。

- 如果邮政编码必须是有效的美国邮政编码，则可以调用邮政编码 Web 服务来验证用户输入的数据。

<xref:System.Windows.Forms.Control.Validating> 事件由类型为 <xref:System.ComponentModel.CancelEventArgs> 的对象提供。 如果确定控件的数据无效，可将此对象的 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 属性设置为 `true`，以取消 <xref:System.Windows.Forms.Control.Validating> 事件。 如果未设置 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 属性，则 Windows 窗体将假定针对该控件的验证成功，并引发 <xref:System.Windows.Forms.Control.Validated> 事件。

有关对 <xref:System.Windows.Controls.TextBox> 中的电子邮件地址进行验证的代码示例，请参阅 <xref:System.Windows.Forms.Control.Validating> 事件参考。

### <a name="event-driven-validation-data-bound-controls"></a>事件驱动的验证数据绑定控件

将控件绑定到数据源（例如数据库表）时，验证很有用。 通过使用验证，可确保控件的数据符合数据源所需的格式，并可确保其不包含任何不安全的特殊字符，例如引号和反斜杠。

使用数据绑定时，控件中的数据会在 <xref:System.Windows.Forms.Control.Validating> 事件执行期间与数据源同步。 如果取消 <xref:System.Windows.Forms.Control.Validating> 事件，则数据不会与数据源同步。

> [!IMPORTANT]
> 如果在 <xref:System.Windows.Forms.Control.Validating> 事件之后进行自定义验证，不会影响数据绑定。 例如，如果使用 <xref:System.Windows.Forms.Control.Validated> 事件中的代码尝试取消数据绑定，仍将发生数据绑定。 在这种情况下，若要在 <xref:System.Windows.Forms.Control.Validated> 事件中执行验证，请将控件的 [`Binding.DataSourceUpdateMode`](xref:System.Windows.Forms.Binding.DataSourceUpdateMode) 属性从 <xref:System.Windows.Forms.DataSourceUpdateMode.OnValidation?displayProperty=nameWithType> 更改为 <xref:System.Windows.Forms.DataSourceUpdateMode.Never?displayProperty=nameWithType>，然后将 `your-control.DataBindings["field-name"].WriteValue()` 添加到验证代码。

## <a name="implicit-and-explicit-validation"></a>隐式和显式验证

何时验证控件的数据？ 具体取决于开发人员。 可以根据应用程序的需要使用隐式或显式验证。

### <a name="implicit-validation"></a>隐式验证

隐式验证方法在用户输入数据时对其进行验证。 通过在按键被按下时读取按键来验证数据，更常见的是，在用户将输入焦点从控件移开时验证数据。 如果希望在用户工作时为其提供有关数据的即时反馈，则此方法很有用。

如果要对控件使用隐式验证，则必须将该控件的 <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> 属性设置为 <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange> 或 <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>。 如果取消 <xref:System.Windows.Forms.Control.Validating> 事件，则控件的行为将由分配给 <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> 的值决定。 如果分配了 <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>，则取消事件不会导致发生 <xref:System.Windows.Forms.Control.Validated> 事件。 输入焦点将保留在当前控件上，直到用户将数据更改为有效格式。 如果分配了 <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>，则取消事件时不会发生 <xref:System.Windows.Forms.Control.Validated> 事件，但焦点仍将更改为下一个控件。

将 <xref:System.Windows.Forms.AutoValidate.Disable> 分配给 <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> 属性可完全防止隐式验证。 若要验证控件，必须使用显式验证。

### <a name="explicit-validation"></a>显式验证

显式验证方法可同时验证数据。 可以验证数据，以响应用户操作，例如单击“保存”按钮或“下一步”链接 。 发生用户操作时，可以通过以下方式之一触发显式验证：

- 调用 <xref:System.Windows.Forms.ContainerControl.Validate%2A> 以验证最后一个控件是否失去焦点。
- 调用 <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> 以验证窗体或容器控件中的所有子级控件。
- 调用自定义方法，以手动验证控件中的数据。

### <a name="default-implicit-validation-behavior-for-controls"></a>控件的默认隐式验证行为

不同的 Windows 窗体控件的 <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> 属性具有不同的默认值。 下表显示了最常见的控件及其默认值。

| 控制                                        | 默认验证行为                                     |
|------------------------------------------------|-----------------------------------------------------------------|
| <xref:System.Windows.Forms.ContainerControl>   | <xref:System.Windows.Forms.AutoValidate.Inherit>                |
| <xref:System.Windows.Forms.Form>               | <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange> |
| <xref:System.Windows.Forms.PropertyGrid>       | Visual Studio 中未公开的属性                           |
| <xref:System.Windows.Forms.ToolStripContainer> | Visual Studio 中未公开的属性                           |
| <xref:System.Windows.Forms.SplitContainer>     | <xref:System.Windows.Forms.AutoValidate.Inherit>                |
| <xref:System.Windows.Forms.UserControl>        | <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange> |

## <a name="closing-the-form-and-overriding-validation"></a>关闭窗体和重写验证

控件保持焦点时，由于其所包含的数据无效，因此无法通过以下常用方法之一关闭父级窗体：

- 单击“关闭”按钮。
- 选择“系统” > “关闭”菜单 。
- 以编程方式调用 <xref:System.Windows.Forms.Form.Close%2A> 方法。

但在某些情况下，无论控件中的值是否有效，均建议让用户关闭窗体。 可以通过为窗体的 <xref:System.Windows.Forms.Form.FormClosing> 事件创建处理程序来重写验证并关闭仍包含无效数据的窗体。 在事件中，将 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 属性设置为 `false`。 这将强制关闭窗体。 有关详细信息及示例，请参阅<xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>。

> [!NOTE]
> 如果以这种方式强制关闭窗体，则会丢失窗体控件中尚未保存的所有数据。 此外，模式窗体在关闭时不会验证控件的内容。 你仍可以使用控件验证将焦点锁定在控件上，但不必担心与关闭窗体相关的行为。

## <a name="see-also"></a>另请参阅

- [使用键盘事件（Windows 窗体 .NET）](events.md)
- <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>
- <xref:System.Windows.Forms.FormClosingEventArgs?displayProperty=nameWithType>
