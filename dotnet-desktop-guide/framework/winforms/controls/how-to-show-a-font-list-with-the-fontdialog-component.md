---
title: 如何：使用 FontDialog 组件显示字体列表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- fonts [Windows Forms], showing list
- FontDialog component [Windows Forms]
- fonts [Windows Forms], attributes
- Font property [Windows Forms], setting with FontDialog component
- Font dialog box [Windows Forms], displaying
- fonts [Windows Forms], selecting
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
ms.openlocfilehash: 05e9b5e1280d0318354b0d47f4d78f7ec1c5f4e7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972650"
---
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a><span data-ttu-id="ca3f2-102">如何：使用 FontDialog 组件显示字体列表</span><span class="sxs-lookup"><span data-stu-id="ca3f2-102">How to: Show a Font List with the FontDialog Component</span></span>
<span data-ttu-id="ca3f2-103">使用 [FontDialog](fontdialog-component-windows-forms.md) 组件，用户可以选择字体，还可以更改其显示的方位，如粗细和大小。</span><span class="sxs-lookup"><span data-stu-id="ca3f2-103">The [FontDialog](fontdialog-component-windows-forms.md) component allows users to select a font, as well as change its display aspects, such as its weight and size.</span></span>  
  
 <span data-ttu-id="ca3f2-104">对话框中选择的字体将在属性中返回 <xref:System.Windows.Forms.FontDialog.Font%2A> 。</span><span class="sxs-lookup"><span data-stu-id="ca3f2-104">The font selected in the dialog box is returned in the <xref:System.Windows.Forms.FontDialog.Font%2A> property.</span></span> <span data-ttu-id="ca3f2-105">因此，利用用户选择的字体与读取属性一样简单。</span><span class="sxs-lookup"><span data-stu-id="ca3f2-105">Thus, taking advantage of the font selected by the user is as easy as reading a property.</span></span>  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a><span data-ttu-id="ca3f2-106">使用 FontDialog 组件选择字体属性</span><span class="sxs-lookup"><span data-stu-id="ca3f2-106">To select font properties using the FontDialog Component</span></span>  
  
1. <span data-ttu-id="ca3f2-107">使用方法显示对话框 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 。</span><span class="sxs-lookup"><span data-stu-id="ca3f2-107">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2. <span data-ttu-id="ca3f2-108">使用 <xref:System.Windows.Forms.DialogResult> 属性可确定对话框的关闭方式。</span><span class="sxs-lookup"><span data-stu-id="ca3f2-108">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3. <span data-ttu-id="ca3f2-109">使用 " <xref:System.Windows.Forms.FontDialog.Font%2A> 属性" 设置所需的字体。</span><span class="sxs-lookup"><span data-stu-id="ca3f2-109">Use the <xref:System.Windows.Forms.FontDialog.Font%2A> property to set the desired font.</span></span>  
  
     <span data-ttu-id="ca3f2-110">在下面的示例中， <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Click> 事件处理程序将打开一个 <xref:System.Windows.Forms.FontDialog> 组件。</span><span class="sxs-lookup"><span data-stu-id="ca3f2-110">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="ca3f2-111">如果选择字体，并且用户单击 **"确定"**， <xref:System.Windows.Forms.FontDialog.Font%2A> <xref:System.Windows.Forms.TextBox> 则窗体上的控件的属性将设置为所选字体。</span><span class="sxs-lookup"><span data-stu-id="ca3f2-111">When a font is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.FontDialog.Font%2A> property of a <xref:System.Windows.Forms.TextBox> control that is on the form is set to the chosen font.</span></span> <span data-ttu-id="ca3f2-112">该示例假设窗体具有一个 <xref:System.Windows.Forms.Button> 控件、一个  <xref:System.Windows.Forms.TextBox> 控件和一个 <xref:System.Windows.Forms.FontDialog> 组件。</span><span class="sxs-lookup"><span data-stu-id="ca3f2-112">The example assumes your form has a <xref:System.Windows.Forms.Button> control, a  <xref:System.Windows.Forms.TextBox> control, and a <xref:System.Windows.Forms.FontDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
     <span data-ttu-id="ca3f2-113"> (Visual c # 和 Visual C++) 将以下代码放在窗体构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ca3f2-113">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ca3f2-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca3f2-114">See also</span></span>

- <xref:System.Windows.Forms.FontDialog>
- [<span data-ttu-id="ca3f2-115">FontDialog 组件</span><span class="sxs-lookup"><span data-stu-id="ca3f2-115">FontDialog Component</span></span>](fontdialog-component-windows-forms.md)
