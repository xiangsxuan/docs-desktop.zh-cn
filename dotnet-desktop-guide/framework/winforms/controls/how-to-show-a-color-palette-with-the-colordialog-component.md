---
title: 如何：使用 ColorDialog 组件显示调色板
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- palettes [Windows Forms], showing color
- color dialog box [Windows Forms], showing color palettes
- colors [Windows Forms], allowing users to select
- color palettes [Windows Forms], dialog box
- ColorDialog component [Windows Forms], showing color palettes
- color palettes [Windows Forms], showing in ColorDialog component
- colors [Windows Forms], showing palettes
ms.assetid: ee050f61-dbc8-4436-ba22-51360981ab48
ms.openlocfilehash: 0406ef7a32678bd149c0024348a7adf1f0b72926
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972549"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a>如何：使用 ColorDialog 组件显示调色板
[ColorDialog](colordialog-component-windows-forms.md)组件显示颜色调色板，并返回一个属性，其中包含用户选定的颜色。  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a>使用 ColorDialog 组件选择颜色  
  
1. 使用方法显示对话框 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 。  
  
2. 使用 <xref:System.Windows.Forms.DialogResult> 属性可确定对话框的关闭方式。  
  
3. 使用 <xref:System.Windows.Forms.ColorDialog.Color%2A> 组件的属性 <xref:System.Windows.Forms.ColorDialog> 设置所选的颜色。  
  
     在下面的示例中， <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Click> 事件处理程序将打开一个 <xref:System.Windows.Forms.ColorDialog> 组件。 选择颜色后，用户单击 **"确定"** 时，该 <xref:System.Windows.Forms.Button> 控件的背景色将设置为所选颜色。 该示例假设窗体具有一个 <xref:System.Windows.Forms.Button> 控件和一个 <xref:System.Windows.Forms.ColorDialog> 组件。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       If ColorDialog1.ShowDialog() = DialogResult.OK Then  
          Button1.BackColor = ColorDialog1.Color  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(colorDialog1.ShowDialog() == DialogResult.OK)  
       {  
          button1.BackColor = colorDialog1.Color;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,
          System::EventArgs ^ e)  
       {  
          if(colorDialog1->ShowDialog() == DialogResult::OK)  
          {  
             button1->BackColor = colorDialog1->Color;  
          }  
       }  
    ```  
  
      (Visual c # 中，Visual C++) 将以下代码放在窗体构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ColorDialog>
- [ColorDialog 组件](colordialog-component-windows-forms.md)
