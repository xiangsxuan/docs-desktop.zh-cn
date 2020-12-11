---
title: 如何：用 OpenFileDialog 组件打开文件
ms.date: 02/11/2019
description: 了解如何使用 OpenFileDialog 组件打开 Windows 对话框以浏览和选择文件。
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: 7021aacf09d7d927322abf1c9aa883bbb29507a8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970556"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a>如何：用 OpenFileDialog 打开文件

<xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType>组件打开 Windows 对话框以浏览和选择文件。 若要打开并读取选定的文件，可以使用 <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> 方法，或创建类的实例 <xref:System.IO.StreamReader?displayProperty=nameWithType> 。 下面的示例演示了这两种方法。

在 .NET Framework 中，若要获取或设置 <xref:System.Windows.Forms.FileDialog.FileName%2A> 属性，需要类授予的特权级别 <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> 。 示例运行 <xref:System.Security.Permissions.FileIOPermission> 权限检查，如果在部分信任上下文中运行，则会引发异常，因为权限不足。 有关详细信息，请参阅 [代码访问安全性基础知识](/dotnet/framework/misc/code-access-security-basics)。

可以从 c # 或 Visual Basic 命令行 .NET Framework 应用生成并运行这些示例。 有关详细信息，请参阅 [命令行生成与 csc.exe](/dotnet/csharp/language-reference/compiler-options/command-line-building-with-csc-exe) 或 [从命令行生成](/dotnet/visual-basic/reference/command-line-compiler/building-from-the-command-line)。

从 .NET Core 3.0 开始，还可以从具有 .NET Core Windows 窗体 *\<folder name> .csproj* 项目文件的文件夹生成并运行示例作为 Windows .net core 应用。

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a>示例：使用 StreamReader 将文件作为流进行读取  
  
下面的示例使用 Windows 窗体 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Click> 事件处理程序， <xref:System.Windows.Forms.OpenFileDialog> 通过方法打开 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 。 用户选择文件并选择 **"确定"** 后，类的实例将 <xref:System.IO.StreamReader> 读取该文件并在窗体的文本框中显示其内容。 有关从文件流读取的详细信息，请参阅 <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> 和 <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType> 。  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a>示例：使用 OpenFile 通过筛选的选定内容打开文件

下面的示例使用 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Click> 事件处理程序打开 <xref:System.Windows.Forms.OpenFileDialog> 带有筛选器的，该筛选器只显示文本文件。 用户选择一个文本文件并选择 **"确定"** 后，该 <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 方法将用于在记事本中打开该文件。

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.OpenFileDialog>
- [OpenFileDialog 组件](openfiledialog-component-windows-forms.md)
