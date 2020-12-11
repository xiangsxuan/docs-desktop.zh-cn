---
title: 呈现控件
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- OnPaintBackground method [Windows Forms], invoking in Windows Forms custom controls
- custom controls [Windows Forms], graphics resources
- custom controls [Windows Forms], invalidation and painting
ms.assetid: aae8e1e6-4786-432b-a15e-f4c44760d302
ms.openlocfilehash: 86e219723dde8c10a8cc0d4ee7bdf149cde399bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972013"
---
# <a name="rendering-a-windows-forms-control"></a><span data-ttu-id="3cd98-102">呈现 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="3cd98-102">Rendering a Windows Forms Control</span></span>

<span data-ttu-id="3cd98-103">呈现是指在用户屏幕上创建视觉对象表示形式的过程。</span><span class="sxs-lookup"><span data-stu-id="3cd98-103">Rendering refers to the process of creating a visual representation on a user's screen.</span></span> <span data-ttu-id="3cd98-104">Windows 窗体使用 GDI (新的 Windows 图形库) 来呈现。</span><span class="sxs-lookup"><span data-stu-id="3cd98-104">Windows Forms uses GDI (the new Windows graphics library) for rendering.</span></span> <span data-ttu-id="3cd98-105">提供对 GDI 的访问的托管类位于 <xref:System.Drawing?displayProperty=nameWithType> 命名空间及其子命名空间中。</span><span class="sxs-lookup"><span data-stu-id="3cd98-105">The managed classes that provide access to GDI are in the <xref:System.Drawing?displayProperty=nameWithType> namespace and its subnamespaces.</span></span>  
  
 <span data-ttu-id="3cd98-106">控件呈现涉及以下元素：</span><span class="sxs-lookup"><span data-stu-id="3cd98-106">The following elements are involved in control rendering:</span></span>  
  
- <span data-ttu-id="3cd98-107">基类提供的绘制功能 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="3cd98-107">The drawing functionality provided by the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="3cd98-108">GDI 图形库的重要元素。</span><span class="sxs-lookup"><span data-stu-id="3cd98-108">The essential elements of the GDI graphics library.</span></span>  
  
- <span data-ttu-id="3cd98-109">绘图区域的几何。</span><span class="sxs-lookup"><span data-stu-id="3cd98-109">The geometry of the drawing region.</span></span>  
  
- <span data-ttu-id="3cd98-110">用于释放图形资源的过程。</span><span class="sxs-lookup"><span data-stu-id="3cd98-110">The procedure for freeing graphics resources.</span></span>  
  
