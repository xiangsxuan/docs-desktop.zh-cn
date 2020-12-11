---
title: 使用 RichTextBox 控件启用拖放操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- drag and drop [Windows Forms], richTextBox control
- text boxes [Windows Forms], drag-and-drop operations
- RichTextBox control [Windows Forms], drag-and-drop operations
ms.assetid: ca167d1c-2014-4cf0-96a0-20598470be3b
ms.openlocfilehash: 27e5c18598552c465ef17f5e58069bc10e401c09
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971318"
---
# <a name="how-to-enable-drag-and-drop-operations-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="cdb5b-102">如何：使用 Windows 窗体 RichTextBox 控件启用拖放操作</span><span class="sxs-lookup"><span data-stu-id="cdb5b-102">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="cdb5b-103">通过处理 <xref:System.Windows.Forms.RichTextBox> 和 <xref:System.Windows.Forms.RichTextBox.DragEnter> 事件，在 Windows 窗体 <xref:System.Windows.Forms.RichTextBox.DragDrop> 控件中进行拖放操作。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-103">Drag-and-drop operations with the Windows Forms <xref:System.Windows.Forms.RichTextBox> control are done by handling the <xref:System.Windows.Forms.RichTextBox.DragEnter> and <xref:System.Windows.Forms.RichTextBox.DragDrop> events.</span></span> <span data-ttu-id="cdb5b-104">因此，在 <xref:System.Windows.Forms.RichTextBox> 控件中进行拖放操作是非常简单的。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-104">Thus, drag-and-drop operations are extremely simple with the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
### <a name="to-enable-drag-operations-in-a-richtextbox-control"></a><span data-ttu-id="cdb5b-105">在 RichTextBox 控件中实现拖动操作</span><span class="sxs-lookup"><span data-stu-id="cdb5b-105">To enable drag operations in a RichTextBox control</span></span>  
  
1. <span data-ttu-id="cdb5b-106">将 <xref:System.Windows.Forms.RichTextBox.AllowDrop%2A> 控件的 <xref:System.Windows.Forms.RichTextBox> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-106">Set the <xref:System.Windows.Forms.RichTextBox.AllowDrop%2A> property of the <xref:System.Windows.Forms.RichTextBox> control to `true`.</span></span>  
  
2. <span data-ttu-id="cdb5b-107">在 <xref:System.Windows.Forms.RichTextBox.DragEnter> 事件的事件处理程序中编写代码。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-107">Write code in the event handler of the <xref:System.Windows.Forms.RichTextBox.DragEnter> event.</span></span> <span data-ttu-id="cdb5b-108">使用 `if` 语句来确保要拖动的数据为可接受的类型（本例为文本）。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-108">Use an `if` statement to ensure that the data being dragged is of an acceptable type (in this case, text).</span></span> <span data-ttu-id="cdb5b-109"><xref:System.Windows.Forms.DragEventArgs.Effect%2A?displayProperty=nameWithType> 属性可以设置为 <xref:System.Windows.Forms.DragDropEffects> 枚举的任何值。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-109">The <xref:System.Windows.Forms.DragEventArgs.Effect%2A?displayProperty=nameWithType> property can be set to any value of the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span>  
  
    ```vb  
    Private Sub RichTextBox1_DragEnter(ByVal sender As Object, _
       ByVal e As System.Windows.Forms.DragEventArgs) _
       Handles RichTextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
          e.Effect = DragDropEffects.Copy  
       Else  
          e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragEnter(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    ```cpp  
    private:  
       void richTextBox1_DragEnter(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          if (e->Data->GetDataPresent(DataFormats::Text))  
             e->Effect = DragDropEffects::Copy;  
          else  
             e->Effect = DragDropEffects::None;  
       }  
    ```  
  
     <span data-ttu-id="cdb5b-110"> (Visual c # 和 Visual C++) 将以下代码放在窗体构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-110">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.richTextBox1.DragEnter += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragEnter);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragEnter += gcnew  
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragEnter);  
    ```  
  
