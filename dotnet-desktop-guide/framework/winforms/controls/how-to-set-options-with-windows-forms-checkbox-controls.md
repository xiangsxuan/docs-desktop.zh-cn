---
title: 使用 CheckBox 控件设置选项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- checked
helpviewer_keywords:
- CheckBox control [Windows Forms], checked state
- check boxes [Windows Forms], using to set options
- CheckBox control [Windows Forms], using to set options
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
ms.openlocfilehash: 00b467836d8e60aeee51a010a6384abf7dd73c56
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971121"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a><span data-ttu-id="9a458-102">如何：使用 Windows 窗体 CheckBox 控件设置选项</span><span class="sxs-lookup"><span data-stu-id="9a458-102">How to: Set Options with Windows Forms CheckBox Controls</span></span>
<span data-ttu-id="9a458-103">Windows 窗体 <xref:System.Windows.Forms.CheckBox> 控件用于向用户授予 True/False 或 Yes/No 选项。</span><span class="sxs-lookup"><span data-stu-id="9a458-103">A Windows Forms <xref:System.Windows.Forms.CheckBox> control is used to give users True/False or Yes/No options.</span></span> <span data-ttu-id="9a458-104">选中时，控件将显示复选标记。</span><span class="sxs-lookup"><span data-stu-id="9a458-104">The control displays a check mark when it is selected.</span></span>  
  
### <a name="to-set-options-with-checkbox-controls"></a><span data-ttu-id="9a458-105">用 CheckBox 控件设置选项</span><span class="sxs-lookup"><span data-stu-id="9a458-105">To set options with CheckBox controls</span></span>  
  
1. <span data-ttu-id="9a458-106">检查属性的值 <xref:System.Windows.Forms.CheckBox.Checked%2A> 以确定其状态，并使用该值来设置选项。</span><span class="sxs-lookup"><span data-stu-id="9a458-106">Examine the value of the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine its state, and use that value to set an option.</span></span>  
  
     <span data-ttu-id="9a458-107">在下面的代码示例中，当 <xref:System.Windows.Forms.CheckBox> 引发控件的 <xref:System.Windows.Forms.CheckBox.CheckedChanged> 事件时， <xref:System.Windows.Forms.Control.AllowDrop%2A> `false` 如果选中此复选框，窗体的属性将设置为。</span><span class="sxs-lookup"><span data-stu-id="9a458-107">In the code sample below, when the <xref:System.Windows.Forms.CheckBox> control's <xref:System.Windows.Forms.CheckBox.CheckedChanged> event is raised, the form's <xref:System.Windows.Forms.Control.AllowDrop%2A> property is set to `false` if the check box is checked.</span></span> <span data-ttu-id="9a458-108">这对于想要限制用户交互的情况非常有用。</span><span class="sxs-lookup"><span data-stu-id="9a458-108">This is useful for situations where you want to restrict user interaction.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_CheckedChanged(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles CheckBox1.CheckedChanged  
       ' Determine the CheckState of the check box.  
       If CheckBox1.CheckState = CheckState.Checked Then  
          ' If checked, do not allow items to be dragged onto the form.  
          Me.AllowDrop = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_CheckedChanged(object sender, System.EventArgs e)  
    {  
       // Determine the CheckState of the check box.  
       if (checkBox1.CheckState == CheckState.Checked)
       {  
          // If checked, do not allow items to be dragged onto the form.  
          this.AllowDrop = false;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Determine the CheckState of the check box.  
          if (checkBox1->CheckState == CheckState::Checked)
          {  
             // If checked, do not allow items to be dragged onto the form.  
             this->AllowDrop = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9a458-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a458-109">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="9a458-110">CheckBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="9a458-110">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="9a458-111">如何：响应 Windows 窗体 CheckBox 的单击</span><span class="sxs-lookup"><span data-stu-id="9a458-111">How to: Respond to Windows Forms CheckBox Clicks</span></span>](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [<span data-ttu-id="9a458-112">CheckBox 控件</span><span class="sxs-lookup"><span data-stu-id="9a458-112">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