## <a name="drawing-functionality-provided-by-control"></a><span data-ttu-id="3cd98-111">控件提供的绘制功能</span><span class="sxs-lookup"><span data-stu-id="3cd98-111">Drawing Functionality Provided by Control</span></span>  

 <span data-ttu-id="3cd98-112">基类 <xref:System.Windows.Forms.Control> 通过其事件提供绘制功能 <xref:System.Windows.Forms.Control.Paint> 。</span><span class="sxs-lookup"><span data-stu-id="3cd98-112">The base class <xref:System.Windows.Forms.Control> provides drawing functionality through its <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="3cd98-113"><xref:System.Windows.Forms.Control.Paint>每当控件需要更新其显示时，都会引发事件。</span><span class="sxs-lookup"><span data-stu-id="3cd98-113">A control raises the <xref:System.Windows.Forms.Control.Paint> event whenever it needs to update its display.</span></span> <span data-ttu-id="3cd98-114">有关 .NET Framework 中事件的详细信息，请参阅 [处理和引发事件](/dotnet/standard/events/index)。</span><span class="sxs-lookup"><span data-stu-id="3cd98-114">For more information about events in the .NET Framework, see [Handling and Raising Events](/dotnet/standard/events/index).</span></span>  
  
 <span data-ttu-id="3cd98-115">事件的事件数据类 <xref:System.Windows.Forms.Control.Paint> <xref:System.Windows.Forms.PaintEventArgs> 包含绘制控件所需的数据-图形对象的句柄和表示要在其中绘制的区域的矩形对象。</span><span class="sxs-lookup"><span data-stu-id="3cd98-115">The event data class for the <xref:System.Windows.Forms.Control.Paint> event, <xref:System.Windows.Forms.PaintEventArgs>, holds the data needed for drawing a control — a handle to a graphics object and a rectangle object that represents the region to draw in.</span></span> <span data-ttu-id="3cd98-116">这些对象在以下代码片段中显示为粗体。</span><span class="sxs-lookup"><span data-stu-id="3cd98-116">These objects are shown in bold in the following code fragment.</span></span>  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   Implements IDisposable  
  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property  
   ' Other properties and methods.  
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs, IDisposable {  
public System.Drawing.Rectangle ClipRectangle {get;}  
public System.Drawing.Graphics Graphics {get;}  
// Other properties and methods.  
...  
}  
```  
  
 <span data-ttu-id="3cd98-117"><xref:System.Drawing.Graphics> 是一个封装了绘制功能的托管类，如本主题后面的 GDI 讨论中所述。</span><span class="sxs-lookup"><span data-stu-id="3cd98-117"><xref:System.Drawing.Graphics> is a managed class that encapsulates drawing functionality, as described in the discussion of GDI later in this topic.</span></span> <span data-ttu-id="3cd98-118"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>是结构的实例 <xref:System.Drawing.Rectangle> ，用于定义可在其中绘制控件的可用区域。</span><span class="sxs-lookup"><span data-stu-id="3cd98-118">The <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is an instance of the <xref:System.Drawing.Rectangle> structure and defines the available area in which a control can draw.</span></span> <span data-ttu-id="3cd98-119">控件开发人员可以 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 使用 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 控件的属性计算，如本主题后面的几何讨论中所述。</span><span class="sxs-lookup"><span data-stu-id="3cd98-119">A control developer can compute the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> using the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of a control, as described in the discussion of geometry later in this topic.</span></span>  
  
 <span data-ttu-id="3cd98-120">控件必须通过重写继承自的方法来提供呈现逻辑 <xref:System.Windows.Forms.Control.OnPaint%2A> <xref:System.Windows.Forms.Control> 。</span><span class="sxs-lookup"><span data-stu-id="3cd98-120">A control must provide rendering logic by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="3cd98-121"><xref:System.Windows.Forms.Control.OnPaint%2A> 获取对图形对象的访问，以及通过 <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 传递给它的实例的属性在中绘制的矩形 <xref:System.Windows.Forms.PaintEventArgs> 。</span><span class="sxs-lookup"><span data-stu-id="3cd98-121"><xref:System.Windows.Forms.Control.OnPaint%2A> gets access to a graphics object and a rectangle to draw in through the <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> properties of the <xref:System.Windows.Forms.PaintEventArgs> instance passed to it.</span></span>  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 <span data-ttu-id="3cd98-122"><xref:System.Windows.Forms.Control.OnPaint%2A>基类的方法 <xref:System.Windows.Forms.Control> 不会实现任何绘制功能，而只会调用向事件注册的事件委托 <xref:System.Windows.Forms.Control.Paint> 。</span><span class="sxs-lookup"><span data-stu-id="3cd98-122">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base <xref:System.Windows.Forms.Control> class does not implement any drawing functionality but merely invokes the event delegates that are registered with the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="3cd98-123">重写时 <xref:System.Windows.Forms.Control.OnPaint%2A> ，通常应调用基类的 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法，以便注册的委托接收 <xref:System.Windows.Forms.Control.Paint> 事件。</span><span class="sxs-lookup"><span data-stu-id="3cd98-123">When you override <xref:System.Windows.Forms.Control.OnPaint%2A>, you should typically invoke the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class so that registered delegates receive the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="3cd98-124">但是，绘制整个图面的控件不应调用基类的 <xref:System.Windows.Forms.Control.OnPaint%2A> ，因为这会引入闪烁。</span><span class="sxs-lookup"><span data-stu-id="3cd98-124">However, controls that paint their entire surface should not invoke the base class's <xref:System.Windows.Forms.Control.OnPaint%2A>, as this introduces flicker.</span></span> <span data-ttu-id="3cd98-125">有关替代事件的示例 <xref:System.Windows.Forms.Control.OnPaint%2A> ，请参阅 [如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)。</span><span class="sxs-lookup"><span data-stu-id="3cd98-125">For an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> event, see the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3cd98-126">不要 <xref:System.Windows.Forms.Control.OnPaint%2A> 直接从控件调用; 而是调用 <xref:System.Windows.Forms.Control.Invalidate%2A> (继承自) 的方法 <xref:System.Windows.Forms.Control> 或调用的其他方法 <xref:System.Windows.Forms.Control.Invalidate%2A> 。</span><span class="sxs-lookup"><span data-stu-id="3cd98-126">Do not invoke <xref:System.Windows.Forms.Control.OnPaint%2A> directly from your control; instead, invoke the <xref:System.Windows.Forms.Control.Invalidate%2A> method (inherited from <xref:System.Windows.Forms.Control>) or some other method that invokes <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="3cd98-127"><xref:System.Windows.Forms.Control.Invalidate%2A>方法又会调用 <xref:System.Windows.Forms.Control.OnPaint%2A> 。</span><span class="sxs-lookup"><span data-stu-id="3cd98-127">The <xref:System.Windows.Forms.Control.Invalidate%2A> method in turn invokes <xref:System.Windows.Forms.Control.OnPaint%2A>.</span></span> <span data-ttu-id="3cd98-128"><xref:System.Windows.Forms.Control.Invalidate%2A>重载方法时，控件会重 <xref:System.Windows.Forms.Control.Invalidate%2A> `e` 绘其部分或全部屏幕区域，具体取决于提供给的参数。</span><span class="sxs-lookup"><span data-stu-id="3cd98-128">The <xref:System.Windows.Forms.Control.Invalidate%2A> method is overloaded, and, depending on the arguments supplied to <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, a control redraws either some or all of its screen area.</span></span>  
  
 <span data-ttu-id="3cd98-129">基类 <xref:System.Windows.Forms.Control> 定义可用于绘制的另一种方法，即 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="3cd98-129">The base <xref:System.Windows.Forms.Control> class defines another method that is useful for drawing — the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method.</span></span>  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <span data-ttu-id="3cd98-130"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> 绘制背景 (，从而使窗口) 的形状，并保证其速度非常快，同时 <xref:System.Windows.Forms.Control.OnPaint%2A> 绘制详细信息并可能比较慢，因为单个绘制请求合并为一个 <xref:System.Windows.Forms.Control.Paint> 事件，该事件涵盖了所有需要重新绘制的区域。</span><span class="sxs-lookup"><span data-stu-id="3cd98-130"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> paints the background (and thereby the shape) of the window and is guaranteed to be fast, while <xref:System.Windows.Forms.Control.OnPaint%2A> paints the details and might be slower because individual paint requests are combined into one <xref:System.Windows.Forms.Control.Paint> event that covers all areas that have to be redrawn.</span></span> <span data-ttu-id="3cd98-131">例如， <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 如果想要绘制控件的渐变颜色背景，则可能需要调用。</span><span class="sxs-lookup"><span data-stu-id="3cd98-131">You might want to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> if, for instance, you want to draw a gradient-colored background for your control.</span></span>  
  
 <span data-ttu-id="3cd98-132">虽然 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 具有类似事件的命名法并采用与方法相同的参数 `OnPaint` ，但并 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 不是真正的事件方法。</span><span class="sxs-lookup"><span data-stu-id="3cd98-132">While <xref:System.Windows.Forms.Control.OnPaintBackground%2A> has an event-like nomenclature and takes the same argument as the `OnPaint` method, <xref:System.Windows.Forms.Control.OnPaintBackground%2A> is not a true event method.</span></span> <span data-ttu-id="3cd98-133">没有 `PaintBackground` 事件，并且不 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 调用事件委托。</span><span class="sxs-lookup"><span data-stu-id="3cd98-133">There is no `PaintBackground` event and <xref:System.Windows.Forms.Control.OnPaintBackground%2A> does not invoke event delegates.</span></span> <span data-ttu-id="3cd98-134">重写 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 方法时，派生类不需要调用 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 其基类的方法。</span><span class="sxs-lookup"><span data-stu-id="3cd98-134">When overriding the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method, a derived class is not required to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method of its base class.</span></span>  
  
## <a name="gdi-basics"></a><span data-ttu-id="3cd98-135">GDI + 基础知识</span><span class="sxs-lookup"><span data-stu-id="3cd98-135">GDI+ Basics</span></span>  

 <span data-ttu-id="3cd98-136"><xref:System.Drawing.Graphics>类提供用于绘制各种形状（如圆、三角形、弧形和椭圆）的方法，以及用于显示文本的方法。</span><span class="sxs-lookup"><span data-stu-id="3cd98-136">The <xref:System.Drawing.Graphics> class provides methods for drawing various shapes such as circles, triangles, arcs, and ellipses, as well as methods for displaying text.</span></span> <span data-ttu-id="3cd98-137"><xref:System.Drawing?displayProperty=nameWithType>命名空间及其子命名空间包含类，这些类封装图形元素，如形状 (圆形、矩形、弧形以及其他) 、颜色、字体、画笔等。</span><span class="sxs-lookup"><span data-stu-id="3cd98-137">The <xref:System.Drawing?displayProperty=nameWithType> namespace and its subnamespaces contain classes that encapsulate graphics elements such as shapes (circles, rectangles, arcs, and others), colors, fonts, brushes, and so on.</span></span> <span data-ttu-id="3cd98-138">有关 GDI 的详细信息，请参阅 [使用托管图形类](../advanced/using-managed-graphics-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="3cd98-138">For more information about GDI, see [Using Managed Graphics Classes](../advanced/using-managed-graphics-classes.md).</span></span> <span data-ttu-id="3cd98-139">[如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)中还介绍了 GDI 的基本知识。</span><span class="sxs-lookup"><span data-stu-id="3cd98-139">The essentials of GDI are also described in the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="geometry-of-the-drawing-region"></a><span data-ttu-id="3cd98-140">绘图区域的几何图形</span><span class="sxs-lookup"><span data-stu-id="3cd98-140">Geometry of the Drawing Region</span></span>  

 <span data-ttu-id="3cd98-141"><xref:System.Windows.Forms.Control.ClientRectangle%2A>控件的属性指定可用于用户屏幕上的控件的矩形区域，而的 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 属性 <xref:System.Windows.Forms.PaintEventArgs> 指定实际绘制的区域。</span><span class="sxs-lookup"><span data-stu-id="3cd98-141">The <xref:System.Windows.Forms.Control.ClientRectangle%2A> property of a control specifies the rectangular region available to the control on the user's screen, while the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs> specifies the area that is actually painted.</span></span> <span data-ttu-id="3cd98-142"> (请记住，在将 <xref:System.Windows.Forms.Control.Paint> <xref:System.Windows.Forms.PaintEventArgs> 实例作为其参数) 的事件方法中完成了绘制。</span><span class="sxs-lookup"><span data-stu-id="3cd98-142">(Remember that painting is done in the <xref:System.Windows.Forms.Control.Paint> event method that takes a <xref:System.Windows.Forms.PaintEventArgs> instance as its argument).</span></span> <span data-ttu-id="3cd98-143">控件可能只需要绘制部分可用区域，这种情况下，当控件的小部分显示更改时。</span><span class="sxs-lookup"><span data-stu-id="3cd98-143">A control might need to paint only a portion of its available area, as is the case when a small section of the control's display changes.</span></span> <span data-ttu-id="3cd98-144">在这些情况下，控件开发人员必须计算要在其中进行绘制的实际矩形，并将其传递给 <xref:System.Windows.Forms.Control.Invalidate%2A> 。</span><span class="sxs-lookup"><span data-stu-id="3cd98-144">In those situations, a control developer must compute the actual rectangle to draw in and pass that to <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="3cd98-145"><xref:System.Windows.Forms.Control.Invalidate%2A>采用或作为参数的的重载 <xref:System.Drawing.Rectangle> 版本 <xref:System.Drawing.Region> 使用该参数来生成的 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 属性 <xref:System.Windows.Forms.PaintEventArgs> 。</span><span class="sxs-lookup"><span data-stu-id="3cd98-145">The overloaded versions of <xref:System.Windows.Forms.Control.Invalidate%2A> that take a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.Region> as an argument use that argument to generate the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
 <span data-ttu-id="3cd98-146">下面的代码段演示 `FlashTrackBar` 自定义控件如何计算要在中绘制的矩形区域。</span><span class="sxs-lookup"><span data-stu-id="3cd98-146">The following code fragment shows how the `FlashTrackBar` custom control computes the rectangular area to draw in.</span></span> <span data-ttu-id="3cd98-147">`client`变量表示 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="3cd98-147">The `client` variable denotes the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property.</span></span> <span data-ttu-id="3cd98-148">有关完整示例，请参阅 [如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)。</span><span class="sxs-lookup"><span data-stu-id="3cd98-148">For a complete sample, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a><span data-ttu-id="3cd98-149">释放图形资源</span><span class="sxs-lookup"><span data-stu-id="3cd98-149">Freeing Graphics Resources</span></span>  

 <span data-ttu-id="3cd98-150">图形对象开销高昂，因为它们使用系统资源。</span><span class="sxs-lookup"><span data-stu-id="3cd98-150">Graphics objects are expensive because they use system resources.</span></span> <span data-ttu-id="3cd98-151">此类对象包括类的实例 <xref:System.Drawing.Graphics?displayProperty=nameWithType> <xref:System.Drawing.Brush?displayProperty=nameWithType> ，以及、 <xref:System.Drawing.Pen?displayProperty=nameWithType> 和其他图形类的实例。</span><span class="sxs-lookup"><span data-stu-id="3cd98-151">Such objects include instances of the <xref:System.Drawing.Graphics?displayProperty=nameWithType> class as well as instances of <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>, and other graphics classes.</span></span> <span data-ttu-id="3cd98-152">只有在需要图形资源并在使用完毕后立即将其释放，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="3cd98-152">It is important that you create a graphics resource only when you need it and release it soon as you are finished using it.</span></span> <span data-ttu-id="3cd98-153">如果创建实现接口的类型 <xref:System.IDisposable> ，请在完成该操作后调用其方法，以便 <xref:System.IDisposable.Dispose%2A> 释放资源。</span><span class="sxs-lookup"><span data-stu-id="3cd98-153">If you create a type that implements the <xref:System.IDisposable> interface, call its <xref:System.IDisposable.Dispose%2A> method when you are finished with it in order to free resources.</span></span>  
  
 <span data-ttu-id="3cd98-154">下面的代码段演示 `FlashTrackBar` 自定义控件如何创建和释放 <xref:System.Drawing.Brush> 资源。</span><span class="sxs-lookup"><span data-stu-id="3cd98-154">The following code fragment shows how the `FlashTrackBar` custom control creates and releases a <xref:System.Drawing.Brush> resource.</span></span> <span data-ttu-id="3cd98-155">有关完整的源代码，请参阅 [如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)。</span><span class="sxs-lookup"><span data-stu-id="3cd98-155">For the complete source code, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="3cd98-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cd98-156">See also</span></span>

- [<span data-ttu-id="3cd98-157">如何：创建显示进度的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="3cd98-157">How to: Create a Windows Forms Control That Shows Progress</span></span>](how-to-create-a-windows-forms-control-that-shows-progress.md)
