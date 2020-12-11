---
title: 使用 ShouldSerialize 和 Reset 方法定义默认值
description: 了解如何使用 ShouldSerialize 和 Reset 属性方法控制 Windows 窗体设计器的行为。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property methods
- ShouldPersist method
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
ms.openlocfilehash: b425b301a1c07030ad4cefa70e41198d08598631
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970097"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a>使用 ShouldSerialize 和 Reset 方法定义默认值
`ShouldSerialize` 和 `Reset` 是可为属性提供的可选方法（如果该属性没有简单的默认值）。 如果属性具有简单的默认值，则应应用 <xref:System.ComponentModel.DefaultValueAttribute> ，并改为向特性类构造函数提供默认值。 其中任何一个机制都会在设计器中启用以下功能：

- 如果属性已从其默认值中修改，则属性在属性浏览器中提供可视指示。

- 用户可以右键单击属性，然后选择 " **重置** " 将属性还原为其默认值。

- 设计器生成更高效的代码。

> [!NOTE]
> 应用 <xref:System.ComponentModel.DefaultValueAttribute> 或提供 `Reset` *propertyname* 和 `ShouldSerialize` *propertyname* 方法。 请勿同时使用这两种方法。

声明 `ShouldSerialize` 或方法时 `Reset` ，请使用 `private` 访问修饰符。 这些方法通常由设计器调用，而不是由用户代码调用。

 `Reset` *PropertyName* 方法将属性设置为其默认值，如下面的代码段所示。

```vb
Private Sub ResetMyFont()
   MyFont = Nothing
End Sub
```

```csharp
private void ResetMyFont()
{
   MyFont = null;
}
```

> [!NOTE]
> 如果属性没有 `Reset` 方法，则不会标记为 <xref:System.ComponentModel.DefaultValueAttribute> ，并且在其声明中未提供默认值，则在 Visual Studio 中的 Windows 窗体设计器的 " `Reset` **属性** " 窗口的快捷菜单中禁用该属性的选项。

 Visual Studio 等设计器使用 `ShouldSerialize` *PropertyName* 方法来检查属性是否已从其默认值更改并仅在属性发生更改时将代码写入窗体中，从而允许更高效地生成代码。 例如：

```vb
'Returns true if the font has changed; otherwise, returns false.
' The designer writes code to the form only if true is returned.
Private Function ShouldSerializeMyFont() As Boolean
   Return thefont IsNot Nothing
End Function
```

```csharp
// Returns true if the font has changed; otherwise, returns false.
// The designer writes code to the form only if true is returned.
private bool ShouldSerializeMyFont()
{
   return thefont != null;
}
```

> [!TIP]
> 如果要永久禁止设计器对某个属性进行序列化，请添加值为的 [designerserializationvisibility.content](xref:System.ComponentModel.DesignerSerializationVisibilityAttribute) 特性 `Hidden` 。

 下面是完整的代码示例。

```vb
Option Explicit
Option Strict

Imports System.Drawing
Imports System.Windows.Forms

Public Class MyControl
   Inherits Control

   ' Declare an instance of the Font class
   ' and set its default value to Nothing.
   Private thefont As Font = Nothing

   ' The MyFont property.
   Public Property MyFont() As Font
      ' Note that the Font property never
      ' returns null.
      Get
         If Not (thefont Is Nothing) Then
            Return thefont
         End If
         If Not (Parent Is Nothing) Then
            Return Parent.Font
         End If
         Return Control.DefaultFont
      End Get
      Set
         thefont = value
      End Set
   End Property

   Private Function ShouldSerializeMyFont() As Boolean
      Return thefont IsNot Nothing
   End Function

   Private Sub ResetMyFont()
      MyFont = Nothing
   End Sub
End Class
```

```csharp
using System;
using System.Drawing;
using System.Windows.Forms;

public class MyControl : Control {
   // Declare an instance of the Font class
   // and set its default value to null.
   private Font thefont = null;

   // The MyFont property.
   public Font MyFont {
      // Note that the MyFont property never
      // returns null.
      get {
         if (thefont != null) return thefont;
         if (Parent != null) return Parent.Font;
         return Control.DefaultFont;
      }
      set {
         thefont = value;
      }
   }

   private bool ShouldSerializeMyFont()
   {
      return thefont != null;
   }

   private void ResetMyFont()
   {
      MyFont = null;
   }
}
```

 在这种情况下，即使属性访问的私有变量的值 `MyFont` 为，也 `null` 不会显示属性浏览器 `null` ; 而是显示 <xref:System.Windows.Forms.Control.Font%2A> 父级的属性（如果未 `null` 指定）或 <xref:System.Windows.Forms.Control.Font%2A> 中定义的默认值 <xref:System.Windows.Forms.Control> 。 因此，的默认值 `MyFont` 不能简单地设置，并且 <xref:System.ComponentModel.DefaultValueAttribute> 不能应用于此属性。 相反， `ShouldSerialize` `Reset` 必须为属性实现和方法 `MyFont` 。

## <a name="see-also"></a>另请参阅

- [Windows 窗体控件中的属性](properties-in-windows-forms-controls.md)
- [定义属性](defining-a-property-in-windows-forms-controls.md)
- [属性更改事件](property-changed-events.md)
- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute?displayProperty=fullName>
