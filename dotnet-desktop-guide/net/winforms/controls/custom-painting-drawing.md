---
title: 控件的自定义绘制
description: 了解如何在 .NET 的 Windows 窗体中通过 OnPaint 方法和绘制事件来自定义控件的外观。
ms.date: 10/26/2020
ms.topic: overview
dev_langs:
- csharp
- vb
f1_keywords:
- OnPaint
helpviewer_keywords:
- controls [Windows Forms], user controls
- controls [Windows Forms], types of
- composite controls [Windows Forms]
- extended controls [Windows Forms]
- controls [Windows Forms], extended
- user controls [Windows Forms]
- custom controls [Windows Forms]
- controls [Windows Forms], composite
ms.openlocfilehash: 8d9775c02addb68cc962cdc2e4bf2d1baa6ab2a1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941962"
---
# <a name="painting-and-drawing-on-controls-windows-forms-net"></a>在控件上绘图（Windows 窗体 .NET）

控件的自定义绘制是 Windows 窗体可以轻松完成的众多复杂任务之一。 创作自定义控件时，有许多选项可用于处理控件的图形外观。 如果要创作[自定义控件](custom.md#custom-controls)（即从 <xref:System.Windows.Forms.Control> 继承的控件），则必须提供代码以呈现其图形表示形式。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

如果要创建[复合控件](custom.md#composite-controls)（即从 <xref:System.Windows.Forms.UserControl> 继承的控件或某个现有的 Windows 窗体控件），则可以重写标准图形表示形式，并提供你自己的图形代码。

如果要在不创建新控件的情况下为现有控件提供自定义呈现，选项会变得更为有限。 但是，对于控件和应用程序，仍有各种各样的图形。

控件呈现涉及以下元素：

- 基类 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 提供的绘图功能。
- GDI 图形库的基本元素。
- 绘图区域的几何图形。
- 释放图形资源的过程。

## <a name="drawing-provided-by-control"></a>控件提供的绘图

基类 <xref:System.Windows.Forms.Control> 通过其 <xref:System.Windows.Forms.Control.Paint> 事件提供绘图功能。 每当控件需要更新其显示时，它都会引发 <xref:System.Windows.Forms.Control.Paint> 事件。 有关 .NET 中的事件的详细信息，请参阅[处理和引发事件](/dotnet/standard/events/index)。

<xref:System.Windows.Forms.Control.Paint> 事件的事件数据类 <xref:System.Windows.Forms.PaintEventArgs> 包含绘制控件所需的数据 - 图形对象的句柄和表示绘制区域的矩形。

```csharp
public class PaintEventArgs : EventArgs, IDisposable
{

    public System.Drawing.Rectangle ClipRectangle {get;}
    public System.Drawing.Graphics Graphics {get;}

    // Other properties and methods.
}
```

```vb
Public Class PaintEventArgs
    Inherits EventArgs
    Implements IDisposable

    Public ReadOnly Property ClipRectangle As System.Drawing.Rectangle
    Public ReadOnly Property Graphics As System.Drawing.Graphics

    ' Other properties and methods.
End Class
```

<xref:System.Drawing.Graphics> 是一个可封装绘图功能的托管类，如本文后面的 GDI 讨论中所述。 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 是 <xref:System.Drawing.Rectangle> 结构的实例，它定义了可在其中绘制控件的可用区域。 控件开发人员可以使用控件的 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 属性来计算 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>，如本文后面的几何图形讨论中所述。

### <a name="onpaint"></a>OnPaint

控件必须通过重写它从 <xref:System.Windows.Forms.Control> 继承的 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法来提供呈现逻辑。 <xref:System.Windows.Forms.Control.OnPaint%2A> 可访问图形对象和矩形，以通过传递给它的 <xref:System.Windows.Forms.PaintEventArgs> 实例的 <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> 和 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 属性进行绘制。

下面的代码使用 `System.Drawing` 命名空间：

:::code language="csharp" source="./snippets/custom-painting-drawing/cs/UserControl1.cs" id="OnPaintMethod":::

:::code language="vb" source="./snippets/custom-painting-drawing/vb/UserControl1.vb" id="OnPaintMethod":::

<xref:System.Windows.Forms.Control> 基类的 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法不实现任何绘图功能，只是调用注册到 <xref:System.Windows.Forms.Control.Paint> 事件的事件委托。 重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 时，应确保调用基类的 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法，以便注册的委托可接收 <xref:System.Windows.Forms.Control.Paint> 事件。 但是，绘制整个表面的控件不应调用基类的 <xref:System.Windows.Forms.Control.OnPaint%2A>，因为这会引起闪烁。

> [!NOTE]
> 请勿直接从控件调用 <xref:System.Windows.Forms.Control.OnPaint%2A>；请改为调用 <xref:System.Windows.Forms.Control.Invalidate%2A> 方法（从 <xref:System.Windows.Forms.Control> 继承）或调用 <xref:System.Windows.Forms.Control.Invalidate%2A> 的其他方法。 <xref:System.Windows.Forms.Control.Invalidate%2A> 方法又会调用 <xref:System.Windows.Forms.Control.OnPaint%2A>。 重载 <xref:System.Windows.Forms.Control.Invalidate%2A> 方法，并根据提供给 <xref:System.Windows.Forms.Control.Invalidate%2A> `e` 的参数重绘其部分屏幕区域或整个屏幕区域。

控件的 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法中的代码将在第一次绘制控件以及每次刷新该控件时执行。 若要确保在每次调整控件大小时都重新进行绘制，请将下面的行添加到控件的构造函数中：

```csharp
SetStyle(ControlStyles.ResizeRedraw, true);
```

```vb
SetStyle(ControlStyles.ResizeRedraw, True)
```

### <a name="onpaintbackground"></a>OnPaintBackground

<xref:System.Windows.Forms.Control> 基类定义了另一种可用于绘图的方法，即 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 方法。

```csharp
protected virtual void OnPaintBackground(PaintEventArgs e);
```

```vb
Protected Overridable Sub OnPaintBackground(e As PaintEventArgs)
```

<xref:System.Windows.Forms.Control.OnPaintBackground%2A> 绘制窗口的背景（并以相同方式绘制形状），并保证速度较快，而 <xref:System.Windows.Forms.Control.OnPaint%2A> 绘制详细信息，速度可能较慢，因为单个绘制请求会合并为一个 <xref:System.Windows.Forms.Control.Paint> 事件，其中涵盖了所有需要重新绘制的区域。 例如，如果想要为控件绘制颜色渐变的背景，则可能需要调用 <xref:System.Windows.Forms.Control.OnPaintBackground%2A>。

虽然 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 具有类似事件的命名法并采用与 `OnPaint` 方法相同的参数，但 `OnPaintBackground` 不是真正的事件方法。 不存在 `PaintBackground` 事件，并且 `OnPaintBackground` 不调用事件委托。 重写 `OnPaintBackground` 方法时，无需使用派生类即可调用其基类的 `OnPaintBackground` 方法。

## <a name="gdi-basics"></a>GDI+ 基础知识

<xref:System.Drawing.Graphics> 类提供用于绘制各种形状（如圆形、三角形、弧形和椭圆形）的方法，以及用于显示文本的方法。 <xref:System.Drawing?displayProperty=nameWithType> 命名空间包含命名空间和类，它们可用于封装图形元素，如形状（圆形、矩形、弧形等）、颜色、字体、画笔等。<!-- TODO  For more information about GDI, see [Using Managed Graphics Classes](../advanced/using-managed-graphics-classes.md).-->

## <a name="geometry-of-the-drawing-region"></a>绘图区域的几何图形

控件的 <xref:System.Windows.Forms.Control.ClientRectangle%2A> 属性指定可用于用户屏幕上的控件的矩形区域，而 <xref:System.Windows.Forms.PaintEventArgs> 的 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 属性指定所绘制的区域。 当控件的一小部分显示发生变化时，控件可能只需要绘制部分可用区域。 在这些情况下，控件开发人员必须计算要在其中进行绘制的实际矩形，并将其传递到 <xref:System.Windows.Forms.Control.Invalidate%2A>。 采用 <xref:System.Drawing.Rectangle> 或 <xref:System.Drawing.Region> 作为参数的 <xref:System.Windows.Forms.Control.Invalidate%2A> 的重载版本使用该参数生成 <xref:System.Windows.Forms.PaintEventArgs> 的 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 属性。

## <a name="freeing-graphics-resources"></a>释放图形资源

图形对象成本昂贵，因为它们使用系统资源。 此类对象包括 <xref:System.Drawing.Graphics?displayProperty=nameWithType> 类的实例以及 <xref:System.Drawing.Brush?displayProperty=nameWithType>、<xref:System.Drawing.Pen?displayProperty=nameWithType> 和其他图形类的实例。 请务必仅在需要时才创建图形资源，并在使用完之后立即释放。 如果创建实现 <xref:System.IDisposable> 接口的类型的实例，请在使用完该实例之后，调用其 <xref:System.IDisposable.Dispose%2A> 方法来释放资源。

## <a name="see-also"></a>另请参阅

- [自定义控件的类型](custom.md)
