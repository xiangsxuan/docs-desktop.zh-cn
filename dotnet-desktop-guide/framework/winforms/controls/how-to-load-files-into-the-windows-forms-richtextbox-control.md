---
title: 将文件加载到 RichTextBox 控件中
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying files
- examples [Windows Forms], text boxes
- .rtf files [Windows Forms], opening in RichTextBox control
- RTF files [Windows Forms], opening in RichTextBox control
- text files [Windows Forms], displaying in RichTextBox control
- .rtf files [Windows Forms], displaying in RichTextBox control
- RichTextBox control [Windows Forms], opening files
- RTF files [Windows Forms], displaying in RichTextBox control
ms.assetid: c03451be-f285-4428-a71a-c41e002cc919
ms.openlocfilehash: 78285094eb1d7def9b306ec88b95bf9e456f90d5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972579"
---
# <a name="how-to-load-files-into-the-windows-forms-richtextbox-control"></a><span data-ttu-id="b5bd3-102">如何：将文件加载到 Windows 窗体 RichTextBox 控件中</span><span class="sxs-lookup"><span data-stu-id="b5bd3-102">How to: Load Files into the Windows Forms RichTextBox Control</span></span>

<span data-ttu-id="b5bd3-103">Windows 窗体 <xref:System.Windows.Forms.RichTextBox> 控件可以显示纯文本、Unicode 纯文本或 RTF 格式 (RTF) 文件。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display a plain-text, Unicode plain-text, or Rich-Text-Format (RTF) file.</span></span> <span data-ttu-id="b5bd3-104">若要显示这些文件，请调用 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-104">To do so, call the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method.</span></span> <span data-ttu-id="b5bd3-105">还可以使用 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> 方法从流中加载数据。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-105">You can also use the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method to load data from a stream.</span></span> <span data-ttu-id="b5bd3-106">有关详细信息，请参阅 <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-106">For more information, see <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>

### <a name="to-load-a-file-into-the-richtextbox-control"></a><span data-ttu-id="b5bd3-107">将文件加载到 RichTextBox 控件中</span><span class="sxs-lookup"><span data-stu-id="b5bd3-107">To load a file into the RichTextBox control</span></span>

1. <span data-ttu-id="b5bd3-108">使用 <xref:System.Windows.Forms.OpenFileDialog> 组件确定要打开的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-108">Determine the path of the file to be opened using the <xref:System.Windows.Forms.OpenFileDialog> component.</span></span> <span data-ttu-id="b5bd3-109">有关概述，请参阅 [OpenFileDialog 组件概述](openfiledialog-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-109">For an overview, see [OpenFileDialog Component Overview](openfiledialog-component-overview-windows-forms.md).</span></span>

2. <span data-ttu-id="b5bd3-110">调用 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> 控件的 <xref:System.Windows.Forms.RichTextBox> 方法，指定要加载的文件，并且可以指定文件类型。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-110">Call the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to load and optionally a file type.</span></span> <span data-ttu-id="b5bd3-111">在下面的示例中，要加载的文件来自 <xref:System.Windows.Forms.OpenFileDialog> 组件的 <xref:System.Windows.Forms.FileDialog.FileName%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-111">In the example below, the file to load is taken from the <xref:System.Windows.Forms.OpenFileDialog> component's <xref:System.Windows.Forms.FileDialog.FileName%2A> property.</span></span> <span data-ttu-id="b5bd3-112">如果调用该方法时仅使用文件名作为其唯一参数，则会假定该文件类型为 RTF。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-112">If you call the method with a file name as its only argument, the file type will be assumed to be RTF.</span></span> <span data-ttu-id="b5bd3-113">若要指定其他文件类型，请使用 <xref:System.Windows.Forms.RichTextBoxStreamType> 枚举的值作为其第二个参数来调用该方法。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-113">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>

    <span data-ttu-id="b5bd3-114">在下面的示例中，单击按钮时显示 <xref:System.Windows.Forms.OpenFileDialog> 组件。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-114">In the example below, the <xref:System.Windows.Forms.OpenFileDialog> component is shown when a button is clicked.</span></span> <span data-ttu-id="b5bd3-115">然后，在 <xref:System.Windows.Forms.RichTextBox> 控件中打开并显示所选文件。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-115">The file selected is then opened and displayed in the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="b5bd3-116">此示例假定窗体包含一个`btnOpenFile`按钮。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-116">This example assumes a form has a button,`btnOpenFile`.</span></span>

    ```vb
    Private Sub btnOpenFile_Click(ByVal sender As System.Object, _
       ByVal e As System.EventArgs) Handles btnOpenFile.Click
         If OpenFileDialog1.ShowDialog() = DialogResult.OK Then
           RichTextBox1.LoadFile(OpenFileDialog1.FileName, _
              RichTextBoxStreamType.RichText)
          End If
    End Sub
    ```

    ```csharp
    private void btnOpenFile_Click(object sender, System.EventArgs e)
    {
       if(openFileDialog1.ShowDialog() == DialogResult.OK)
       {
         richTextBox1.LoadFile(openFileDialog1.FileName, RichTextBoxStreamType.RichText);
       }
    }
    ```

    ```cpp
    private:
       void btnOpenFile_Click(System::Object ^  sender,
          System::EventArgs ^  e)
       {
          if(openFileDialog1->ShowDialog() == DialogResult::OK)
          {
             richTextBox1->LoadFile(openFileDialog1->FileName,
                RichTextBoxStreamType::RichText);
          }
       }
    ```

    <span data-ttu-id="b5bd3-117"> (Visual c # 中，Visual C++) 将以下代码放在窗体构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-117">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>

    ```csharp
    this.btnOpenFile.Click += new System.EventHandler(this. btnOpenFile_Click);
    ```

    ```cpp
    this->btnOpenFile->Click += gcnew
       System::EventHandler(this, &Form1::btnOpenFile_Click);
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="b5bd3-118">若要运行此进程，程序集可能需要 <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> 类授予的特权等级。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-118">To run this process, your assembly may require a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="b5bd3-119">如果在部分信任上下文中运行，该进程可能会因特权不足而引发异常。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-119">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="b5bd3-120">有关详细信息，请参阅 [Code Access Security Basics](/dotnet/framework/misc/code-access-security-basics)。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-120">For more information, see [Code Access Security Basics](/dotnet/framework/misc/code-access-security-basics).</span></span>

## <a name="see-also"></a><span data-ttu-id="b5bd3-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5bd3-121">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.LoadFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="b5bd3-122">RichTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="b5bd3-122">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="b5bd3-123">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="b5bd3-123">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
