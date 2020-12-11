---
title: 通过 RichTextBox 控件保存文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- RTF files [Windows Forms], saving in RichTextBox control
- examples [Windows Forms], text boxes
- saving files [Windows Forms], RichTextBox control
- files [Windows Forms], saving with RichTextBox control
- RichTextBox control [Windows Forms], saving files
- .rtf files [Windows Forms], saving in RichTextBox control
- text files [Windows Forms], saving from RichTextBox control
ms.assetid: 4a58ec19-84d1-4383-9110-298c06adcfca
ms.openlocfilehash: a87b93a53347aeba54f944b0f4c455aa272ea243
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970534"
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="8bace-102">如何：使用 Windows 窗体 RichTextBox 控件保存文件</span><span class="sxs-lookup"><span data-stu-id="8bace-102">How to: Save Files with the Windows Forms RichTextBox Control</span></span>

<span data-ttu-id="8bace-103">Windows 窗体 <xref:System.Windows.Forms.RichTextBox> 控件可以用以下几种格式之一编写显示的信息：</span><span class="sxs-lookup"><span data-stu-id="8bace-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can write the information it displays in one of several formats:</span></span>

- <span data-ttu-id="8bace-104">纯文本</span><span class="sxs-lookup"><span data-stu-id="8bace-104">Plain text</span></span>

- <span data-ttu-id="8bace-105">Unicode 纯文本</span><span class="sxs-lookup"><span data-stu-id="8bace-105">Unicode plain text</span></span>

- <span data-ttu-id="8bace-106">Rich-Text 格式 (RTF) </span><span class="sxs-lookup"><span data-stu-id="8bace-106">Rich-Text Format (RTF)</span></span>

- <span data-ttu-id="8bace-107">用空格代替 OLE 对象的 RTF</span><span class="sxs-lookup"><span data-stu-id="8bace-107">RTF with spaces in place of OLE objects</span></span>

- <span data-ttu-id="8bace-108">带有 OLE 对象的文本化表示形式的纯文本</span><span class="sxs-lookup"><span data-stu-id="8bace-108">Plain text with a textual representation of OLE objects</span></span>

<span data-ttu-id="8bace-109">若要保存文件，请调用 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="8bace-109">To save a file, call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method.</span></span> <span data-ttu-id="8bace-110">还可以使用 **SaveFile** 方法将数据保存到流中。</span><span class="sxs-lookup"><span data-stu-id="8bace-110">You can also use the **SaveFile** method to save data to a stream.</span></span> <span data-ttu-id="8bace-111">有关详细信息，请参阅 <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>。</span><span class="sxs-lookup"><span data-stu-id="8bace-111">For more information, see <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>

### <a name="to-save-the-contents-of-the-control-to-a-file"></a><span data-ttu-id="8bace-112">将控件的内容保存到文件中</span><span class="sxs-lookup"><span data-stu-id="8bace-112">To save the contents of the control to a file</span></span>

