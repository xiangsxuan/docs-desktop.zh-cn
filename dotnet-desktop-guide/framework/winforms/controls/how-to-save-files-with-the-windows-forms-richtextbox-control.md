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
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a>如何：使用 Windows 窗体 RichTextBox 控件保存文件

Windows 窗体 <xref:System.Windows.Forms.RichTextBox> 控件可以用以下几种格式之一编写显示的信息：

- 纯文本

- Unicode 纯文本

- Rich-Text 格式 (RTF) 

- 用空格代替 OLE 对象的 RTF

- 带有 OLE 对象的文本化表示形式的纯文本

若要保存文件，请调用 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> 方法。 还可以使用 **SaveFile** 方法将数据保存到流中。 有关详细信息，请参阅 <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>。

### <a name="to-save-the-contents-of-the-control-to-a-file"></a>将控件的内容保存到文件中

1. 确定要保存的文件的路径。

    若要在实际应用程序中执行此操作，通常要使用 <xref:System.Windows.Forms.SaveFileDialog> 组件。 有关概述，请参阅 [SaveFileDialog 组件概述](savefiledialog-component-overview-windows-forms.md)。

2. 调用 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> 控件的方法 <xref:System.Windows.Forms.RichTextBox> ，指定要保存的文件，还可以指定一个文件类型。 如果调用方法时将文件名作为其唯一参数，则该文件将保存为 RTF 格式。 若要指定其他文件类型，请使用 <xref:System.Windows.Forms.RichTextBoxStreamType> 枚举的值作为其第二个参数来调用该方法。

    在下面的示例中，为 rtf 文件的位置设置的路径是 " **我的文档** " 文件夹。 使用此位置的原因是，你可以假定大多数运行 Windows 操作系统的计算机都包含此文件夹。 选择此位置还允许具有最低系统访问级别的用户安全运行该应用程序。 下面的示例假设窗体 <xref:System.Windows.Forms.RichTextBox> 已添加控件。

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
    > 此示例在文件尚未存在时创建新文件。 如果应用程序需要创建文件，则该应用程序需要为该文件夹创建访问权限。 可使用访问控制列表设置权限。 如果该文件已存在，则该应用程序只需一个较小的权限。 如果可能，在部署过程中创建文件并只授予对单个文件的读取访问权限，而不是创建对文件夹的访问权限，则更安全。 此外，较安全的做法是将数据写入用户文件夹，而不是根文件夹或“Program Files”文件夹。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox 控件](richtextbox-control-windows-forms.md)
- [在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)
