---
title: 打印支持
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: d6e8f60db7afe2f1b04eaae6fe71aa93e5c22cae
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971344"
---
# <a name="windows-forms-print-support"></a>Windows 窗体打印支持
Windows 窗体中的打印主要包括使用 [PrintDocument 组件](../controls/printdocument-component-windows-forms.md) 组件来使用户能够打印， [PrintPreviewDialog 控件](../controls/printpreviewdialog-control-windows-forms.md) 控制 [PrintDialog 组件](../controls/printdialog-component-windows-forms.md) 和 [PageSetupDialog 组件](../controls/pagesetupdialog-component-windows-forms.md) 组件，为习惯于 Windows 操作系统的用户提供熟悉的图形界面。  
  
 通常，您创建组件的新实例 <xref:System.Drawing.Printing.PrintDocument> ，使用和类设置描述打印内容的属性， <xref:System.Drawing.Printing.PrinterSettings> <xref:System.Drawing.Printing.PageSettings> 然后调用 <xref:System.Drawing.Printing.PrintDocument.Print%2A> 方法以实际打印文档。  
  
 在从基于 Windows 的应用程序中进行打印的过程中，该 <xref:System.Drawing.Printing.PrintDocument> 组件将显示 "中止打印" 对话框，以便向用户发出警报，提醒用户发生打印并允许取消打印作业。  
  
## <a name="in-this-section"></a>本节内容  
 [如何：创建标准的 Windows 窗体打印作业](how-to-create-standard-windows-forms-print-jobs.md)  
 介绍如何使用 <xref:System.Drawing.Printing.PrintDocument> 组件从 Windows 窗体中进行打印。  
  
 [如何：在运行时从 PrintDialog 中捕获用户输入](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 说明如何使用组件以编程方式修改选定的打印选项 <xref:System.Windows.Forms.PrintDialog> 。  
  
 [如何：在 Windows 窗体中选择附加到用户计算机的打印机](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 描述如何在运行时使用组件更改要打印到的打印机 <xref:System.Windows.Forms.PrintDialog> 。  
  
 [如何：打印 Windows 窗体中的图形](how-to-print-graphics-in-windows-forms.md)  
 介绍如何将图形发送到打印机。  
  
 [如何：打印 Windows 窗体中的多页文本文件](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 介绍如何将文本发送到打印机。  
  
 [如何：完成 Windows 窗体打印作业](how-to-complete-windows-forms-print-jobs.md)  
 说明如何提醒用户完成打印作业。  
  
 [如何：打印 Windows 窗体](how-to-print-a-windows-form.md)  
 说明如何打印当前窗体的副本。  
  
 [如何：使用打印预览在 Windows 窗体中进行打印](how-to-print-in-windows-forms-using-print-preview.md)  
 演示如何使用 <xref:System.Windows.Forms.PrintPreviewDialog> 来打印文档。  
  
## <a name="related-sections"></a>相关章节  
 [PrintDocument 组件](../controls/printdocument-component-windows-forms.md)  
 介绍组件的用法 <xref:System.Drawing.Printing.PrintDocument> 。  
  
 [PrintDialog 组件](../controls/printdialog-component-windows-forms.md)  
 介绍组件的用法 <xref:System.Windows.Forms.PrintDialog> 。  
  
 [PrintPreviewDialog 控件](../controls/printpreviewdialog-control-windows-forms.md)  
 说明控件的用法 <xref:System.Windows.Forms.PrintPreviewDialog> 。  
  
 [PageSetupDialog 组件](../controls/pagesetupdialog-component-windows-forms.md)  
 介绍组件的用法 <xref:System.Windows.Forms.PageSetupDialog> 。  
  
 <xref:System.Drawing.Printing>  
 描述命名空间中的类 <xref:System.Drawing.Printing> 。
