---
title: 如何模拟鼠标事件
description: 了解如何模拟适用于 .NET 的 Windows 窗体中的鼠标事件。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse [Windows Forms], event simulation
- user input [Windows Forms], simulating
- SendKeys [Windows Forms], using
ms.openlocfilehash: 443611163d33a266b3c49d03df13131c994b0bd3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941971"
---
# <a name="how-to-simulate-mouse-events-windows-forms-net"></a>如何模拟鼠标事件（Windows 窗体 .NET）

在 Windows 窗体中模拟鼠标事件不像模拟键盘事件那样直接。 Windows 窗体不提供帮助程序类来移动鼠标和调用鼠标单击操作。 控制鼠标的唯一方式是使用本机 Windows 方法。 如果你使用的是自定义控件或窗体，可模拟鼠标事件，但不能直接控制鼠标。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="events"></a>事件

大多数事件都具有调用这些事件的相应方法，以 `On` 后跟 `EventName` 的模式命名，如 `OnMouseMove`。 这种方式只适用于自定义控件或窗体内，因为这些方法受到保护且不能从控件或窗体的上下文外访问。 使用方法（如 `OnMouseMove`）的缺点在于，它不会实际控制鼠标或与控件交互，而只是引发关联的事件。 例如，如果你想模拟将鼠标悬停在 <xref:System.Windows.Forms.ListBox> 中的某一项上，则 `OnMouseMove` 和 `ListBox` 不会以光标下的突出显示的项的方式直观地作出反应。

这些受保护的方法可用于模拟鼠标事件。

- `OnMouseDown`
- `OnMouseEnter`
- `OnMouseHover`
- `OnMouseLeave`
- `OnMouseMove`
- `OnMouseUp`
- `OnMouseWheel`
- `OnMouseClick`
- `OnMouseDoubleClick`

有关这些事件的详细信息，请参阅[使用鼠标事件（Windows 窗体 .NET）](events.md)

## <a name="invoke-a-click"></a>调用单击

考虑到大多数控件在单击时会执行某些操作（如调用用户代码的按钮或更改其选中状态的复选框），Windows 窗体提供一种简单的方法来触发单击操作。 某些控件（如组合框）在单击时不会执行任何特殊操作，并且模拟单击不会对控件产生任何影响。

### <a name="performclick"></a>PerformClick

<xref:System.Windows.Forms.IButtonControl?displayProperty=nameWithType> 接口提供模拟单击控件的 <xref:System.Windows.Forms.IButtonControl.PerformClick%2A> 方法。 <xref:System.Windows.Forms.Button?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.LinkLabel?displayProperty=nameWithType> 控件都实现此接口。

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form1.cs" id="PerformClick":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form1.vb" id="PerformClick":::

### <a name="invokeclick"></a>InvokeClick

对于窗体的自定义控件，使用 <xref:System.Windows.Forms.Control.InvokeOnClick%2A> 方法模拟鼠标单击。 这是一个受保护的方法，只能从窗体或派生的自定义控件中调用。

例如，以下代码从 `button1` 单击复选框。

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form1.cs" id="ClickCheckbox":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form1.vb" id="ClickCheckbox":::

## <a name="use-native-windows-methods"></a>使用本机 Windows 方法

Windows 提供了一些方法，你可调用这些方法来模拟鼠标移动和单击，如 [`User32.dll SendInput`](/windows/win32/api/winuser/nf-winuser-sendinput) 和 [`User32.dll SetCursorPos`](/windows/win32/api/winuser/nf-winuser-setcursorpos)。 下面的示例将鼠标光标移动到控件的中心：

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form2.cs" id="MoveCursor":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form2.vb" id="MoveCursor":::

## <a name="see-also"></a>另请参阅

- [使用鼠标的概述（Windows 窗体 .NET）](overview.md)
- [使用鼠标事件（Windows 窗体 .NET）](events.md)
- [如何区分单击和双击（Windows 窗体 .NET）](how-to-distinguish-between-clicks-and-double-clicks.md)
- [管理鼠标指针（Windows 窗体 .NET）](how-to-manage-cursor-pointer.md)
