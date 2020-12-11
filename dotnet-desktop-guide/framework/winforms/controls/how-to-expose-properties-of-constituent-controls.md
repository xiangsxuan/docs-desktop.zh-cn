---
title: 如何：公开构成控件的属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], exposing constituent controls
- controls [Windows Forms], constituent
- custom controls [Windows Forms], exposing properties
- constituent controls
ms.assetid: 5c1ec98b-aa48-4823-986e-4712551cfdf1
ms.openlocfilehash: f006e42771a5ecc71f6a508fd78d0e2dd8f2d2f2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971176"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a>如何：公开构成控件的属性
构成复合控件的控件称为 *构成控件*。 这些控件通常声明为私有，因此开发人员无法访问这些控件。 如果要使这些控件的属性可供未来用户使用，则必须将这些控件公开给用户。 通过在用户控件中创建一个属性，并使用 `get` `set` 该属性的和访问器来影响构成控件的 private 属性中的更改，可以公开构成控件的属性。

 假设有一个名为的 "构成" 按钮的假设用户控件 `MyButton` 。 在此示例中，当用户请求 `ConstituentButtonBackColor` 属性时，将传递在的属性中存储的值 <xref:System.Windows.Forms.Control.BackColor%2A> `MyButton` 。 当用户将值分配给此属性时，该值将自动传递到的 <xref:System.Windows.Forms.Control.BackColor%2A> 属性， `MyButton` 并 `set` 将执行代码，从而更改的颜色 `MyButton` 。

 下面的示例演示如何公开 <xref:System.Windows.Forms.Control.BackColor%2A> "构成" 按钮的属性：

```vb
Public Property ButtonColor() as System.Drawing.Color
   Get
      Return MyButton.BackColor
   End Get
   Set(Value as System.Drawing.Color)
      MyButton.BackColor = Value
   End Set
End Property
```

```csharp
public Color ButtonColor
{
   get
   {
      return(myButton.BackColor);
   }
   set
   {
      myButton.BackColor = value;
   }
}
```

### <a name="to-expose-a-property-of-a-constituent-control"></a>公开构成控件的属性

1. 为用户控件创建公共属性。

2. 在 `get` 属性的部分，编写用于检索要公开的属性的值的代码。

3. 在 `set` 属性的部分，编写将属性的值传递给构成控件的公开属性的代码。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.UserControl>
- [Windows 窗体控件中的属性](properties-in-windows-forms-controls.md)
- [各种自定义控件](varieties-of-custom-controls.md)
