---
title: 用户描述的控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user-drawn
- OnPaint method [Windows Forms]
- user-drawn controls [Windows Forms]
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
ms.openlocfilehash: c68c8c88376cfe7295962264c466030115f2f3db
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973160"
---
# <a name="user-drawn-controls"></a>用户描述的控件
.NET Framework 使你能够轻松地开发自己的控件。 您可以创建一个用户控件，该控件是通过代码绑定在一起的一组标准控件，或者您可以从头开始设计自己的控件。 甚至可以使用继承来创建一个从现有控件继承的控件并将其添加到其固有的功能中。 无论使用哪种方法，.NET Framework 都提供了为您创建的任何控件绘制自定义图形界面的功能。  
  
 控件的绘制通过执行控件的方法中的代码来实现 <xref:System.Windows.Forms.Control.OnPaint%2A> 。 方法的单个参数 <xref:System.Windows.Forms.Control.OnPaint%2A> 是一个 <xref:System.Windows.Forms.PaintEventArgs> 对象，该对象提供了呈现控件所需的所有信息和功能。 <xref:System.Windows.Forms.PaintEventArgs>提供了两个将用于呈现控件的主体对象：  
  
- <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object-表示要绘制的控件部分的矩形。 这可以是整个控件或控件的一部分，具体取决于控件的绘制方式。  
  
- <xref:System.Drawing.Graphics> 对象-封装一些面向图形的对象和方法，这些对象和方法提供绘制控件所必需的功能。  
  
 有关 <xref:System.Drawing.Graphics> 对象以及如何使用它的详细信息，请参阅 [如何：为绘图创建图形对象](../advanced/how-to-create-graphics-objects-for-drawing.md)。  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>每当在屏幕上绘制或刷新控件时都会触发事件，而 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 对象表示在其中进行绘制的矩形。 如果需要刷新整个控件， <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 将表示整个控件的大小。 但是，如果只需要刷新部分控件，则 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 对象只表示需要重新绘制的区域。 此类情况的一个示例就是在用户界面中，控件被另一个控件或窗体部分遮盖。  
  
 从类继承时 <xref:System.Windows.Forms.Control> ，必须重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法，并在内提供图形呈现代码。 如果要为用户控件或继承的控件提供自定义图形界面，还可以通过重写方法来执行此操作 <xref:System.Windows.Forms.Control.OnPaint%2A> 。 下面显示了一个示例：  
  
```vb  
Protected Overrides Sub OnPaint(ByVal e As PaintEventArgs)  
   ' Call the OnPaint method of the base class.  
   MyBase.OnPaint(e)  
  
   ' Declare and instantiate a drawing pen.  
   Using myPen As System.Drawing.Pen = New System.Drawing.Pen(Color.Aqua)  
      ' Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, New Rectangle(Me.Location, Me.Size))  
   End Using
End Sub  
```  
  
```csharp  
protected override void OnPaint(PaintEventArgs e)  
{  
   // Call the OnPaint method of the base class.  
   base.OnPaint(e);  
  
   // Declare and instantiate a new pen.  
   using (System.Drawing.Pen myPen = new System.Drawing.Pen(Color.Aqua))  
   {
      // Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, new Rectangle(this.Location,
         this.Size));  
   }
}  
```  
  
 前面的示例演示如何使用非常简单的图形表示形式呈现控件。 它调用 <xref:System.Windows.Forms.Control.OnPaint%2A> 基类的方法，并创建用于 <xref:System.Drawing.Pen> 绘制的对象，最后在由控件的和确定的矩形中绘制一个椭圆 <xref:System.Windows.Forms.Control.Location%2A> <xref:System.Windows.Forms.Control.Size%2A> 。 尽管大多数呈现代码的复杂程度要大得多，但本示例演示了 <xref:System.Drawing.Graphics> 对象中包含的对象的用法 <xref:System.Windows.Forms.PaintEventArgs> 。 请注意，如果从已具有图形表示形式（如或）的类继承， <xref:System.Windows.Forms.UserControl> <xref:System.Windows.Forms.Button> 并且不希望将该表示形式合并到您的呈现中，则不应调用基类的 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法。  
  
 控件的方法中的代码 <xref:System.Windows.Forms.Control.OnPaint%2A> 将在第一次绘制控件时和每次刷新时执行。 若要确保每次调整控件大小时都重新绘制控件，请将以下行添加到控件的构造函数中：  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
> 使用 <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> 属性实现非矩形控件。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [如何：创建用于绘制的 Graphics 对象](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [构成控件](constituent-controls.md)
- [各种自定义控件](varieties-of-custom-controls.md)
