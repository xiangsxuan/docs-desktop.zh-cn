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
# <a name="painting-and-drawing-on-controls-windows-forms-net"></a><span data-ttu-id="be869-103">在控件上绘图（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="be869-103">Painting and drawing on controls (Windows Forms .NET)</span></span>

<span data-ttu-id="be869-104">控件的自定义绘制是 Windows 窗体可以轻松完成的众多复杂任务之一。</span><span class="sxs-lookup"><span data-stu-id="be869-104">Custom painting of controls is one of the many complicated tasks made easy by Windows Forms.</span></span> <span data-ttu-id="be869-105">创作自定义控件时，有许多选项可用于处理控件的图形外观。</span><span class="sxs-lookup"><span data-stu-id="be869-105">When authoring a custom control, you have many options available to handle your control's graphical appearance.</span></span> <span data-ttu-id="be869-106">如果要创作[自定义控件](custom.md#custom-controls)（即从 <xref:System.Windows.Forms.Control> 继承的控件），则必须提供代码以呈现其图形表示形式。</span><span class="sxs-lookup"><span data-stu-id="be869-106">If you're authoring a [custom control](custom.md#custom-controls), that is, a control that inherits from <xref:System.Windows.Forms.Control>, you must provide code to render its graphical representation.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="be869-107">如果要创建[复合控件](custom.md#composite-controls)（即从 <xref:System.Windows.Forms.UserControl> 继承的控件或某个现有的 Windows 窗体控件），则可以重写标准图形表示形式，并提供你自己的图形代码。</span><span class="sxs-lookup"><span data-stu-id="be869-107">If you're creating a [composite control](custom.md#composite-controls), that is a control that inherits from <xref:System.Windows.Forms.UserControl> or one of the existing Windows Forms controls, you may override the standard graphical representation and provide your own graphics code.</span></span>

<span data-ttu-id="be869-108">如果要在不创建新控件的情况下为现有控件提供自定义呈现，选项会变得更为有限。</span><span class="sxs-lookup"><span data-stu-id="be869-108">If you want to provide custom rendering for an existing control without creating a new control, your options become more limited.</span></span> <span data-ttu-id="be869-109">但是，对于控件和应用程序，仍有各种各样的图形。</span><span class="sxs-lookup"><span data-stu-id="be869-109">However, there are still a wide range of graphical possibilities for your controls and applications.</span></span>

<span data-ttu-id="be869-110">控件呈现涉及以下元素：</span><span class="sxs-lookup"><span data-stu-id="be869-110">The following elements are involved in control rendering:</span></span>

- <span data-ttu-id="be869-111">基类 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 提供的绘图功能。</span><span class="sxs-lookup"><span data-stu-id="be869-111">The drawing functionality provided by the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="be869-112">GDI 图形库的基本元素。</span><span class="sxs-lookup"><span data-stu-id="be869-112">The essential elements of the GDI graphics library.</span></span>
- <span data-ttu-id="be869-113">绘图区域的几何图形。</span><span class="sxs-lookup"><span data-stu-id="be869-113">The geometry of the drawing region.</span></span>
- <span data-ttu-id="be869-114">释放图形资源的过程。</span><span class="sxs-lookup"><span data-stu-id="be869-114">The procedure for freeing graphics resources.</span></span>

## <a name="drawing-provided-by-control"></a><span data-ttu-id="be869-115">控件提供的绘图</span><span class="sxs-lookup"><span data-stu-id="be869-115">Drawing provided by control</span></span>

<span data-ttu-id="be869-116">基类 <xref:System.Windows.Forms.Control> 通过其 <xref:System.Windows.Forms.Control.Paint> 事件提供绘图功能。</span><span class="sxs-lookup"><span data-stu-id="be869-116">The base class <xref:System.Windows.Forms.Control> provides drawing functionality through its <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="be869-117">每当控件需要更新其显示时，它都会引发 <xref:System.Windows.Forms.Control.Paint> 事件。</span><span class="sxs-lookup"><span data-stu-id="be869-117">A control raises the <xref:System.Windows.Forms.Control.Paint> event whenever it needs to update its display.</span></span> <span data-ttu-id="be869-118">有关 .NET 中的事件的详细信息，请参阅[处理和引发事件](/dotnet/standard/events/index)。</span><span class="sxs-lookup"><span data-stu-id="be869-118">For more information about events in the .NET, see [Handling and raising events](/dotnet/standard/events/index).</span></span>

<span data-ttu-id="be869-119"><xref:System.Windows.Forms.Control.Paint> 事件的事件数据类 <xref:System.Windows.Forms.PaintEventArgs> 包含绘制控件所需的数据 - 图形对象的句柄和表示绘制区域的矩形。</span><span class="sxs-lookup"><span data-stu-id="be869-119">The event data class for the <xref:System.Windows.Forms.Control.Paint> event, <xref:System.Windows.Forms.PaintEventArgs>, holds the data needed for drawing a control - a handle to a graphics object and a rectangle that represents the region to draw in.</span></span>

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

<span data-ttu-id="be869-120"><xref:System.Drawing.Graphics> 是一个可封装绘图功能的托管类，如本文后面的 GDI 讨论中所述。</span><span class="sxs-lookup"><span data-stu-id="be869-120"><xref:System.Drawing.Graphics> is a managed class that encapsulates drawing functionality, as described in the discussion of GDI later in this article.</span></span> <span data-ttu-id="be869-121"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 是 <xref:System.Drawing.Rectangle> 结构的实例，它定义了可在其中绘制控件的可用区域。</span><span class="sxs-lookup"><span data-stu-id="be869-121">The <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is an instance of the <xref:System.Drawing.Rectangle> structure and defines the available area in which a control can draw.</span></span> <span data-ttu-id="be869-122">控件开发人员可以使用控件的 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 属性来计算 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>，如本文后面的几何图形讨论中所述。</span><span class="sxs-lookup"><span data-stu-id="be869-122">A control developer can compute the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> using the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of a control, as described in the discussion of geometry later in this article.</span></span>

### <a name="onpaint"></a><span data-ttu-id="be869-123">OnPaint</span><span class="sxs-lookup"><span data-stu-id="be869-123">OnPaint</span></span>

<span data-ttu-id="be869-124">控件必须通过重写它从 <xref:System.Windows.Forms.Control> 继承的 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法来提供呈现逻辑。</span><span class="sxs-lookup"><span data-stu-id="be869-124">A control must provide rendering logic by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="be869-125"><xref:System.Windows.Forms.Control.OnPaint%2A> 可访问图形对象和矩形，以通过传递给它的 <xref:System.Windows.Forms.PaintEventArgs> 实例的 <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> 和 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 属性进行绘制。</span><span class="sxs-lookup"><span data-stu-id="be869-125"><xref:System.Windows.Forms.Control.OnPaint%2A> gets access to a graphics object and a rectangle to draw in through the <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> properties of the <xref:System.Windows.Forms.PaintEventArgs> instance passed to it.</span></span>

<span data-ttu-id="be869-126">下面的代码使用 `System.Drawing` 命名空间：</span><span class="sxs-lookup"><span data-stu-id="be869-126">The following code uses the `System.Drawing` namespace:</span></span>

:::code language="csharp" source="./snippets/custom-painting-drawing/cs/UserControl1.cs" id="OnPaintMethod":::

:::code language="vb" source="./snippets/custom-painting-drawing/vb/UserControl1.vb" id="OnPaintMethod":::

<span data-ttu-id="be869-127"><xref:System.Windows.Forms.Control> 基类的 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法不实现任何绘图功能，只是调用注册到 <xref:System.Windows.Forms.Control.Paint> 事件的事件委托。</span><span class="sxs-lookup"><span data-stu-id="be869-127">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base <xref:System.Windows.Forms.Control> class doesn't implement any drawing functionality but merely invokes the event delegates that are registered with the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="be869-128">重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 时，应确保调用基类的 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法，以便注册的委托可接收 <xref:System.Windows.Forms.Control.Paint> 事件。</span><span class="sxs-lookup"><span data-stu-id="be869-128">When you override <xref:System.Windows.Forms.Control.OnPaint%2A>, you should typically invoke the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class so that registered delegates receive the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="be869-129">但是，绘制整个表面的控件不应调用基类的 <xref:System.Windows.Forms.Control.OnPaint%2A>，因为这会引起闪烁。</span><span class="sxs-lookup"><span data-stu-id="be869-129">However, controls that paint their entire surface shouldn't invoke the base class's <xref:System.Windows.Forms.Control.OnPaint%2A>, as this introduces flicker.</span></span>

> [!NOTE]
> <span data-ttu-id="be869-130">请勿直接从控件调用 <xref:System.Windows.Forms.Control.OnPaint%2A>；请改为调用 <xref:System.Windows.Forms.Control.Invalidate%2A> 方法（从 <xref:System.Windows.Forms.Control> 继承）或调用 <xref:System.Windows.Forms.Control.Invalidate%2A> 的其他方法。</span><span class="sxs-lookup"><span data-stu-id="be869-130">Don't invoke <xref:System.Windows.Forms.Control.OnPaint%2A> directly from your control; instead, invoke the <xref:System.Windows.Forms.Control.Invalidate%2A> method (inherited from <xref:System.Windows.Forms.Control>) or some other method that invokes <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="be869-131"><xref:System.Windows.Forms.Control.Invalidate%2A> 方法又会调用 <xref:System.Windows.Forms.Control.OnPaint%2A>。</span><span class="sxs-lookup"><span data-stu-id="be869-131">The <xref:System.Windows.Forms.Control.Invalidate%2A> method in turn invokes <xref:System.Windows.Forms.Control.OnPaint%2A>.</span></span> <span data-ttu-id="be869-132">重载 <xref:System.Windows.Forms.Control.Invalidate%2A> 方法，并根据提供给 <xref:System.Windows.Forms.Control.Invalidate%2A> `e` 的参数重绘其部分屏幕区域或整个屏幕区域。</span><span class="sxs-lookup"><span data-stu-id="be869-132">The <xref:System.Windows.Forms.Control.Invalidate%2A> method is overloaded, and, depending on the arguments supplied to <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, redraws either some or all of its screen area.</span></span>

<span data-ttu-id="be869-133">控件的 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法中的代码将在第一次绘制控件以及每次刷新该控件时执行。</span><span class="sxs-lookup"><span data-stu-id="be869-133">The code in the <xref:System.Windows.Forms.Control.OnPaint%2A> method of your control will execute when the control is first drawn, and whenever it is refreshed.</span></span> <span data-ttu-id="be869-134">若要确保在每次调整控件大小时都重新进行绘制，请将下面的行添加到控件的构造函数中：</span><span class="sxs-lookup"><span data-stu-id="be869-134">To ensure that your control is redrawn every time it is resized, add the following line to the constructor of your control:</span></span>

```csharp
SetStyle(ControlStyles.ResizeRedraw, true);
```

```vb
SetStyle(ControlStyles.ResizeRedraw, True)
```

### <a name="onpaintbackground"></a><span data-ttu-id="be869-135">OnPaintBackground</span><span class="sxs-lookup"><span data-stu-id="be869-135">OnPaintBackground</span></span>

<span data-ttu-id="be869-136"><xref:System.Windows.Forms.Control> 基类定义了另一种可用于绘图的方法，即 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="be869-136">The base <xref:System.Windows.Forms.Control> class defines another method that is useful for drawing, the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method.</span></span>

```csharp
protected virtual void OnPaintBackground(PaintEventArgs e);
```

```vb
Protected Overridable Sub OnPaintBackground(e As PaintEventArgs)
```

<span data-ttu-id="be869-137"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> 绘制窗口的背景（并以相同方式绘制形状），并保证速度较快，而 <xref:System.Windows.Forms.Control.OnPaint%2A> 绘制详细信息，速度可能较慢，因为单个绘制请求会合并为一个 <xref:System.Windows.Forms.Control.Paint> 事件，其中涵盖了所有需要重新绘制的区域。</span><span class="sxs-lookup"><span data-stu-id="be869-137"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> paints the background (and in that way, the shape) of the window and is guaranteed to be fast, while <xref:System.Windows.Forms.Control.OnPaint%2A> paints the details and might be slower because individual paint requests are combined into one <xref:System.Windows.Forms.Control.Paint> event that covers all areas that have to be redrawn.</span></span> <span data-ttu-id="be869-138">例如，如果想要为控件绘制颜色渐变的背景，则可能需要调用 <xref:System.Windows.Forms.Control.OnPaintBackground%2A>。</span><span class="sxs-lookup"><span data-stu-id="be869-138">You might want to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> if, for instance, you want to draw a gradient-colored background for your control.</span></span>

<span data-ttu-id="be869-139">虽然 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 具有类似事件的命名法并采用与 `OnPaint` 方法相同的参数，但 `OnPaintBackground` 不是真正的事件方法。</span><span class="sxs-lookup"><span data-stu-id="be869-139">While <xref:System.Windows.Forms.Control.OnPaintBackground%2A> has an event-like nomenclature and takes the same argument as the `OnPaint` method, `OnPaintBackground` is not a true event method.</span></span> <span data-ttu-id="be869-140">不存在 `PaintBackground` 事件，并且 `OnPaintBackground` 不调用事件委托。</span><span class="sxs-lookup"><span data-stu-id="be869-140">There is no `PaintBackground` event and `OnPaintBackground` doesn't invoke event delegates.</span></span> <span data-ttu-id="be869-141">重写 `OnPaintBackground` 方法时，无需使用派生类即可调用其基类的 `OnPaintBackground` 方法。</span><span class="sxs-lookup"><span data-stu-id="be869-141">When overriding the `OnPaintBackground` method, a derived class is not required to invoke the `OnPaintBackground` method of its base class.</span></span>

## <a name="gdi-basics"></a><span data-ttu-id="be869-142">GDI+ 基础知识</span><span class="sxs-lookup"><span data-stu-id="be869-142">GDI+ Basics</span></span>

<span data-ttu-id="be869-143"><xref:System.Drawing.Graphics> 类提供用于绘制各种形状（如圆形、三角形、弧形和椭圆形）的方法，以及用于显示文本的方法。</span><span class="sxs-lookup"><span data-stu-id="be869-143">The <xref:System.Drawing.Graphics> class provides methods for drawing various shapes such as circles, triangles, arcs, and ellipses, and methods for displaying text.</span></span> <span data-ttu-id="be869-144"><xref:System.Drawing?displayProperty=nameWithType> 命名空间包含命名空间和类，它们可用于封装图形元素，如形状（圆形、矩形、弧形等）、颜色、字体、画笔等。</span><span class="sxs-lookup"><span data-stu-id="be869-144">The <xref:System.Drawing?displayProperty=nameWithType> namespace contains namespaces and classes that encapsulate graphics elements such as shapes (circles, rectangles, arcs, and others), colors, fonts, brushes, and so on.</span></span><!-- TODO  For more information about GDI, see [Using Managed Graphics Classes](../advanced/using-managed-graphics-classes.md).-->

## <a name="geometry-of-the-drawing-region"></a><span data-ttu-id="be869-145">绘图区域的几何图形</span><span class="sxs-lookup"><span data-stu-id="be869-145">Geometry of the Drawing Region</span></span>

<span data-ttu-id="be869-146">控件的 <xref:System.Windows.Forms.Control.ClientRectangle%2A> 属性指定可用于用户屏幕上的控件的矩形区域，而 <xref:System.Windows.Forms.PaintEventArgs> 的 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 属性指定所绘制的区域。</span><span class="sxs-lookup"><span data-stu-id="be869-146">The <xref:System.Windows.Forms.Control.ClientRectangle%2A> property of a control specifies the rectangular region available to the control on the user's screen, while the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs> specifies the area that is painted.</span></span> <span data-ttu-id="be869-147">当控件的一小部分显示发生变化时，控件可能只需要绘制部分可用区域。</span><span class="sxs-lookup"><span data-stu-id="be869-147">A control might need to paint only a portion of its available area, as is the case when a small section of the control's display changes.</span></span> <span data-ttu-id="be869-148">在这些情况下，控件开发人员必须计算要在其中进行绘制的实际矩形，并将其传递到 <xref:System.Windows.Forms.Control.Invalidate%2A>。</span><span class="sxs-lookup"><span data-stu-id="be869-148">In those situations, a control developer must compute the actual rectangle to draw in and pass that to <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="be869-149">采用 <xref:System.Drawing.Rectangle> 或 <xref:System.Drawing.Region> 作为参数的 <xref:System.Windows.Forms.Control.Invalidate%2A> 的重载版本使用该参数生成 <xref:System.Windows.Forms.PaintEventArgs> 的 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="be869-149">The overloaded versions of <xref:System.Windows.Forms.Control.Invalidate%2A> that take a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.Region> as an argument use that argument to generate the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs>.</span></span>

## <a name="freeing-graphics-resources"></a><span data-ttu-id="be869-150">释放图形资源</span><span class="sxs-lookup"><span data-stu-id="be869-150">Freeing Graphics Resources</span></span>

<span data-ttu-id="be869-151">图形对象成本昂贵，因为它们使用系统资源。</span><span class="sxs-lookup"><span data-stu-id="be869-151">Graphics objects are expensive because they use system resources.</span></span> <span data-ttu-id="be869-152">此类对象包括 <xref:System.Drawing.Graphics?displayProperty=nameWithType> 类的实例以及 <xref:System.Drawing.Brush?displayProperty=nameWithType>、<xref:System.Drawing.Pen?displayProperty=nameWithType> 和其他图形类的实例。</span><span class="sxs-lookup"><span data-stu-id="be869-152">Such objects include instances of the <xref:System.Drawing.Graphics?displayProperty=nameWithType> class and instances of <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>, and other graphics classes.</span></span> <span data-ttu-id="be869-153">请务必仅在需要时才创建图形资源，并在使用完之后立即释放。</span><span class="sxs-lookup"><span data-stu-id="be869-153">It's important that you create a graphics resource only when you need it and release it soon as you're finished using it.</span></span> <span data-ttu-id="be869-154">如果创建实现 <xref:System.IDisposable> 接口的类型的实例，请在使用完该实例之后，调用其 <xref:System.IDisposable.Dispose%2A> 方法来释放资源。</span><span class="sxs-lookup"><span data-stu-id="be869-154">If you create an instance of a type that implements the <xref:System.IDisposable> interface, call its <xref:System.IDisposable.Dispose%2A> method when you're finished with it to free resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="be869-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be869-155">See also</span></span>

- [<span data-ttu-id="be869-156">自定义控件的类型</span><span class="sxs-lookup"><span data-stu-id="be869-156">Types of custom controls</span></span>](custom.md)
