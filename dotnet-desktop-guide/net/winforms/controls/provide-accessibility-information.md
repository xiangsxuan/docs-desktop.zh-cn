---
title: 为 Windows 窗体上的控件提供辅助功能信息
description: 了解如何向控件添加辅助功能信息。 通过 Windows 窗体，可以向控件添加辅助功能设置，为残疾人士提供帮助。
ms.date: 10/26/2020
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
dev_langs:
- csharp
- vb
ms.openlocfilehash: 27c06a7d01cb98ecb2f7216c09dc292d2fe68a6f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941990"
---
# <a name="providing-accessibility-information-for-controls-windows-forms-net"></a>为控件提供辅助功能信息（Windows 窗体 .NET）

辅助工具是专用的程序和设备，用于帮助残障人士更加有效地使用计算机。 示例包括适用于盲人的屏幕阅读器，还有声音输入实用功能，方便人们发出声音命令，而不使用鼠标或键盘。 这些辅助工具与由 Windows 窗体控件公开的辅助功能属性相交互。 这些属性为：

- <xref:System.Windows.Forms.AccessibleObject?displayProperty=fullName>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription?displayProperty=fullName>
- <xref:System.Windows.Forms.Control.AccessibleDescription?displayProperty=fullName>
- <xref:System.Windows.Forms.Control.AccessibleName?displayProperty=fullName>
- <xref:System.Windows.Forms.AccessibleRole?displayProperty=fullName>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="accessibilityobject-property"></a>AccessibilityObject 属性

此只读属性包含 <xref:System.Windows.Forms.AccessibleObject> 实例。 `AccessibleObject` 实现了 <xref:Accessibility.IAccessible> 接口，它提供了有关控件的说明、屏幕位置、导航功能和值的信息。 在将控件添加到窗体时，设计器会设置此值。

## <a name="accessibledefaultactiondescription-property"></a>AccessibleDefaultActionDescription 属性

该字符串描述控件的操作。 它不显示在“属性”窗口中，可能只在代码中被设置。 下面的示例为按钮控件设置 <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription> 属性：

```vb
Button1.AccessibleDefaultActionDescription = "Closes the application."
```

```csharp
button1.AccessibleDefaultActionDescription = "Closes the application.";
```

## <a name="accessibledescription-property"></a>AccessibleDescription 属性

该字符串描述控件。 <xref:System.Windows.Forms.Control.AccessibleDescription> 属性可能在“属性”窗口或代码中被设置，如下所示：

```vb
Button1.AccessibleDescription = "A button with text 'Exit'."
```

```csharp
button1.AccessibleDescription = "A button with text 'Exit'";
```

## <a name="accessiblename-property"></a>AccessibleName 属性

这是报告给辅助工具的控件名称。 <xref:System.Windows.Forms.Control.AccessibleName> 属性可能在“属性”窗口或代码中被设置，如下所示：

```vb
Button1.AccessibleName = "Order"
```

```csharp
button1.AccessibleName = "Order";
```

## <a name="accessiblerole-property"></a>AccessibleRole 属性

此属性描述控件的用户接口角色，其中包含 <xref:System.Windows.Forms.AccessibleRole> 枚举。 新控件的值设置为 `Default`。 这意味着默认情况下，`Button` 控件充当 `Button`。 如果控件具有另一个角色，你可能希望重置此属性。 例如，你可能正将 `PictureBox` 控件用作 `Chart`，并且可能希望辅助工具将角色报告为 `Chart`，而非 `PictureBox`。 你可能还希望为已开发的自定义控件指定此属性。 此属性可能在“属性”窗口或代码中被设置，如下所示：

```vb
PictureBox1.AccessibleRole = AccessibleRole.Chart
```

```csharp
pictureBox1.AccessibleRole = AccessibleRole.Chart;
```

## <a name="see-also"></a>另请参阅

- [Label 控件概述（Windows 窗体 .NET）](labels.md)
- <xref:System.Windows.Forms.AccessibleObject>
- <xref:System.Windows.Forms.Control.AccessibilityObject?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDescription?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleName?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleRole?displayProperty=nameWithType>
- <xref:System.Windows.Forms.AccessibleRole>
