---
title: 如何显示 PrintDialog 组件
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: de0acc655bbcf0cfc017d594545fae56cc27f981
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971190"
---
# <a name="how-to-display-the-printdialog-component"></a>如何显示 PrintDialog 组件

<xref:System.Windows.Forms.PrintDialog>组件是您的许多用户将熟悉的标准 Windows "打印" 对话框。 由于你的用户会立即熟悉它，因此，你可以使用该 <xref:System.Windows.Forms.PrintDialog> 组件。

## <a name="to-display-the-printdialog-component"></a>显示 PrintDialog 组件

- <xref:System.Windows.Forms.Form.ShowDialog%2A>从应用程序的代码中调用方法。

     显示出该组件后，用户可以与之进行交互，设置打印作业的属性。 <xref:System.Drawing.Printing.PrinterSettings> <xref:System.Drawing.Printing.PageSettings> 如果用户通过与该打印作业关联) 组件访问[PageSetupDialog 组件](pagesetupdialog-component-windows-forms.md)，则这些存储在类 (和类中 <xref:System.Windows.Forms.PrintDialog> 。 然后可以调用它们所设置的属性以确定打印作业的细节。

## <a name="see-also"></a>另请参阅

- [如何：创建标准的 Windows 窗体打印作业](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [如何：在运行时从 PrintDialog 中捕获用户输入](../advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)
- [PrintPreviewDialog 控件](printpreviewdialog-control-windows-forms.md)
- [PrintDialog 组件](printdialog-component-windows-forms.md)
- [Windows 窗体打印支持](../advanced/windows-forms-print-support.md)
- [Windows 窗体控件](index.md)
