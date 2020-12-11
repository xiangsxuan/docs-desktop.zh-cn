---
title: 演练：使用 MaskedTextBox 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
ms.openlocfilehash: db32b3ec88a07747ea3e286af9f04edce3f1ba3b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972489"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a>演练：使用 MaskedTextBox 控件
本演练涉及以下任务：  
  
- 初始化 <xref:System.Windows.Forms.MaskedTextBox> 控件  
  
- 使用 <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> 事件处理程序在字符不符合掩码时向用户发出警报  
  
- 将类型分配给 <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 属性，并使用 <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> 事件处理程序在尝试提交的值对类型无效时向用户发出警报  
  
## <a name="creating-the-project-and-adding-a-control"></a>创建项目并添加控件  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a>向窗体中添加 MaskedTextBox 控件  
  
1. 打开要在其上放置控件的窗体 <xref:System.Windows.Forms.MaskedTextBox> 。  
  
2. 将 <xref:System.Windows.Forms.MaskedTextBox> 控件从 **工具箱** 拖到窗体上。  
  
3. 右键单击控件，然后选择 " **属性**"。 在 " **属性** " 窗口中，选择 " **Mask** " 属性，然后单击属性名称旁边的 " **...** (省略号) " 按钮。  
  
4. 在 " **输入掩码** " 对话框中，选择 **短日期** 掩码，并单击 **"确定"**。  
  
5. 在 " **属性** " 窗口中，将 <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> 属性设置为 `true` 。 每次用户尝试输入违反掩码定义的字符时，此属性会导致短提示音。  
  
 有关 Mask 属性支持的字符摘要，请参阅属性的 "备注" 部分 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 。  
  
## <a name="alert-the-user-to-input-errors"></a>提醒用户输入错误  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a>为拒绝的掩码输入添加气球提示  
  
1. 返回到 " **工具箱** "，并将添加 <xref:System.Windows.Forms.ToolTip> 到窗体。  
  
2. 为 <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> 引发输入错误时引发的事件创建事件处理程序 <xref:System.Windows.Forms.ToolTip> 。 气球状提示在5秒内保持可见，或在用户单击它之前显示。  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a>向用户通知无效类型  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a>为无效数据类型添加气球状提示  
  
1. 在窗体的 <xref:System.Windows.Forms.Form.Load> 事件处理程序中，将 <xref:System.Type> 表示类型的对象分配 <xref:System.DateTime> 给 <xref:System.Windows.Forms.MaskedTextBox> 控件的 <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 属性：  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2. 为 <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> 事件添加事件处理程序：  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.MaskedTextBox>
- [MaskedTextBox 控件](maskedtextbox-control-windows-forms.md)
