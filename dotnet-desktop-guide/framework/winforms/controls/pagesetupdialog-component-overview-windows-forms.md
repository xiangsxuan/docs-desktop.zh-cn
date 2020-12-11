---
title: PageSetupDialog 组件概述
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: a891cb8cc77007d7591d41461c94f61c077eb300
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972589"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a><span data-ttu-id="23817-102">PageSetupDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="23817-102">PageSetupDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="23817-103">Windows 窗体 <xref:System.Windows.Forms.PageSetupDialog> 组件是一个预先配置的对话框，用于在基于 Windows 的应用程序中设置用于打印的页面详细信息。</span><span class="sxs-lookup"><span data-stu-id="23817-103">The Windows Forms <xref:System.Windows.Forms.PageSetupDialog> component is a pre-configured dialog box used to set page details for printing in Windows-based applications.</span></span> <span data-ttu-id="23817-104">在基于 Windows 的应用程序中使用它作为一种简单的解决方案，用户可以使用它来设置页面首选项，而不是配置自己的对话框。</span><span class="sxs-lookup"><span data-stu-id="23817-104">Use it within your Windows-based application as a simple solution for users to set page preferences in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="23817-105">可以让用户设置边框和边距调整、页眉和页脚以及纵向或横向方向。</span><span class="sxs-lookup"><span data-stu-id="23817-105">You can enable users to set border and margin adjustments, headers and footers, and portrait or landscape orientation.</span></span> <span data-ttu-id="23817-106">利用标准的 Windows 对话框，你可以创建其基本功能可立即为用户所熟悉的应用程序。</span><span class="sxs-lookup"><span data-stu-id="23817-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span>

## <a name="key-properties-and-methods"></a><span data-ttu-id="23817-107">键属性和方法</span><span class="sxs-lookup"><span data-stu-id="23817-107">Key Properties and Methods</span></span>

<span data-ttu-id="23817-108">使用 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 方法可在运行时显示对话框。</span><span class="sxs-lookup"><span data-stu-id="23817-108">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="23817-109">此组件具有可设置的属性，这些属性与单个页面 (<xref:System.Drawing.Printing.PrintDocument> 类) 或任何文档 (<xref:System.Drawing.Printing.PageSettings> 类) 相关。</span><span class="sxs-lookup"><span data-stu-id="23817-109">This component has properties you can set that relate to either a single page (<xref:System.Drawing.Printing.PrintDocument> class) or any document (<xref:System.Drawing.Printing.PageSettings> class).</span></span> <span data-ttu-id="23817-110">此外，该 <xref:System.Windows.Forms.PageSetupDialog> 组件可用于确定存储在类中的特定打印机设置 <xref:System.Drawing.Printing.PrinterSettings> 。</span><span class="sxs-lookup"><span data-stu-id="23817-110">Additionally, the <xref:System.Windows.Forms.PageSetupDialog> component can be used to determine specific printer settings, which are stored in the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span>

<span data-ttu-id="23817-111">将该组件添加到窗体时，该 <xref:System.Windows.Forms.PageSetupDialog> 组件将出现在 Visual Studio 中 Windows 窗体设计器底部的托盘中。</span><span class="sxs-lookup"><span data-stu-id="23817-111">When it is added to a form, the <xref:System.Windows.Forms.PageSetupDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="23817-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23817-112">See also</span></span>

- <xref:System.Windows.Forms.PageSetupDialog>
- [<span data-ttu-id="23817-113">PageSetupDialog 组件</span><span class="sxs-lookup"><span data-stu-id="23817-113">PageSetupDialog Component</span></span>](pagesetupdialog-component-windows-forms.md)
