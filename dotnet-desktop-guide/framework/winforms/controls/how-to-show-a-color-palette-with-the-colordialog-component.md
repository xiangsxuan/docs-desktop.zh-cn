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
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a><span data-ttu-id="f5895-102">如何：使用 ColorDialog 组件显示调色板</span><span class="sxs-lookup"><span data-stu-id="f5895-102">How to: Show a Color Palette with the ColorDialog Component</span></span>
<span data-ttu-id="f5895-103">[ColorDialog](colordialog-component-windows-forms.md)组件显示颜色调色板，并返回一个属性，其中包含用户选定的颜色。</span><span class="sxs-lookup"><span data-stu-id="f5895-103">The [ColorDialog](colordialog-component-windows-forms.md) component displays a palette of colors and returns a property containing the color the user has selected.</span></span>  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a><span data-ttu-id="f5895-104">使用 ColorDialog 组件选择颜色</span><span class="sxs-lookup"><span data-stu-id="f5895-104">To choose a color using the ColorDialog component</span></span>  
  
1. <span data-ttu-id="f5895-105">使用方法显示对话框 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 。</span><span class="sxs-lookup"><span data-stu-id="f5895-105">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2. <span data-ttu-id="f5895-106">使用 <xref:System.Windows.Forms.DialogResult> 属性可确定对话框的关闭方式。</span><span class="sxs-lookup"><span data-stu-id="f5895-106">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3. <span data-ttu-id="f5895-107">使用 <xref:System.Windows.Forms.ColorDialog.Color%2A> 组件的属性 <xref:System.Windows.Forms.ColorDialog> 设置所选的颜色。</span><span class="sxs-lookup"><span data-stu-id="f5895-107">Use the <xref:System.Windows.Forms.ColorDialog.Color%2A> property of the <xref:System.Windows.Forms.ColorDialog> component to set the chosen color.</span></span>  
  
     <span data-ttu-id="f5895-108">在下面的示例中， <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Click> 事件处理程序将打开一个 <xref:System.Windows.Forms.ColorDialog> 组件。</span><span class="sxs-lookup"><span data-stu-id="f5895-108">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="f5895-109">选择颜色后，用户单击 **"确定"** 时，该 <xref:System.Windows.Forms.Button> 控件的背景色将设置为所选颜色。</span><span class="sxs-lookup"><span data-stu-id="f5895-109">When a color is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.Button> control's background color is set to the chosen color.</span></span> <span data-ttu-id="f5895-110">该示例假设窗体具有一个 <xref:System.Windows.Forms.Button> 控件和一个 <xref:System.Windows.Forms.ColorDialog> 组件。</span><span class="sxs-lookup"><span data-stu-id="f5895-110">The example assumes your form has a <xref:System.Windows.Forms.Button> control and a <xref:System.Windows.Forms.ColorDialog> component.</span></span>  
  
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
  
     <span data-ttu-id="f5895-111"> (Visual c # 中，Visual C++) 将以下代码放在窗体构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="f5895-111">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f5895-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5895-112">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="f5895-113">ColorDialog 组件</span><span class="sxs-lookup"><span data-stu-id="f5895-113">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
