---
title: PrintDocument 组件概述
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: 96b18a44853d836cb0f16ba0e8372a825e998b74
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971063"
---
# <a name="printdocument-component-overview-windows-forms"></a><span data-ttu-id="fad14-102">PrintDocument 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="fad14-102">PrintDocument Component Overview (Windows Forms)</span></span>

<span data-ttu-id="fad14-103">Windows 窗体 [PrintDocument](printdocument-component-windows-forms.md) 组件用于设置属性，这些属性描述在基于 Windows 的应用程序中要打印什么内容以及打印文档的能力。</span><span class="sxs-lookup"><span data-stu-id="fad14-103">The Windows Forms [PrintDocument](printdocument-component-windows-forms.md) component is used to set the properties that describe what to print and the ability to print the document within Windows-based applications.</span></span> <span data-ttu-id="fad14-104">此组件可与 [PrintDialog](printdialog-component-windows-forms.md) 组件一起使用，控制文档打印的各个方面。</span><span class="sxs-lookup"><span data-stu-id="fad14-104">It can be used in conjunction with the [PrintDialog](printdialog-component-windows-forms.md) component to be in control of all aspects of document printing.</span></span>

## <a name="working-with-the-printdocument-component"></a><span data-ttu-id="fad14-105">使用 PrintDocument 组件</span><span class="sxs-lookup"><span data-stu-id="fad14-105">Working with the PrintDocument Component</span></span>

<span data-ttu-id="fad14-106">涉及组件的两个主要方案 <xref:System.Drawing.Printing.PrintDocument> 是：</span><span class="sxs-lookup"><span data-stu-id="fad14-106">Two of the main scenarios that involve the <xref:System.Drawing.Printing.PrintDocument> component are:</span></span>

- <span data-ttu-id="fad14-107">简单的打印作业，如打印单个文本文件。</span><span class="sxs-lookup"><span data-stu-id="fad14-107">Simple print jobs, such as printing an individual text file.</span></span> <span data-ttu-id="fad14-108">在这种情况下，您需要将 <xref:System.Drawing.Printing.PrintDocument> 组件添加到 Windows 窗体中，然后添加在 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 事件处理程序中打印文件的编程逻辑。</span><span class="sxs-lookup"><span data-stu-id="fad14-108">In such a case you would add the <xref:System.Drawing.Printing.PrintDocument> component to a Windows Form, then add programming logic that prints a file in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler.</span></span> <span data-ttu-id="fad14-109">编程逻辑应形成 <xref:System.Drawing.Printing.PrintDocument.Print%2A> 用于打印文档的方法。</span><span class="sxs-lookup"><span data-stu-id="fad14-109">The programming logic should culminate with the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to print the document.</span></span> <span data-ttu-id="fad14-110">此方法将 <xref:System.Drawing.Graphics> 包含在类的属性中的对象发送 <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> <xref:System.Drawing.Printing.PrintPageEventArgs> 到打印机。</span><span class="sxs-lookup"><span data-stu-id="fad14-110">This method sends a <xref:System.Drawing.Graphics> object, contained in the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class, to the printer.</span></span> <span data-ttu-id="fad14-111">有关演示如何使用组件打印文本文档的示例 <xref:System.Drawing.Printing.PrintDocument> ，请参阅 [如何：在 Windows 窗体中打印多页文本文件](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="fad14-111">For an example that shows how to print a text document using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print a Multi-Page Text File in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span></span>

- <span data-ttu-id="fad14-112">更复杂的打印作业，如想要重新使用已编写的打印逻辑的情况。</span><span class="sxs-lookup"><span data-stu-id="fad14-112">More complex print jobs, such as a situation where you will want to reuse printing logic you have written.</span></span> <span data-ttu-id="fad14-113">在这种情况下，你将从组件派生新组件 <xref:System.Drawing.Printing.PrintDocument> 并重写 (请参阅 c # 的 [替代](/dotnet/visual-basic/language-reference/modifiers/overrides) Visual Basic 或 [重写](/dotnet/csharp/language-reference/keywords/override) ) <xref:System.Drawing.Printing.PrintDocument.PrintPage> 事件。</span><span class="sxs-lookup"><span data-stu-id="fad14-113">In such a case you would derive a new component from the <xref:System.Drawing.Printing.PrintDocument> component and override (see [Overrides](/dotnet/visual-basic/language-reference/modifiers/overrides) for Visual Basic or [override](/dotnet/csharp/language-reference/keywords/override) for C#) the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>

<span data-ttu-id="fad14-114">将该组件添加到窗体时，该 <xref:System.Drawing.Printing.PrintDocument> 组件将出现在 Visual Studio 中 Windows 窗体设计器底部的托盘中。</span><span class="sxs-lookup"><span data-stu-id="fad14-114">When it is added to a form, the <xref:System.Drawing.Printing.PrintDocument> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="fad14-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fad14-115">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="fad14-116">Windows 窗体打印支持</span><span class="sxs-lookup"><span data-stu-id="fad14-116">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="fad14-117">PrintDocument 组件</span><span class="sxs-lookup"><span data-stu-id="fad14-117">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
