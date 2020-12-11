---
title: 显示用于 ErrorProvider 组件的窗体验证的错误图标
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error icons
- ErrorProvider component [Windows Forms], displaying error icons
- error messages [Windows Forms], displaying icons
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
ms.openlocfilehash: a1e346e332db489351f59c9a0c03ae731baf3dc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970065"
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a>如何：使用 Windows 窗体 ErrorProvider 组件显示窗体验证的错误图标
<xref:System.Windows.Forms.ErrorProvider>用户输入无效数据时，可以使用 Windows 窗体组件来显示错误图标。 窗体上必须至少有两个控件，才能在它们之间进行 tab 键排列，从而调用验证代码。  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a>当控件的值无效时显示错误图标  
  
1. 向 Windows 窗体添加两个控件（例如文本框）。  
  
2. 将 <xref:System.Windows.Forms.ErrorProvider> 组件添加到窗体。  
  
3. 选择第一个控件并将代码添加到其 <xref:System.Windows.Forms.Control.Validating> 事件处理程序。 为了使此代码正常运行，该过程必须连接到事件。 有关详细信息，请参阅 [如何：在运行时为 Windows 窗体创建事件处理程序](../how-to-create-event-handlers-at-run-time-for-windows-forms.md)。  
  
     以下代码将测试用户输入的数据的有效性;如果数据无效，则 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> 调用方法。 方法的第一个参数 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> 指定要在其旁边显示图标的控件。 第二个参数是要显示的错误文本。  
  
    ```vb  
    Private Sub TextBox1_Validating(ByVal Sender As Object, _  
       ByVal e As System.ComponentModel.CancelEventArgs) Handles _  
       TextBox1.Validating  
          If Not IsNumeric(TextBox1.Text) Then  
             ErrorProvider1.SetError(TextBox1, "Not a numeric value.")  
          Else  
             ' Clear the error.  
             ErrorProvider1.SetError(TextBox1, "")  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void textBox1_Validating (object sender,  
       System.ComponentModel.CancelEventArgs e)  
    {  
       try  
       {  
          int x = Int32.Parse(textBox1.Text);  
          errorProvider1.SetError(textBox1, "");  
       }  
       catch (Exception ex)  
       {  
          errorProvider1.SetError(textBox1, "Not an integer value.");  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void textBox1_Validating(System::Object ^  sender,  
          System::ComponentModel::CancelEventArgs ^  e)  
       {  
          try  
          {  
             int x = Int32::Parse(textBox1->Text);  
             errorProvider1->SetError(textBox1, "");  
          }  
          catch (System::Exception ^ ex)  
          {  
             errorProvider1->SetError(textBox1, "Not an integer value.");  
          }  
       }  
    ```  
  
      (Visual c # 中，Visual C++) 将以下代码放在窗体构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4. 运行该项目。 在此示例中，键入无效的 (，将非数值) 数据导入第一个控件，然后按 tab 键到第二个控件。 显示错误图标时，用鼠标指针指向它，查看错误文本。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ErrorProvider.SetError%2A>
- [ErrorProvider 组件概述](errorprovider-component-overview-windows-forms.md)
- [如何：使用 Windows 窗体 ErrorProvider 组件查看数据集中的错误](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
