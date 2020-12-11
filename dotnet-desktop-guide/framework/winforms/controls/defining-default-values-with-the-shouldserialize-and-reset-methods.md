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
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a><span data-ttu-id="73fb2-103">使用 ShouldSerialize 和 Reset 方法定义默认值</span><span class="sxs-lookup"><span data-stu-id="73fb2-103">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>
<span data-ttu-id="73fb2-104">`ShouldSerialize` 和 `Reset` 是可为属性提供的可选方法（如果该属性没有简单的默认值）。</span><span class="sxs-lookup"><span data-stu-id="73fb2-104">`ShouldSerialize` and `Reset` are optional methods that you can provide for a property, if the property does not have a simple default value.</span></span> <span data-ttu-id="73fb2-105">如果属性具有简单的默认值，则应应用 <xref:System.ComponentModel.DefaultValueAttribute> ，并改为向特性类构造函数提供默认值。</span><span class="sxs-lookup"><span data-stu-id="73fb2-105">If the property has a simple default value, you should apply the <xref:System.ComponentModel.DefaultValueAttribute> and supply the default value to the attribute class constructor instead.</span></span> <span data-ttu-id="73fb2-106">其中任何一个机制都会在设计器中启用以下功能：</span><span class="sxs-lookup"><span data-stu-id="73fb2-106">Either of these mechanisms enables the following features in the designer:</span></span>

- <span data-ttu-id="73fb2-107">如果属性已从其默认值中修改，则属性在属性浏览器中提供可视指示。</span><span class="sxs-lookup"><span data-stu-id="73fb2-107">The property provides visual indication in the property browser if it has been modified from its default value.</span></span>

- <span data-ttu-id="73fb2-108">用户可以右键单击属性，然后选择 " **重置** " 将属性还原为其默认值。</span><span class="sxs-lookup"><span data-stu-id="73fb2-108">The user can right-click on the property and choose **Reset** to restore the property to its default value.</span></span>

- <span data-ttu-id="73fb2-109">设计器生成更高效的代码。</span><span class="sxs-lookup"><span data-stu-id="73fb2-109">The designer generates more efficient code.</span></span>

> [!NOTE]
> <span data-ttu-id="73fb2-110">应用 <xref:System.ComponentModel.DefaultValueAttribute> 或提供 `Reset` *propertyname* 和 `ShouldSerialize` *propertyname* 方法。</span><span class="sxs-lookup"><span data-stu-id="73fb2-110">Either apply the <xref:System.ComponentModel.DefaultValueAttribute> or provide `Reset`*PropertyName* and `ShouldSerialize`*PropertyName* methods.</span></span> <span data-ttu-id="73fb2-111">请勿同时使用这两种方法。</span><span class="sxs-lookup"><span data-stu-id="73fb2-111">Do not use both.</span></span>

