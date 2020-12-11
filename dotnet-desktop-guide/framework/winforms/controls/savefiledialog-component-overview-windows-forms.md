---
title: SaveFileDialog 组件概述
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: 7609c29b7e932ecee7dc8a289617094bd8d480e2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970292"
---
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="8c26f-102">SaveFileDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="8c26f-102">SaveFileDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="8c26f-103">Windows 窗体 <xref:System.Windows.Forms.SaveFileDialog> 组件是一个预配置的对话框。</span><span class="sxs-lookup"><span data-stu-id="8c26f-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="8c26f-104">它与 Windows 使用的标准 " **保存文件** " 对话框相同。</span><span class="sxs-lookup"><span data-stu-id="8c26f-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="8c26f-105">它继承自 <xref:System.Windows.Forms.CommonDialog> 类。</span><span class="sxs-lookup"><span data-stu-id="8c26f-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="8c26f-106">使用 SaveFileDialog 组件</span><span class="sxs-lookup"><span data-stu-id="8c26f-106">Working with the SaveFileDialog Component</span></span>

<span data-ttu-id="8c26f-107">将其用作使用户能够保存文件而不是配置自己的对话框的简单解决方案。</span><span class="sxs-lookup"><span data-stu-id="8c26f-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="8c26f-108">通过依赖标准 Windows 对话框，用户可以立即熟悉您创建的应用程序的基本功能。</span><span class="sxs-lookup"><span data-stu-id="8c26f-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="8c26f-109">但请注意，在使用 <xref:System.Windows.Forms.SaveFileDialog> 组件时，必须编写自己的文件保存逻辑。</span><span class="sxs-lookup"><span data-stu-id="8c26f-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>

<span data-ttu-id="8c26f-110">您可以使用 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 方法在运行时显示该对话框。</span><span class="sxs-lookup"><span data-stu-id="8c26f-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="8c26f-111">您可以使用方法在读/写模式下打开文件 <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> 。</span><span class="sxs-lookup"><span data-stu-id="8c26f-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>

<span data-ttu-id="8c26f-112">将该组件添加到窗体时，该 <xref:System.Windows.Forms.SaveFileDialog> 组件将出现在 Visual Studio 中 Windows 窗体设计器底部的托盘中。</span><span class="sxs-lookup"><span data-stu-id="8c26f-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c26f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c26f-113">See also</span></span>

- <xref:System.Windows.Forms.SaveFileDialog>
- [<span data-ttu-id="8c26f-114">SaveFileDialog 组件</span><span class="sxs-lookup"><span data-stu-id="8c26f-114">SaveFileDialog Component</span></span>](savefiledialog-component-windows-forms.md)