1. <span data-ttu-id="8bace-113">确定要保存的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="8bace-113">Determine the path of the file to be saved.</span></span>

    <span data-ttu-id="8bace-114">若要在实际应用程序中执行此操作，通常要使用 <xref:System.Windows.Forms.SaveFileDialog> 组件。</span><span class="sxs-lookup"><span data-stu-id="8bace-114">To do this in a real-world application, you would typically use the <xref:System.Windows.Forms.SaveFileDialog> component.</span></span> <span data-ttu-id="8bace-115">有关概述，请参阅 [SaveFileDialog 组件概述](savefiledialog-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="8bace-115">For an overview, see [SaveFileDialog Component Overview](savefiledialog-component-overview-windows-forms.md).</span></span>

2. <span data-ttu-id="8bace-116">调用 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> 控件的方法 <xref:System.Windows.Forms.RichTextBox> ，指定要保存的文件，还可以指定一个文件类型。</span><span class="sxs-lookup"><span data-stu-id="8bace-116">Call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to save and optionally a file type.</span></span> <span data-ttu-id="8bace-117">如果调用方法时将文件名作为其唯一参数，则该文件将保存为 RTF 格式。</span><span class="sxs-lookup"><span data-stu-id="8bace-117">If you call the method with a file name as its only argument, the file will be saved as RTF.</span></span> <span data-ttu-id="8bace-118">若要指定其他文件类型，请使用 <xref:System.Windows.Forms.RichTextBoxStreamType> 枚举的值作为其第二个参数来调用该方法。</span><span class="sxs-lookup"><span data-stu-id="8bace-118">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>

    <span data-ttu-id="8bace-119">在下面的示例中，为 rtf 文件的位置设置的路径是 " **我的文档** " 文件夹。</span><span class="sxs-lookup"><span data-stu-id="8bace-119">In the example below, the path set for the location of the rich-text file is the **My Documents** folder.</span></span> <span data-ttu-id="8bace-120">使用此位置的原因是，你可以假定大多数运行 Windows 操作系统的计算机都包含此文件夹。</span><span class="sxs-lookup"><span data-stu-id="8bace-120">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="8bace-121">选择此位置还允许具有最低系统访问级别的用户安全运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="8bace-121">Choosing this location also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="8bace-122">下面的示例假设窗体 <xref:System.Windows.Forms.RichTextBox> 已添加控件。</span><span class="sxs-lookup"><span data-stu-id="8bace-122">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control already added.</span></span>

    ```vb
    Public Sub SaveFile()
       ' You should replace the bold file name in the
       ' sample below with a file name of your own choosing.
       RichTextBox1.SaveFile(System.Environment.GetFolderPath _
       (System.Environment.SpecialFolder.Personal) _
       & "\Testdoc.rtf", _
          RichTextBoxStreamType.RichNoOleObjs)
    End Sub
    ```

    ```csharp
    public void SaveFile()
    {
       // You should replace the bold file name in the
       // sample below with a file name of your own choosing.
       // Note the escape character used (@) when specifying the path.
       richTextBox1.SaveFile(System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\Testdoc.rtf",
          RichTextBoxStreamType.RichNoOleObjs);
    }
    ```

    ```cpp
    public:
       void SaveFile()
       {
          // You should replace the bold file name in the
          // sample below with a file name of your own choosing.
          richTextBox1->SaveFile(String::Concat
             (System::Environment::GetFolderPath
             (System::Environment::SpecialFolder::Personal),
             "\\Testdoc.rtf"), RichTextBoxStreamType::RichNoOleObjs);
       }
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="8bace-123">此示例在文件尚未存在时创建新文件。</span><span class="sxs-lookup"><span data-stu-id="8bace-123">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="8bace-124">如果应用程序需要创建文件，则该应用程序需要为该文件夹创建访问权限。</span><span class="sxs-lookup"><span data-stu-id="8bace-124">If an application needs to create a file, that application needs Create access for the folder.</span></span> <span data-ttu-id="8bace-125">可使用访问控制列表设置权限。</span><span class="sxs-lookup"><span data-stu-id="8bace-125">Permissions are set using access control lists.</span></span> <span data-ttu-id="8bace-126">如果该文件已存在，则该应用程序只需一个较小的权限。</span><span class="sxs-lookup"><span data-stu-id="8bace-126">If the file already exists, the application needs only Write access, a lesser privilege.</span></span> <span data-ttu-id="8bace-127">如果可能，在部署过程中创建文件并只授予对单个文件的读取访问权限，而不是创建对文件夹的访问权限，则更安全。</span><span class="sxs-lookup"><span data-stu-id="8bace-127">Where possible, it is more secure to create the file during deployment, and only grant Read access to a single file, rather than Create access for a folder.</span></span> <span data-ttu-id="8bace-128">此外，较安全的做法是将数据写入用户文件夹，而不是根文件夹或“Program Files”文件夹。</span><span class="sxs-lookup"><span data-stu-id="8bace-128">Also, it is more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>

## <a name="see-also"></a><span data-ttu-id="8bace-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8bace-129">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="8bace-130">RichTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="8bace-130">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="8bace-131">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="8bace-131">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