3. <span data-ttu-id="cdb5b-111">编写代码以处理 <xref:System.Windows.Forms.RichTextBox.DragDrop> 事件。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-111">Write code to handle the <xref:System.Windows.Forms.RichTextBox.DragDrop> event.</span></span> <span data-ttu-id="cdb5b-112">使用 <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=nameWithType> 方法来检索要拖动的数据。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-112">Use the <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=nameWithType> method to retrieve the data being dragged.</span></span>  
  
     <span data-ttu-id="cdb5b-113">在下面的示例中，代码会将 <xref:System.Windows.Forms.RichTextBox.Text%2A> 控件的 <xref:System.Windows.Forms.RichTextBox> 属性设置为等于要拖动的数据。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-113">In the example below, the code sets the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control equal to the data being dragged.</span></span> <span data-ttu-id="cdb5b-114">如果 <xref:System.Windows.Forms.RichTextBox> 控件中已有文本，拖动的文本将插入到插入点。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-114">If there is already text in the <xref:System.Windows.Forms.RichTextBox> control, the dragged text is inserted at the insertion point.</span></span>  
  
    ```vb  
    Private Sub RichTextBox1_DragDrop(ByVal sender As Object, _
       ByVal e As System.Windows.Forms.DragEventArgs) _
       Handles RichTextBox1.DragDrop  
       Dim i As Int16
       Dim s As String  
  
       ' Get start position to drop the text.  
       i = RichTextBox1.SelectionStart  
       s = RichTextBox1.Text.Substring(i)  
       RichTextBox1.Text = RichTextBox1.Text.Substring(0, i)  
  
       ' Drop the text on to the RichTextBox.  
       RichTextBox1.Text = RichTextBox1.Text + _  
          e.Data.GetData(DataFormats.Text).ToString()  
       RichTextBox1.Text = RichTextBox1.Text + s  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragDrop(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       int i;  
       String s;  
  
       // Get start position to drop the text.  
       i = richTextBox1.SelectionStart;  
       s = richTextBox1.Text.Substring(i);  
       richTextBox1.Text = richTextBox1.Text.Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       richTextBox1.Text = richTextBox1.Text +
          e.Data.GetData(DataFormats.Text).ToString();  
       richTextBox1.Text = richTextBox1.Text + s;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void richTextBox1_DragDrop(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          int i;  
          String ^s;  
  
       // Get start position to drop the text.  
       i = richTextBox1->SelectionStart;  
       s = richTextBox1->Text->Substring(i);  
       richTextBox1->Text = richTextBox1->Text->Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       String ^str = String::Concat(richTextBox1->Text, e->Data  
       ->GetData(DataFormats->Text)->ToString());
       richTextBox1->Text = String::Concat(str, s);  
       }  
    ```  
  
     <span data-ttu-id="cdb5b-115"> (Visual c # 和 Visual C++) 将以下代码放在窗体构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-115">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.richTextBox1.DragDrop += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragDrop);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragDrop += gcnew
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragDrop);  
    ```  
  
### <a name="to-test-the-drag-and-drop-functionality-in-your-application"></a><span data-ttu-id="cdb5b-116">测试应用程序中的拖放功能</span><span class="sxs-lookup"><span data-stu-id="cdb5b-116">To test the drag-and-drop functionality in your application</span></span>  
  
1. <span data-ttu-id="cdb5b-117">保存并生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-117">Save and build your application.</span></span> <span data-ttu-id="cdb5b-118">在运行期间，运行写字板。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-118">While it is running, run WordPad.</span></span>  
  
     <span data-ttu-id="cdb5b-119">写字板是由 Windows 安装的允许拖放操作的文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-119">WordPad is a text editor installed by Windows that allows drag-and-drop operations.</span></span> <span data-ttu-id="cdb5b-120">可以通过单击“开始”  按钮，选择“运行” ，在“运行” `WordPad`**对话框的文本框中键入** ，然后单击“确定” 来访问它。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-120">It is accessible by clicking the **Start** button, selecting **Run**, typing `WordPad` in the text box of the **Run** dialog box, and then clicking **OK**.</span></span>  
  
2. <span data-ttu-id="cdb5b-121">打开写字板后，在其中键入文本字符串。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-121">Once WordPad is open, type a string of text in it.</span></span> <span data-ttu-id="cdb5b-122">使用鼠标选择该文本，然后将所选的文本拖到 Windows 应用程序中的 <xref:System.Windows.Forms.RichTextBox> 控件之上。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-122">Using the mouse, select the text, and then drag the selected text over to the <xref:System.Windows.Forms.RichTextBox> control in your Windows application.</span></span>  
  
     <span data-ttu-id="cdb5b-123">注意，将鼠标移到 <xref:System.Windows.Forms.RichTextBox> 控件上（并因此引发 <xref:System.Windows.Forms.RichTextBox.DragEnter> 事件）时，鼠标指针会改变，可以将所选的文本放入 <xref:System.Windows.Forms.RichTextBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-123">Notice that when you point the mouse at the <xref:System.Windows.Forms.RichTextBox> control (and, consequently, raise the <xref:System.Windows.Forms.RichTextBox.DragEnter> event), the mouse pointer changes and you can drop the selected text into the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
     <span data-ttu-id="cdb5b-124">释放鼠标按钮，所选文本将放开（也就是引发 <xref:System.Windows.Forms.RichTextBox.DragDrop> 事件）并插入到 <xref:System.Windows.Forms.RichTextBox> 控件中。</span><span class="sxs-lookup"><span data-stu-id="cdb5b-124">When you release the mouse button, the selected text is dropped (that is, the <xref:System.Windows.Forms.RichTextBox.DragDrop> event is raised) and is inserted within the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdb5b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cdb5b-125">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="cdb5b-126">如何：在应用程序之间执行拖放操作</span><span class="sxs-lookup"><span data-stu-id="cdb5b-126">How to: Perform Drag-and-Drop Operations Between Applications</span></span>](../advanced/how-to-perform-drag-and-drop-operations-between-applications.md)
- [<span data-ttu-id="cdb5b-127">RichTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="cdb5b-127">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="cdb5b-128">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="cdb5b-128">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
