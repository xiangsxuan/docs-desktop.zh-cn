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
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a><span data-ttu-id="9df37-102">如何：将 Windows 窗体按钮指定为“取消”按钮</span><span class="sxs-lookup"><span data-stu-id="9df37-102">How to: Designate a Windows Forms Button as the Cancel Button</span></span>
<span data-ttu-id="9df37-103">在任何 Windows 窗体上，都可以将 <xref:System.Windows.Forms.Button> 控件指定为 "取消" 按钮。</span><span class="sxs-lookup"><span data-stu-id="9df37-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="9df37-104">用户按 ESC 键时单击 "取消" 按钮，而不考虑窗体上的其他哪个控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="9df37-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="9df37-105">通常对此类按钮进行编程，使用户能够快速退出操作，而无需提交任何操作。</span><span class="sxs-lookup"><span data-stu-id="9df37-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="9df37-106">指定 "取消" 按钮</span><span class="sxs-lookup"><span data-stu-id="9df37-106">To designate the cancel button</span></span>  
  
1. <span data-ttu-id="9df37-107">将窗体的 <xref:System.Windows.Forms.Form.CancelButton%2A> 属性设置为相应的 <xref:System.Windows.Forms.Button> 控件。</span><span class="sxs-lookup"><span data-stu-id="9df37-107">Set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9df37-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9df37-108">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="9df37-109">Button 控件概述</span><span class="sxs-lookup"><span data-stu-id="9df37-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="9df37-110">选择 Windows 窗体 Button 控件的方法</span><span class="sxs-lookup"><span data-stu-id="9df37-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="9df37-111">如何：响应 Windows 窗体按钮的单击</span><span class="sxs-lookup"><span data-stu-id="9df37-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="9df37-112">如何：将 Windows 窗体按钮指定为“接受”按钮</span><span class="sxs-lookup"><span data-stu-id="9df37-112">How to: Designate a Windows Forms Button as the Accept Button</span></span>](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [<span data-ttu-id="9df37-113">Button 控件</span><span class="sxs-lookup"><span data-stu-id="9df37-113">Button Control</span></span>](button-control-windows-forms.md)
