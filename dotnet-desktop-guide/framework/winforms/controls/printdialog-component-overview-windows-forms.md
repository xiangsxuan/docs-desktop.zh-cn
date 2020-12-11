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
# <a name="printdialog-component-overview-windows-forms"></a><span data-ttu-id="0048e-102">PrintDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="0048e-102">PrintDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="0048e-103">Windows 窗体 [PrintDialog](printdialog-component-windows-forms.md) 组件是一个预先配置的对话框，用于选择打印机、选择要打印的页面，以及在基于 Windows 的应用程序中确定其他与打印相关的设置。</span><span class="sxs-lookup"><span data-stu-id="0048e-103">The Windows Forms [PrintDialog](printdialog-component-windows-forms.md) component is a pre-configured dialog box used to select a printer, choose the pages to print, and determine other print-related settings in Windows-based applications.</span></span> <span data-ttu-id="0048e-104">将该组件用作选择打印机和打印相关设置的简单解决方案，而不用配置你自己的对话框。</span><span class="sxs-lookup"><span data-stu-id="0048e-104">Use it as a simple solution for printer and print-related settings selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="0048e-105">可以让用户打印文档的多个部分： "全部打印"、"打印选定的页范围" 或 "打印选定内容"。</span><span class="sxs-lookup"><span data-stu-id="0048e-105">You can enable users to print many parts of their documents: print all, print a selected page range, or print a selection.</span></span> <span data-ttu-id="0048e-106">利用标准的 Windows 对话框，你可以创建其基本功能可立即为用户所熟悉的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0048e-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="0048e-107"><xref:System.Windows.Forms.PrintDialog>组件继承自 <xref:System.Windows.Forms.CommonDialog> 类。</span><span class="sxs-lookup"><span data-stu-id="0048e-107">The <xref:System.Windows.Forms.PrintDialog> component inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="working-with-the-component"></a><span data-ttu-id="0048e-108">使用组件</span><span class="sxs-lookup"><span data-stu-id="0048e-108">Working with the Component</span></span>

<span data-ttu-id="0048e-109">使用 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 方法可在运行时显示该对话框。</span><span class="sxs-lookup"><span data-stu-id="0048e-109">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="0048e-110">此组件具有与单个打印作业 (<xref:System.Drawing.Printing.PrintDocument> 类) 或单个打印机 (类) 设置相关的属性 <xref:System.Drawing.Printing.PrinterSettings> 。</span><span class="sxs-lookup"><span data-stu-id="0048e-110">This component has properties that relate to either a single print job (<xref:System.Drawing.Printing.PrintDocument> class) or the settings of an individual printer (<xref:System.Drawing.Printing.PrinterSettings> class).</span></span> <span data-ttu-id="0048e-111">反过来，其中的任何一个都可以由多个打印机共享。</span><span class="sxs-lookup"><span data-stu-id="0048e-111">Either of these, in turn, may be shared by multiple printers.</span></span>

<span data-ttu-id="0048e-112">将该组件添加到窗体时，该 <xref:System.Windows.Forms.PrintDialog> 组件将出现在 Visual Studio 中 Windows 窗体设计器底部的托盘中。</span><span class="sxs-lookup"><span data-stu-id="0048e-112">When it is added to a form, the <xref:System.Windows.Forms.PrintDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="0048e-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0048e-113">See also</span></span>

- <xref:System.Windows.Forms.PrintDialog>
- [<span data-ttu-id="0048e-114">PrintDialog 组件</span><span class="sxs-lookup"><span data-stu-id="0048e-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)