<span data-ttu-id="73fb2-112">声明 `ShouldSerialize` 或方法时 `Reset` ，请使用 `private` 访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="73fb2-112">When declaring a `ShouldSerialize` or `Reset` method, use the `private` access modifier.</span></span> <span data-ttu-id="73fb2-113">这些方法通常由设计器调用，而不是由用户代码调用。</span><span class="sxs-lookup"><span data-stu-id="73fb2-113">These methods are usually invoked by the designer and not by user code.</span></span>

 <span data-ttu-id="73fb2-114">`Reset` *PropertyName* 方法将属性设置为其默认值，如下面的代码段所示。</span><span class="sxs-lookup"><span data-stu-id="73fb2-114">The `Reset`*PropertyName* method sets a property to its default value, as shown in the following code fragment.</span></span>

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
> <span data-ttu-id="73fb2-115">如果属性没有 `Reset` 方法，则不会标记为 <xref:System.ComponentModel.DefaultValueAttribute> ，并且在其声明中未提供默认值，则在 Visual Studio 中的 Windows 窗体设计器的 " `Reset` **属性** " 窗口的快捷菜单中禁用该属性的选项。</span><span class="sxs-lookup"><span data-stu-id="73fb2-115">If a property does not have a `Reset` method, is not marked with a <xref:System.ComponentModel.DefaultValueAttribute>, and does not have a default value supplied in its declaration, the `Reset` option for that property is disabled in the shortcut menu of the **Properties** window of the Windows Forms Designer in Visual Studio.</span></span>

 <span data-ttu-id="73fb2-116">Visual Studio 等设计器使用 `ShouldSerialize` *PropertyName* 方法来检查属性是否已从其默认值更改并仅在属性发生更改时将代码写入窗体中，从而允许更高效地生成代码。</span><span class="sxs-lookup"><span data-stu-id="73fb2-116">Designers such as Visual Studio use the `ShouldSerialize`*PropertyName* method to check whether a property has changed from its default value and write code into the form only if a property is changed, thus allowing for more efficient code generation.</span></span> <span data-ttu-id="73fb2-117">例如：</span><span class="sxs-lookup"><span data-stu-id="73fb2-117">For example:</span></span>

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
> <span data-ttu-id="73fb2-118">如果要永久禁止设计器对某个属性进行序列化，请添加值为的 [designerserializationvisibility.content](xref:System.ComponentModel.DesignerSerializationVisibilityAttribute) 特性 `Hidden` 。</span><span class="sxs-lookup"><span data-stu-id="73fb2-118">If you want to permanently prevent a property from being serialized by the designer, add the [DesignerSerializationVisibility](xref:System.ComponentModel.DesignerSerializationVisibilityAttribute) attribute with the value of `Hidden`.</span></span>

 <span data-ttu-id="73fb2-119">下面是完整的代码示例。</span><span class="sxs-lookup"><span data-stu-id="73fb2-119">A complete code example follows.</span></span>

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

 <span data-ttu-id="73fb2-120">在这种情况下，即使属性访问的私有变量的值 `MyFont` 为，也 `null` 不会显示属性浏览器 `null` ; 而是显示 <xref:System.Windows.Forms.Control.Font%2A> 父级的属性（如果未 `null` 指定）或 <xref:System.Windows.Forms.Control.Font%2A> 中定义的默认值 <xref:System.Windows.Forms.Control> 。</span><span class="sxs-lookup"><span data-stu-id="73fb2-120">In this case, even when the value of the private variable accessed by the `MyFont` property is `null`, the property browser does not display `null`; instead, it displays the <xref:System.Windows.Forms.Control.Font%2A> property of the parent, if it is not `null`, or the default <xref:System.Windows.Forms.Control.Font%2A> value defined in <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="73fb2-121">因此，的默认值 `MyFont` 不能简单地设置，并且 <xref:System.ComponentModel.DefaultValueAttribute> 不能应用于此属性。</span><span class="sxs-lookup"><span data-stu-id="73fb2-121">Thus the default value for `MyFont` cannot be simply set, and a <xref:System.ComponentModel.DefaultValueAttribute> cannot be applied to this property.</span></span> <span data-ttu-id="73fb2-122">相反， `ShouldSerialize` `Reset` 必须为属性实现和方法 `MyFont` 。</span><span class="sxs-lookup"><span data-stu-id="73fb2-122">Instead, the `ShouldSerialize` and `Reset` methods must be implemented for the `MyFont` property.</span></span>

## <a name="see-also"></a><span data-ttu-id="73fb2-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73fb2-123">See also</span></span>

- [<span data-ttu-id="73fb2-124">Windows 窗体控件中的属性</span><span class="sxs-lookup"><span data-stu-id="73fb2-124">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="73fb2-125">定义属性</span><span class="sxs-lookup"><span data-stu-id="73fb2-125">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)
- [<span data-ttu-id="73fb2-126">属性更改事件</span><span class="sxs-lookup"><span data-stu-id="73fb2-126">Property-Changed Events</span></span>](property-changed-events.md)
- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute?displayProperty=fullName>
