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
# <a name="how-to-expose-properties-of-constituent-controls"></a><span data-ttu-id="a5d56-102">如何：公开构成控件的属性</span><span class="sxs-lookup"><span data-stu-id="a5d56-102">How to: Expose Properties of Constituent Controls</span></span>
<span data-ttu-id="a5d56-103">构成复合控件的控件称为 *构成控件*。</span><span class="sxs-lookup"><span data-stu-id="a5d56-103">The controls that make up a composite control are called *constituent controls*.</span></span> <span data-ttu-id="a5d56-104">这些控件通常声明为私有，因此开发人员无法访问这些控件。</span><span class="sxs-lookup"><span data-stu-id="a5d56-104">These controls are normally declared private, and thus cannot be accessed by the developer.</span></span> <span data-ttu-id="a5d56-105">如果要使这些控件的属性可供未来用户使用，则必须将这些控件公开给用户。</span><span class="sxs-lookup"><span data-stu-id="a5d56-105">If you want to make properties of these controls available to future users, you must expose them to the user.</span></span> <span data-ttu-id="a5d56-106">通过在用户控件中创建一个属性，并使用 `get` `set` 该属性的和访问器来影响构成控件的 private 属性中的更改，可以公开构成控件的属性。</span><span class="sxs-lookup"><span data-stu-id="a5d56-106">A property of a constituent control is exposed by creating a property in the user control, and using the `get` and `set` accessors of that property to effect the change in the private property of the constituent control.</span></span>

 <span data-ttu-id="a5d56-107">假设有一个名为的 "构成" 按钮的假设用户控件 `MyButton` 。</span><span class="sxs-lookup"><span data-stu-id="a5d56-107">Consider a hypothetical user control with a constituent button named `MyButton`.</span></span> <span data-ttu-id="a5d56-108">在此示例中，当用户请求 `ConstituentButtonBackColor` 属性时，将传递在的属性中存储的值 <xref:System.Windows.Forms.Control.BackColor%2A> `MyButton` 。</span><span class="sxs-lookup"><span data-stu-id="a5d56-108">In this example, when the user requests the `ConstituentButtonBackColor` property, the value stored in the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` is delivered.</span></span> <span data-ttu-id="a5d56-109">当用户将值分配给此属性时，该值将自动传递到的 <xref:System.Windows.Forms.Control.BackColor%2A> 属性， `MyButton` 并 `set` 将执行代码，从而更改的颜色 `MyButton` 。</span><span class="sxs-lookup"><span data-stu-id="a5d56-109">When the user assigns a value to this property, that value is automatically passed to the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` and the `set` code will execute, changing the color of `MyButton`.</span></span>

 <span data-ttu-id="a5d56-110">下面的示例演示如何公开 <xref:System.Windows.Forms.Control.BackColor%2A> "构成" 按钮的属性：</span><span class="sxs-lookup"><span data-stu-id="a5d56-110">The following example shows how to expose the <xref:System.Windows.Forms.Control.BackColor%2A> property of the constituent button:</span></span>

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

### <a name="to-expose-a-property-of-a-constituent-control"></a><span data-ttu-id="a5d56-111">公开构成控件的属性</span><span class="sxs-lookup"><span data-stu-id="a5d56-111">To expose a property of a constituent control</span></span>

1. <span data-ttu-id="a5d56-112">为用户控件创建公共属性。</span><span class="sxs-lookup"><span data-stu-id="a5d56-112">Create a public property for your user control.</span></span>

2. <span data-ttu-id="a5d56-113">在 `get` 属性的部分，编写用于检索要公开的属性的值的代码。</span><span class="sxs-lookup"><span data-stu-id="a5d56-113">In the `get` section of the property, write code that retrieves the value of the property you want to expose.</span></span>

3. <span data-ttu-id="a5d56-114">在 `set` 属性的部分，编写将属性的值传递给构成控件的公开属性的代码。</span><span class="sxs-lookup"><span data-stu-id="a5d56-114">In the `set` section of the property, write code that passes the value of the property to the exposed property of the constituent control.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5d56-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5d56-115">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="a5d56-116">Windows 窗体控件中的属性</span><span class="sxs-lookup"><span data-stu-id="a5d56-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="a5d56-117">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="a5d56-117">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
