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
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="6021e-102">FolderBrowserDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="6021e-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="6021e-103">Windows 窗体 <xref:System.Windows.Forms.FolderBrowserDialog> 组件是用于浏览和选择文件夹的模式对话框。</span><span class="sxs-lookup"><span data-stu-id="6021e-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="6021e-104">还可以从组件内创建新文件夹 <xref:System.Windows.Forms.FolderBrowserDialog> 。</span><span class="sxs-lookup"><span data-stu-id="6021e-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>

> [!NOTE]
> <span data-ttu-id="6021e-105">若要选择文件而不是文件夹，请使用 [OpenFileDialog](openfiledialog-component-windows-forms.md) 组件。</span><span class="sxs-lookup"><span data-stu-id="6021e-105">To select files, instead of folders, use the [OpenFileDialog](openfiledialog-component-windows-forms.md) component.</span></span>

<span data-ttu-id="6021e-106"><xref:System.Windows.Forms.FolderBrowserDialog>组件在运行时使用 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 方法显示。</span><span class="sxs-lookup"><span data-stu-id="6021e-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="6021e-107">设置 <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> 属性以确定最顶层的文件夹以及将出现在对话框的树视图中的所有子文件夹。</span><span class="sxs-lookup"><span data-stu-id="6021e-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="6021e-108">显示该对话框后，可以使用 <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> 属性来获取所选文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="6021e-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>

<span data-ttu-id="6021e-109">将该组件添加到窗体时，该 <xref:System.Windows.Forms.FolderBrowserDialog> 组件将出现在 Visual Studio 中 Windows 窗体设计器底部的托盘中。</span><span class="sxs-lookup"><span data-stu-id="6021e-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="6021e-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6021e-110">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="6021e-111">如何：使用 Windows 窗体 FolderBrowserDialog 组件选择文件夹</span><span class="sxs-lookup"><span data-stu-id="6021e-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [<span data-ttu-id="6021e-112">FolderBrowserDialog 组件</span><span class="sxs-lookup"><span data-stu-id="6021e-112">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
