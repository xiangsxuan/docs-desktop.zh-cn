---
title: OpenFileDialog 组件概述
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: c519b373150a49ee41dbb0c503f7d5a4862477d5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972601"
---
# <a name="openfiledialog-component-overview-windows-forms"></a><span data-ttu-id="eef69-102">OpenFileDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="eef69-102">OpenFileDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="eef69-103">Windows 窗体 <xref:System.Windows.Forms.OpenFileDialog> 组件是一个预配置的对话框。</span><span class="sxs-lookup"><span data-stu-id="eef69-103">The Windows Forms <xref:System.Windows.Forms.OpenFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="eef69-104">它与 Windows 操作系统公开的 " **打开文件** " 对话框相同。</span><span class="sxs-lookup"><span data-stu-id="eef69-104">It is the same **Open File** dialog box exposed by the Windows operating system.</span></span> <span data-ttu-id="eef69-105">它继承自 <xref:System.Windows.Forms.CommonDialog> 类。</span><span class="sxs-lookup"><span data-stu-id="eef69-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="use-this-component"></a><span data-ttu-id="eef69-106">使用此组件</span><span class="sxs-lookup"><span data-stu-id="eef69-106">Use this component</span></span>

<span data-ttu-id="eef69-107">在基于 Windows 的应用程序中使用此组件，就是一个用于选择文件的简单解决方案，而不是配置自己的对话框。</span><span class="sxs-lookup"><span data-stu-id="eef69-107">Use this component within your Windows-based application as a simple solution for file selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="eef69-108">利用标准的 Windows 对话框，你可以创建其基本功能可立即为用户所熟悉的应用程序。</span><span class="sxs-lookup"><span data-stu-id="eef69-108">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="eef69-109">但请注意，在使用 <xref:System.Windows.Forms.OpenFileDialog> 组件时，必须编写自己的文件打开逻辑。</span><span class="sxs-lookup"><span data-stu-id="eef69-109">Be aware, however, that when using the <xref:System.Windows.Forms.OpenFileDialog> component, you must write your own file-opening logic.</span></span>

<span data-ttu-id="eef69-110">使用 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 方法可在运行时显示对话框。</span><span class="sxs-lookup"><span data-stu-id="eef69-110">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="eef69-111">可以让用户通过属性打开多选文件 <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> 。</span><span class="sxs-lookup"><span data-stu-id="eef69-111">You can enable users to multi-select files to be opened with the <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> property.</span></span> <span data-ttu-id="eef69-112">此外，还可以使用 <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> 属性来确定对话框中是否显示了只读复选框。</span><span class="sxs-lookup"><span data-stu-id="eef69-112">Additionally, you can use the <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> property to determine if a read-only check box appears in the dialog box.</span></span> <span data-ttu-id="eef69-113"><xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A>属性指示是否选中只读复选框。</span><span class="sxs-lookup"><span data-stu-id="eef69-113">The <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> property indicates whether the read-only check box is selected.</span></span> <span data-ttu-id="eef69-114">最后，此 <xref:System.Windows.Forms.FileDialog.Filter%2A> 属性设置当前文件名筛选器字符串，该字符串确定对话框中 "文件类型" 框中显示的选项。</span><span class="sxs-lookup"><span data-stu-id="eef69-114">Finally, the <xref:System.Windows.Forms.FileDialog.Filter%2A> property sets the current file name filter string, which determines the choices that appear in the "Files of type" box in the dialog box.</span></span>

<span data-ttu-id="eef69-115">将该组件添加到窗体时，该 <xref:System.Windows.Forms.OpenFileDialog> 组件将出现在 Visual Studio 中 Windows 窗体设计器底部的托盘中。</span><span class="sxs-lookup"><span data-stu-id="eef69-115">When it is added to a form, the <xref:System.Windows.Forms.OpenFileDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="eef69-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eef69-116">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="eef69-117">OpenFileDialog 组件</span><span class="sxs-lookup"><span data-stu-id="eef69-117">OpenFileDialog Component</span></span>](openfiledialog-component-windows-forms.md)
