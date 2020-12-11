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
# <a name="rendering-a-windows-forms-control"></a>呈现 Windows 窗体控件

呈现是指在用户屏幕上创建视觉对象表示形式的过程。 Windows 窗体使用 GDI (新的 Windows 图形库) 来呈现。 提供对 GDI 的访问的托管类位于 <xref:System.Drawing?displayProperty=nameWithType> 命名空间及其子命名空间中。  
  
 控件呈现涉及以下元素：  
  
- 基类提供的绘制功能 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 。  
  
- GDI 图形库的重要元素。  
  
- 绘图区域的几何。  
  
- 用于释放图形资源的过程。  
  
## <a name="drawing-functionality-provided-by-control"></a>控件提供的绘制功能  

 基类 <xref:System.Windows.Forms.Control> 通过其事件提供绘制功能 <xref:System.Windows.Forms.Control.Paint> 。 <xref:System.Windows.Forms.Control.Paint>每当控件需要更新其显示时，都会引发事件。 有关 .NET Framework 中事件的详细信息，请参阅 [处理和引发事件](/dotnet/standard/events/index)。  
  
 事件的事件数据类 <xref:System.Windows.Forms.Control.Paint> <xref:System.Windows.Forms.PaintEventArgs> 包含绘制控件所需的数据-图形对象的句柄和表示要在其中绘制的区域的矩形对象。 这些对象在以下代码片段中显示为粗体。  
  
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
  
 <xref:System.Drawing.Graphics> 是一个封装了绘制功能的托管类，如本主题后面的 GDI 讨论中所述。 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>是结构的实例 <xref:System.Drawing.Rectangle> ，用于定义可在其中绘制控件的可用区域。 控件开发人员可以 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 使用 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 控件的属性计算，如本主题后面的几何讨论中所述。  
  
 控件必须通过重写继承自的方法来提供呈现逻辑 <xref:System.Windows.Forms.Control.OnPaint%2A> <xref:System.Windows.Forms.Control> 。 <xref:System.Windows.Forms.Control.OnPaint%2A> 获取对图形对象的访问，以及通过 <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 传递给它的实例的属性在中绘制的矩形 <xref:System.Windows.Forms.PaintEventArgs> 。  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>基类的方法 <xref:System.Windows.Forms.Control> 不会实现任何绘制功能，而只会调用向事件注册的事件委托 <xref:System.Windows.Forms.Control.Paint> 。 重写时 <xref:System.Windows.Forms.Control.OnPaint%2A> ，通常应调用基类的 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法，以便注册的委托接收 <xref:System.Windows.Forms.Control.Paint> 事件。 但是，绘制整个图面的控件不应调用基类的 <xref:System.Windows.Forms.Control.OnPaint%2A> ，因为这会引入闪烁。 有关替代事件的示例 <xref:System.Windows.Forms.Control.OnPaint%2A> ，请参阅 [如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)。  
  
> [!NOTE]
> 不要 <xref:System.Windows.Forms.Control.OnPaint%2A> 直接从控件调用; 而是调用 <xref:System.Windows.Forms.Control.Invalidate%2A> (继承自) 的方法 <xref:System.Windows.Forms.Control> 或调用的其他方法 <xref:System.Windows.Forms.Control.Invalidate%2A> 。 <xref:System.Windows.Forms.Control.Invalidate%2A>方法又会调用 <xref:System.Windows.Forms.Control.OnPaint%2A> 。 <xref:System.Windows.Forms.Control.Invalidate%2A>重载方法时，控件会重 <xref:System.Windows.Forms.Control.Invalidate%2A> `e` 绘其部分或全部屏幕区域，具体取决于提供给的参数。  
  
 基类 <xref:System.Windows.Forms.Control> 定义可用于绘制的另一种方法，即 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 方法。  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 绘制背景 (，从而使窗口) 的形状，并保证其速度非常快，同时 <xref:System.Windows.Forms.Control.OnPaint%2A> 绘制详细信息并可能比较慢，因为单个绘制请求合并为一个 <xref:System.Windows.Forms.Control.Paint> 事件，该事件涵盖了所有需要重新绘制的区域。 例如， <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 如果想要绘制控件的渐变颜色背景，则可能需要调用。  
  
 虽然 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 具有类似事件的命名法并采用与方法相同的参数 `OnPaint` ，但并 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 不是真正的事件方法。 没有 `PaintBackground` 事件，并且不 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 调用事件委托。 重写 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 方法时，派生类不需要调用 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 其基类的方法。  
  
## <a name="gdi-basics"></a>GDI + 基础知识  

 <xref:System.Drawing.Graphics>类提供用于绘制各种形状（如圆、三角形、弧形和椭圆）的方法，以及用于显示文本的方法。 <xref:System.Drawing?displayProperty=nameWithType>命名空间及其子命名空间包含类，这些类封装图形元素，如形状 (圆形、矩形、弧形以及其他) 、颜色、字体、画笔等。 有关 GDI 的详细信息，请参阅 [使用托管图形类](../advanced/using-managed-graphics-classes.md)。 [如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)中还介绍了 GDI 的基本知识。  
  
## <a name="geometry-of-the-drawing-region"></a>绘图区域的几何图形  

 <xref:System.Windows.Forms.Control.ClientRectangle%2A>控件的属性指定可用于用户屏幕上的控件的矩形区域，而的 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 属性 <xref:System.Windows.Forms.PaintEventArgs> 指定实际绘制的区域。  (请记住，在将 <xref:System.Windows.Forms.Control.Paint> <xref:System.Windows.Forms.PaintEventArgs> 实例作为其参数) 的事件方法中完成了绘制。 控件可能只需要绘制部分可用区域，这种情况下，当控件的小部分显示更改时。 在这些情况下，控件开发人员必须计算要在其中进行绘制的实际矩形，并将其传递给 <xref:System.Windows.Forms.Control.Invalidate%2A> 。 <xref:System.Windows.Forms.Control.Invalidate%2A>采用或作为参数的的重载 <xref:System.Drawing.Rectangle> 版本 <xref:System.Drawing.Region> 使用该参数来生成的 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 属性 <xref:System.Windows.Forms.PaintEventArgs> 。  
  
 下面的代码段演示 `FlashTrackBar` 自定义控件如何计算要在中绘制的矩形区域。 `client`变量表示 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 属性。 有关完整示例，请参阅 [如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)。  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a>释放图形资源  

 图形对象开销高昂，因为它们使用系统资源。 此类对象包括类的实例 <xref:System.Drawing.Graphics?displayProperty=nameWithType> <xref:System.Drawing.Brush?displayProperty=nameWithType> ，以及、 <xref:System.Drawing.Pen?displayProperty=nameWithType> 和其他图形类的实例。 只有在需要图形资源并在使用完毕后立即将其释放，这一点非常重要。 如果创建实现接口的类型 <xref:System.IDisposable> ，请在完成该操作后调用其方法，以便 <xref:System.IDisposable.Dispose%2A> 释放资源。  
  
 下面的代码段演示 `FlashTrackBar` 自定义控件如何创建和释放 <xref:System.Drawing.Brush> 资源。 有关完整的源代码，请参阅 [如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)。  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a>另请参阅

- [如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)
