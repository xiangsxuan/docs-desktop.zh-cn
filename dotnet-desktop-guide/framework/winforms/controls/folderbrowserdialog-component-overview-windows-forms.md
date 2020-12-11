---
title: FolderBrowserDialog 组件概述
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: 8b017ba08ae4205e930ac00177c89a89fde17d3b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971536"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a>FolderBrowserDialog 组件概述（Windows 窗体）

Windows 窗体 <xref:System.Windows.Forms.FolderBrowserDialog> 组件是用于浏览和选择文件夹的模式对话框。 还可以从组件内创建新文件夹 <xref:System.Windows.Forms.FolderBrowserDialog> 。

> [!NOTE]
> 若要选择文件而不是文件夹，请使用 [OpenFileDialog](openfiledialog-component-windows-forms.md) 组件。

<xref:System.Windows.Forms.FolderBrowserDialog>组件在运行时使用 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 方法显示。 设置 <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> 属性以确定最顶层的文件夹以及将出现在对话框的树视图中的所有子文件夹。 显示该对话框后，可以使用 <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> 属性来获取所选文件夹的路径。

将该组件添加到窗体时，该 <xref:System.Windows.Forms.FolderBrowserDialog> 组件将出现在 Visual Studio 中 Windows 窗体设计器底部的托盘中。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [如何：使用 Windows 窗体 FolderBrowserDialog 组件选择文件夹](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [FolderBrowserDialog 组件](folderbrowserdialog-component-windows-forms.md)
