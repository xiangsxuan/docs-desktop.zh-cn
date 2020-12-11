---
title: 如何：将数据发送到活动的 MDI 子窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms
- MDI [Windows Forms], sending data to forms
- Clipboard [Windows Forms], pasting
- Clipboard [Windows Forms], getting data from
ms.assetid: 1047d2fe-1235-46db-aad9-563aea1d743b
ms.openlocfilehash: 563be8494cb84dc74b45985d3ba74e4b6a07eb8a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971666"
---
# <a name="how-to-send-data-to-the-active-mdi-child"></a><span data-ttu-id="68327-102">如何：将数据发送到活动的 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="68327-102">How to: Send Data to the Active MDI Child</span></span>
<span data-ttu-id="68327-103">通常，在 [多文档界面 (MDI) 应用程序](multiple-document-interface-mdi-applications.md)的上下文中，需要将数据发送到活动子窗口，例如当用户将剪贴板中的数据粘贴到 MDI 应用程序中时。</span><span class="sxs-lookup"><span data-stu-id="68327-103">Often, within the context of [Multiple-Document Interface (MDI) Applications](multiple-document-interface-mdi-applications.md), you will need to send data to the active child window, such as when the user pastes data from the Clipboard into an MDI application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68327-104">有关验证哪个子窗口有焦点并发送到剪贴板的内容的信息，请参阅 [确定活动的 MDI 子](how-to-determine-the-active-mdi-child.md)窗口。</span><span class="sxs-lookup"><span data-stu-id="68327-104">For information about verifying which child window has focus and sending its contents to the Clipboard, see [Determining the Active MDI Child](how-to-determine-the-active-mdi-child.md).</span></span>  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a><span data-ttu-id="68327-105">从剪贴板将数据发送到活动的 MDI 子窗口</span><span class="sxs-lookup"><span data-stu-id="68327-105">To send data to the active MDI child window from the Clipboard</span></span>  
  
1. <span data-ttu-id="68327-106">在方法中，将剪贴板上的文本复制到活动子窗体的活动控件。</span><span class="sxs-lookup"><span data-stu-id="68327-106">Within a method, copy the text on the Clipboard to the active control of the active child form.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="68327-107">此示例假设有一个 MDI 父窗体 (`Form1`) 包含一个或多个包含控件的 MDI 子窗口 <xref:System.Windows.Forms.RichTextBox> 。</span><span class="sxs-lookup"><span data-stu-id="68327-107">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="68327-108">有关详细信息，请参阅 [创建 MDI 父窗体](how-to-create-mdi-parent-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="68327-108">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
    ```vb  
    Public Sub mniPaste_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniPaste.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ParentForm.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Try  
             Dim theBox As RichTextBox = Ctype(activeChild.ActiveControl, RichTextBox)  
             If (Not theBox Is Nothing) Then  
                ' Create a new instance of the DataObject interface.  
                Dim data As IDataObject = Clipboard.GetDataObject()  
                ' If the data is text, then set the text of the
                ' RichTextBox to the text in the clipboard.  
                If (data.GetDataPresent(DataFormats.Text)) Then  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString()  
                End If  
             End If  
          Catch  
             MessageBox.Show("You need to select a RichTextBox.")  
          End Try  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniPaste_Click (object sender, System.EventArgs e)  
    {  
      // Determine the active child form.  
       Form activeChild = this.ParentForm.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {  
          try
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Create a new instance of the DataObject interface.  
                IDataObject data = Clipboard.GetDataObject();  
                // If the data is text, then set the text of the
                // RichTextBox to the text in the clipboard.  
                if (data.GetDataPresent(DataFormats.Text))  
                {  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString();
                }  
             }  
          }  
          catch
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="68327-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68327-109">See also</span></span>

- [<span data-ttu-id="68327-110">多文档界面 (MDI) 应用程序</span><span class="sxs-lookup"><span data-stu-id="68327-110">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="68327-111">如何：创建 MDI 父窗体</span><span class="sxs-lookup"><span data-stu-id="68327-111">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="68327-112">如何：创建 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="68327-112">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="68327-113">如何：确定活动的 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="68327-113">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="68327-114">如何：排列 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="68327-114">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
