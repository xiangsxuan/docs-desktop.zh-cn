---
title: 将某个按钮指定为 "取消" 按钮
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 123b3e275065efadd24815320ea7d855808e60b9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971849"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a>如何：将 Windows 窗体按钮指定为“取消”按钮
在任何 Windows 窗体上，都可以将 <xref:System.Windows.Forms.Button> 控件指定为 "取消" 按钮。 用户按 ESC 键时单击 "取消" 按钮，而不考虑窗体上的其他哪个控件具有焦点。 通常对此类按钮进行编程，使用户能够快速退出操作，而无需提交任何操作。  
  
### <a name="to-designate-the-cancel-button"></a>指定 "取消" 按钮  
  
1. 将窗体的 <xref:System.Windows.Forms.Form.CancelButton%2A> 属性设置为相应的 <xref:System.Windows.Forms.Button> 控件。  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Button 控件概述](button-control-overview-windows-forms.md)
- [选择 Windows 窗体 Button 控件的方法](ways-to-select-a-windows-forms-button-control.md)
- [如何：响应 Windows 窗体按钮的单击](how-to-respond-to-windows-forms-button-clicks.md)
- [如何：将 Windows 窗体按钮指定为“接受”按钮](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [Button 控件](button-control-windows-forms.md)
