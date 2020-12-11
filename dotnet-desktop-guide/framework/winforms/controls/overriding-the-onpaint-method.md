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
# <a name="overriding-the-onpaint-method"></a><span data-ttu-id="3e3c1-102">重写 OnPaint 方法</span><span class="sxs-lookup"><span data-stu-id="3e3c1-102">Overriding the OnPaint Method</span></span>

<span data-ttu-id="3e3c1-103">重写 .NET Framework 中定义的任何事件的基本步骤都是相同的，并且在以下列表中进行了总结。</span><span class="sxs-lookup"><span data-stu-id="3e3c1-103">The basic steps for overriding any event defined in the .NET Framework are identical and are summarized in the following list.</span></span>  
  
#### <a name="to-override-an-inherited-event"></a><span data-ttu-id="3e3c1-104">重写继承的事件</span><span class="sxs-lookup"><span data-stu-id="3e3c1-104">To override an inherited event</span></span>  
  
1. <span data-ttu-id="3e3c1-105">重写受保护的 `On` *事件名称* 方法。</span><span class="sxs-lookup"><span data-stu-id="3e3c1-105">Override the protected `On`*EventName* method.</span></span>  
  
2. <span data-ttu-id="3e3c1-106">`On`从重写的事件名称方法调用基类的 *事件名称* 方法 `On`  ，以便注册的委托接收事件。</span><span class="sxs-lookup"><span data-stu-id="3e3c1-106">Call the `On`*EventName* method of the base class from the overridden `On`*EventName* method, so that registered delegates receive the event.</span></span>  
  
 <span data-ttu-id="3e3c1-107"><xref:System.Windows.Forms.Control.Paint>此处详细讨论了该事件，因为每个 Windows 窗体控件必须重写 <xref:System.Windows.Forms.Control.Paint> 它所继承的事件 <xref:System.Windows.Forms.Control> 。</span><span class="sxs-lookup"><span data-stu-id="3e3c1-107">The <xref:System.Windows.Forms.Control.Paint> event is discussed in detail here because every Windows Forms control must override the <xref:System.Windows.Forms.Control.Paint> event that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="3e3c1-108">基类不 <xref:System.Windows.Forms.Control> 知道派生的控件需要如何绘制，并且不会在方法中提供任何绘图逻辑 <xref:System.Windows.Forms.Control.OnPaint%2A> 。</span><span class="sxs-lookup"><span data-stu-id="3e3c1-108">The base <xref:System.Windows.Forms.Control> class does not know how a derived control needs to be drawn and does not provide any painting logic in the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="3e3c1-109"><xref:System.Windows.Forms.Control.OnPaint%2A>方法 <xref:System.Windows.Forms.Control> 只是将事件调度 <xref:System.Windows.Forms.Control.Paint> 到已注册的事件接收器。</span><span class="sxs-lookup"><span data-stu-id="3e3c1-109">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of <xref:System.Windows.Forms.Control> simply dispatches the <xref:System.Windows.Forms.Control.Paint> event to registered event receivers.</span></span>  
  
 <span data-ttu-id="3e3c1-110">如果您在 [如何：开发简单的 Windows 窗体控件](how-to-develop-a-simple-windows-forms-control.md)中演练了示例，您已经看到了一个重写方法的示例 <xref:System.Windows.Forms.Control.OnPaint%2A> 。</span><span class="sxs-lookup"><span data-stu-id="3e3c1-110">If you worked through the sample in [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md), you have seen an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="3e3c1-111">以下代码片段取自该示例。</span><span class="sxs-lookup"><span data-stu-id="3e3c1-111">The following code fragment is taken from that sample.</span></span>  
  
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
  
 <span data-ttu-id="3e3c1-112"><xref:System.Windows.Forms.PaintEventArgs>类包含事件的数据 <xref:System.Windows.Forms.Control.Paint> 。</span><span class="sxs-lookup"><span data-stu-id="3e3c1-112">The <xref:System.Windows.Forms.PaintEventArgs> class contains data for the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="3e3c1-113">它有两个属性，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="3e3c1-113">It has two properties, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="3e3c1-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 要绘制的矩形， <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> 属性引用 <xref:System.Drawing.Graphics> 对象。</span><span class="sxs-lookup"><span data-stu-id="3e3c1-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is the rectangle to be painted, and the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property refers to a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="3e3c1-115">命名空间中的类 <xref:System.Drawing?displayProperty=nameWithType> 是托管类，它们提供对 GDI + （新的 Windows 图形库）功能的访问。</span><span class="sxs-lookup"><span data-stu-id="3e3c1-115">The classes in the <xref:System.Drawing?displayProperty=nameWithType> namespace are managed classes that provide access to the functionality of GDI+, the new Windows graphics library.</span></span> <span data-ttu-id="3e3c1-116"><xref:System.Drawing.Graphics>对象具有一些方法，用于绘制点、字符串、线条、弧形、省略号和许多其他形状。</span><span class="sxs-lookup"><span data-stu-id="3e3c1-116">The <xref:System.Drawing.Graphics> object has methods to draw points, strings, lines, arcs, ellipses, and many other shapes.</span></span>  
  
 <span data-ttu-id="3e3c1-117"><xref:System.Windows.Forms.Control.OnPaint%2A>每当控件需要更改其视觉显示时，它都会调用其方法。</span><span class="sxs-lookup"><span data-stu-id="3e3c1-117">A control invokes its <xref:System.Windows.Forms.Control.OnPaint%2A> method whenever it needs to change its visual display.</span></span> <span data-ttu-id="3e3c1-118">此方法反过来引发 <xref:System.Windows.Forms.Control.Paint> 事件。</span><span class="sxs-lookup"><span data-stu-id="3e3c1-118">This method in turn raises the <xref:System.Windows.Forms.Control.Paint> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e3c1-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e3c1-119">See also</span></span>

- [<span data-ttu-id="3e3c1-120">事件</span><span class="sxs-lookup"><span data-stu-id="3e3c1-120">Events</span></span>](/dotnet/standard/events/index)
- [<span data-ttu-id="3e3c1-121">呈现 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="3e3c1-121">Rendering a Windows Forms Control</span></span>](rendering-a-windows-forms-control.md)
- [<span data-ttu-id="3e3c1-122">定义事件</span><span class="sxs-lookup"><span data-stu-id="3e3c1-122">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
