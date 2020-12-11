---
title: 为 Windows 窗体上的控件提供辅助功能信息
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 887dee6f-5059-4d57-957d-7c6fcd4acb10
ms.openlocfilehash: 672104db94826cfbe113a7ae0ea29546b0c3b9da
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970293"
---
# <a name="providing-accessibility-information-for-controls-on-a-windows-form"></a>为 Windows 窗体上的控件提供辅助功能信息
辅助工具是专用的程序和设备，用于帮助残障人士更加有效地使用计算机。 示例包括适用于盲人的屏幕阅读器，还有声音输入实用功能，方便人们发出声音命令，而不使用鼠标或键盘。 这些辅助工具与由 Windows 窗体控件公开的辅助功能属性相交互。 这些属性为：  
  
- **AccessibilityObject**  
  
- **AccessibleDefaultActionDescription**  
  
- **AccessibleDescription**  
  
- **AccessibleName**  
  
- **AccessibleRole**  
  
## <a name="accessibilityobject-property"></a>AccessibilityObject 属性  
 此只读属性包含 <xref:System.Windows.Forms.AccessibleObject> 实例。 **AccessibleObject** 实现了 <xref:Accessibility.IAccessible> 接口，它提供了有关控件的说明、屏幕位置、导航功能和值的信息。 在将控件添加到窗体时，设计器会设置此值。  
  
## <a name="accessibledefaultactiondescription-property"></a>AccessibleDefaultActionDescription 属性  
 该字符串描述控件的操作。 它不显示在“属性”窗口中，可能只在代码中被设置。 下面的示例为按钮控件设置此属性：  
  
```vb  
Button1.AccessibleDefaultActionDescription = _  
   "Closes the application."  
```

```csharp  
Button1.AccessibleDefaultActionDescription =
   "Closes the application.";  
```

```cpp  
button1->AccessibleDefaultActionDescription =  
   "Closes the application.";  
```  
  
## <a name="accessibledescription-property"></a>AccessibleDescription 属性  
 该字符串描述控件。 它可能在“属性”窗口或代码中被设置，如下所示：  
  
```vb  
Button1.AccessibleDescription = "A button with text 'Exit'."  
```

```csharp  
Button1.AccessibleDescription = "A button with text 'Exit'";  
```

```cpp  
button1->AccessibleDescription = "A button with text 'Exit'";  
```  
  
## <a name="accessiblename-property"></a>AccessibleName 属性  
 这是报告给辅助工具的控件名称。 它可能在“属性”窗口或代码中被设置，如下所示：  
  
```vb  
Button1.AccessibleName = "Order"  
```

```csharp  
Button1.AccessibleName = "Order";  
```

```cpp  
button1->AccessibleName = "Order";  
```  
  
## <a name="accessiblerole-property"></a>AccessibleRole 属性  
 此属性描述控件的用户接口角色，其中包含 <xref:System.Windows.Forms.AccessibleRole> 枚举。 新控件的值设置为 `Default`。 这就意味着默认情况下， **Button** 控件充当 **按钮**。 如果控件具有另一个角色，你可能希望重置此属性。 例如，你可能正将 **PictureBox** 控件用作“图表” ，并且可能希望辅助工具将角色报告为“图表” ，而非 **PictureBox**。 你可能还希望为已开发的自定义控件指定此属性。 此属性可能在“属性”窗口或代码中被设置，如下所示：  
  
```vb
PictureBox1.AccessibleRole = AccessibleRole.Chart  
```

```csharp  
PictureBox1.AccessibleRole = AccessibleRole.Chart;  
```

```cpp  
pictureBox1->AccessibleRole = AccessibleRole::Chart;  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.AccessibleObject>
- <xref:System.Windows.Forms.Control.AccessibilityObject%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleName%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleRole%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.AccessibleRole>
