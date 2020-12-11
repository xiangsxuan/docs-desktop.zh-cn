---
title: PrintDialog 组件概述
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 0ed7f7a1f9770f71b75ae744a056b6943335c852
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971066"
---
# <a name="printdialog-component-overview-windows-forms"></a>PrintDialog 组件概述（Windows 窗体）

Windows 窗体 [PrintDialog](printdialog-component-windows-forms.md) 组件是一个预先配置的对话框，用于选择打印机、选择要打印的页面，以及在基于 Windows 的应用程序中确定其他与打印相关的设置。 将该组件用作选择打印机和打印相关设置的简单解决方案，而不用配置你自己的对话框。 可以让用户打印文档的多个部分： "全部打印"、"打印选定的页范围" 或 "打印选定内容"。 利用标准的 Windows 对话框，你可以创建其基本功能可立即为用户所熟悉的应用程序。 <xref:System.Windows.Forms.PrintDialog>组件继承自 <xref:System.Windows.Forms.CommonDialog> 类。

## <a name="working-with-the-component"></a>使用组件

使用 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 方法可在运行时显示该对话框。 此组件具有与单个打印作业 (<xref:System.Drawing.Printing.PrintDocument> 类) 或单个打印机 (类) 设置相关的属性 <xref:System.Drawing.Printing.PrinterSettings> 。 反过来，其中的任何一个都可以由多个打印机共享。

将该组件添加到窗体时，该 <xref:System.Windows.Forms.PrintDialog> 组件将出现在 Visual Studio 中 Windows 窗体设计器底部的托盘中。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.PrintDialog>
- [PrintDialog 组件](printdialog-component-windows-forms.md)
