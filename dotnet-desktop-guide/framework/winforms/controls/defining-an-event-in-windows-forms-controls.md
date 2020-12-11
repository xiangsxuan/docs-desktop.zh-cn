---
title: 定义控件中的事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- events [Windows Forms], defining within Windows Forms custom controls
- custom controls [Windows Forms], events using code
ms.assetid: d89f1096-8061-42e2-a855-a1f053f1940a
ms.openlocfilehash: fabffc02ecf921eed428ec1ec452aa60c77b5987
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970098"
---
# <a name="defining-an-event-in-windows-forms-controls"></a><span data-ttu-id="29c29-102">在 Windows 窗体控件中定义事件</span><span class="sxs-lookup"><span data-stu-id="29c29-102">Defining an Event in Windows Forms Controls</span></span>

<span data-ttu-id="29c29-103">有关定义自定义事件的详细信息，请参阅 [事件](/dotnet/standard/events/index)。</span><span class="sxs-lookup"><span data-stu-id="29c29-103">For details about defining custom events, see [Events](/dotnet/standard/events/index).</span></span> <span data-ttu-id="29c29-104">如果你定义的事件没有任何关联的数据，则使用事件数据的基类型 <xref:System.EventArgs>，并使用 <xref:System.EventHandler> 作为事件委托。</span><span class="sxs-lookup"><span data-stu-id="29c29-104">If you define an event that does not have any associated data, use the base type for event data, <xref:System.EventArgs>, and use <xref:System.EventHandler> as the event delegate.</span></span> <span data-ttu-id="29c29-105">剩下的工作就是定义一个事件成员和一个引发该事件的受保护的事件 `On` *名称* 方法。</span><span class="sxs-lookup"><span data-stu-id="29c29-105">All that remains to do is to define an event member and a protected `On`*EventName* method that raises the event.</span></span>  
  
 <span data-ttu-id="29c29-106">以下代码段显示了 `FlashTrackBar` 自定义控件如何定义自定义事件 `ValueChanged`。</span><span class="sxs-lookup"><span data-stu-id="29c29-106">The following code fragment shows how the `FlashTrackBar` custom control defines a custom event, `ValueChanged`.</span></span> <span data-ttu-id="29c29-107">有关该示例的完整代码 `FlashTrackBar` ，请参阅 [如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)。</span><span class="sxs-lookup"><span data-stu-id="29c29-107">For the complete code for the `FlashTrackBar` sample, see the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
Imports System.Drawing  
  
Public Class FlashTrackBar  
   Inherits Control  
  
   ' The event does not have any data, so EventHandler is adequate
   ' as the event delegate.
   ' Define the event member using the event keyword.  
   ' In this case, for efficiency, the event is defined
   ' using the event property construct.  
   Public Event ValueChanged As EventHandler  
   ' The protected method that raises the ValueChanged
   ' event when the value has actually
   ' changed. Derived controls can override this method.
   Protected Overridable Sub OnValueChanged(e As EventArgs)  
      RaiseEvent ValueChanged(Me, e)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
using System.Drawing;  
  
public class FlashTrackBar : Control {  
   // The event does not have any data, so EventHandler is adequate
   // as the event delegate.  
   private EventHandler onValueChanged;  
   // Define the event member using the event keyword.  
   // In this case, for efficiency, the event is defined
   // using the event property construct.  
   public event EventHandler ValueChanged {  
            add {  
                onValueChanged += value;  
            }  
            remove {  
                onValueChanged -= value;  
            }  
        }  
   // The protected method that raises the ValueChanged  
   // event when the value has actually
   // changed. Derived controls can override this method.
   protected virtual void OnValueChanged(EventArgs e)
   {  
       onValueChanged?.Invoke(this, e);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="29c29-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29c29-108">See also</span></span>

- [<span data-ttu-id="29c29-109">Windows 窗体控件中的事件</span><span class="sxs-lookup"><span data-stu-id="29c29-109">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="29c29-110">事件</span><span class="sxs-lookup"><span data-stu-id="29c29-110">Events</span></span>](/dotnet/standard/events/index)
