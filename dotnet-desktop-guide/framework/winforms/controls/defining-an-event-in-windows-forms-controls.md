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
# <a name="defining-an-event-in-windows-forms-controls"></a>在 Windows 窗体控件中定义事件

有关定义自定义事件的详细信息，请参阅 [事件](/dotnet/standard/events/index)。 如果你定义的事件没有任何关联的数据，则使用事件数据的基类型 <xref:System.EventArgs>，并使用 <xref:System.EventHandler> 作为事件委托。 剩下的工作就是定义一个事件成员和一个引发该事件的受保护的事件 `On` *名称* 方法。  
  
 以下代码段显示了 `FlashTrackBar` 自定义控件如何定义自定义事件 `ValueChanged`。 有关该示例的完整代码 `FlashTrackBar` ，请参阅 [如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)。  
  
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
  
## <a name="see-also"></a>另请参阅

- [Windows 窗体控件中的事件](events-in-windows-forms-controls.md)
- [事件](/dotnet/standard/events/index)
