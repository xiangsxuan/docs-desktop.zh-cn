---
title: 事件处理程序概述
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
ms.openlocfilehash: ec8bc23ce8aba36ad456114ec645d4f0799f107f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971728"
---
# <a name="event-handlers-overview-windows-forms"></a>事件处理程序概述（Windows 窗体）
事件处理程序是绑定到事件的方法。 引发事件时，将执行事件处理程序中的代码。 每个事件处理程序提供了两个参数，可用于正确处理事件。 下面的示例演示控件事件的事件处理程序 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Click> 。  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)
{  
  
}  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 第一个参数 `sender` 提供对引发事件的对象的引用。 `e`在上面的示例中，第二个参数传递特定于正在处理的事件的对象。 通过引用对象的属性 (，有时，它的方法) ，你可以获取诸如鼠标事件或拖放事件中正在传输的数据的鼠标位置等信息。  
  
 通常，每个事件都为第二个参数生成一个具有不同事件对象类型的事件处理程序。 某些事件处理程序（例如和事件的）的 <xref:System.Windows.Forms.Control.MouseDown> <xref:System.Windows.Forms.Control.MouseUp> 第二个参数具有相同的对象类型。 对于这些类型的事件，可以使用同一事件处理程序来处理这两个事件。  
  
 你还可以使用同一事件处理程序来处理不同控件的同一事件。 例如，如果窗体上有一组 <xref:System.Windows.Forms.RadioButton> 控件，则可以为事件创建一个事件处理程序，并将 <xref:System.Windows.Forms.Control.Click> 每个控件的 <xref:System.Windows.Forms.Control.Click> 事件绑定到单个事件处理程序。 有关详细信息，请参阅 [如何：将多个事件连接到 Windows 窗体中的单个事件处理程序](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)。  
  
## <a name="see-also"></a>另请参阅

- [在 Windows 窗体中创建事件处理程序](creating-event-handlers-in-windows-forms.md)
- [事件概述](events-overview-windows-forms.md)
