---
title: 重写 OnPaint 方法
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Paint event [Windows Forms], handling in Windows Forms custom control
- OnPaint method [Windows Forms], overriding in Windows Forms custom controls
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
ms.openlocfilehash: 140c3e880300f8b1428dd23d946f25d095189fb3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972602"
---
# <a name="overriding-the-onpaint-method"></a>重写 OnPaint 方法

重写 .NET Framework 中定义的任何事件的基本步骤都是相同的，并且在以下列表中进行了总结。  
  
#### <a name="to-override-an-inherited-event"></a>重写继承的事件  
  
1. 重写受保护的 `On` *事件名称* 方法。  
  
2. `On`从重写的事件名称方法调用基类的 *事件名称* 方法 `On`  ，以便注册的委托接收事件。  
  
 <xref:System.Windows.Forms.Control.Paint>此处详细讨论了该事件，因为每个 Windows 窗体控件必须重写 <xref:System.Windows.Forms.Control.Paint> 它所继承的事件 <xref:System.Windows.Forms.Control> 。 基类不 <xref:System.Windows.Forms.Control> 知道派生的控件需要如何绘制，并且不会在方法中提供任何绘图逻辑 <xref:System.Windows.Forms.Control.OnPaint%2A> 。 <xref:System.Windows.Forms.Control.OnPaint%2A>方法 <xref:System.Windows.Forms.Control> 只是将事件调度 <xref:System.Windows.Forms.Control.Paint> 到已注册的事件接收器。  
  
 如果您在 [如何：开发简单的 Windows 窗体控件](how-to-develop-a-simple-windows-forms-control.md)中演练了示例，您已经看到了一个重写方法的示例 <xref:System.Windows.Forms.Control.OnPaint%2A> 。 以下代码片段取自该示例。  
  
```vb  
Public Class FirstControl  
   Inherits Control  
  
   Public Sub New()  
   End Sub  
  
   Protected Overrides Sub OnPaint(e As PaintEventArgs)  
      ' Call the OnPaint method of the base class.  
      MyBase.OnPaint(e)  
      ' Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, New SolidBrush(ForeColor), RectangleF.op_Implicit(ClientRectangle))  
   End Sub  
End Class
```  
  
```csharp  
public class FirstControl : Control {  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }
}
```  
  
 <xref:System.Windows.Forms.PaintEventArgs>类包含事件的数据 <xref:System.Windows.Forms.Control.Paint> 。 它有两个属性，如下面的代码所示。  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   ...  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs {  
...  
    public System.Drawing.Rectangle ClipRectangle {}  
    public System.Drawing.Graphics Graphics {}  
...  
}  
```  
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 要绘制的矩形， <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> 属性引用 <xref:System.Drawing.Graphics> 对象。 命名空间中的类 <xref:System.Drawing?displayProperty=nameWithType> 是托管类，它们提供对 GDI + （新的 Windows 图形库）功能的访问。 <xref:System.Drawing.Graphics>对象具有一些方法，用于绘制点、字符串、线条、弧形、省略号和许多其他形状。  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>每当控件需要更改其视觉显示时，它都会调用其方法。 此方法反过来引发 <xref:System.Windows.Forms.Control.Paint> 事件。  
  
## <a name="see-also"></a>请参阅

- [事件](/dotnet/standard/events/index)
- [呈现 Windows 窗体控件](rendering-a-windows-forms-control.md)
- [定义事件](defining-an-event-in-windows-forms-controls.md)
