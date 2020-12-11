---
title: PrintPreviewDialog 控件概述
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
ms.openlocfilehash: c7576beb56cd10a691a850969c132a2d33ad8870
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970301"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="69a31-102">PrintPreviewDialog 控件概述 (Windows 窗体) </span><span class="sxs-lookup"><span data-stu-id="69a31-102">PrintPreviewDialog control overview (Windows Forms)</span></span>

<span data-ttu-id="69a31-103">Windows 窗体 <xref:System.Windows.Forms.PrintPreviewDialog> 控件是一个预先配置的对话框，用于显示在打印时 [PrintDocument](printdocument-component-windows-forms.md) 的显示方式。</span><span class="sxs-lookup"><span data-stu-id="69a31-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="69a31-104">在基于 Windows 的应用程序中将其用作简单的解决方案，而不是配置自己的对话框。</span><span class="sxs-lookup"><span data-stu-id="69a31-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="69a31-105">该控件包含用于打印、放大、显示一页或多页以及关闭对话框的按钮。</span><span class="sxs-lookup"><span data-stu-id="69a31-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>

## <a name="key-properties-and-methods"></a><span data-ttu-id="69a31-106">键属性和方法</span><span class="sxs-lookup"><span data-stu-id="69a31-106">Key properties and methods</span></span>

<span data-ttu-id="69a31-107">控件的键属性为 <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> ，用于设置要预览的文档。</span><span class="sxs-lookup"><span data-stu-id="69a31-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="69a31-108">文档必须为 <xref:System.Drawing.Printing.PrintDocument> 对象。</span><span class="sxs-lookup"><span data-stu-id="69a31-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="69a31-109">若要显示该对话框，必须调用其 <xref:System.Windows.Forms.Form.ShowDialog%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="69a31-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="69a31-110">抗锯齿会使文本看起来更流畅，但也可以使显示速度变慢;若要使用它，请将 <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> 属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="69a31-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>

<span data-ttu-id="69a31-111">某些属性可通过包含的 <xref:System.Windows.Forms.PrintPreviewControl> 来获取 <xref:System.Windows.Forms.PrintPreviewDialog> 。</span><span class="sxs-lookup"><span data-stu-id="69a31-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="69a31-112"> (无需将 <xref:System.Windows.Forms.PrintPreviewControl> 其添加到窗体中， <xref:System.Windows.Forms.PrintPreviewDialog> 当你将此对话框添加到窗体时，它将自动包含在中。 ) 可通过提供的属性示例 <xref:System.Windows.Forms.PrintPreviewControl> 是 <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 和 <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> 属性，可确定控件上水平和垂直显示的页数。</span><span class="sxs-lookup"><span data-stu-id="69a31-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="69a31-113">可以 <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> `PrintPreviewDialog1.PrintPreviewControl.Columns` Visual Basic、 `printPreviewDialog1.PrintPreviewControl.Columns` Visual c # 或 Visual C++ 中访问属性 `printPreviewDialog1->PrintPreviewControl->Columns` 。</span><span class="sxs-lookup"><span data-stu-id="69a31-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#, or `printPreviewDialog1->PrintPreviewControl->Columns` in Visual C++.</span></span>

## <a name="printpreviewdialog-performance"></a><span data-ttu-id="69a31-114">PrintPreviewDialog 性能</span><span class="sxs-lookup"><span data-stu-id="69a31-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="69a31-115">在以下条件下， <xref:System.Windows.Forms.PrintPreviewDialog> 控件的初始化速度非常慢：</span><span class="sxs-lookup"><span data-stu-id="69a31-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="69a31-116">使用网络打印机。</span><span class="sxs-lookup"><span data-stu-id="69a31-116">A network printer is used.</span></span>
- <span data-ttu-id="69a31-117">此打印机的用户首选项（如双工设置）会被修改。</span><span class="sxs-lookup"><span data-stu-id="69a31-117">User preferences for this printer, such as duplex settings, are modified.</span></span>

<span data-ttu-id="69a31-118">对于在 .NET Framework 4.5.2 上运行的应用，可以在配置文件的节中添加以下键， \<appSettings> 以提高控件初始化的性能 <xref:System.Windows.Forms.PrintPreviewDialog> ：</span><span class="sxs-lookup"><span data-stu-id="69a31-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

<span data-ttu-id="69a31-119">如果 `EnablePrintPreviewOptimization` 该键设置为任何其他值，或者该键不存在，则不会应用优化。</span><span class="sxs-lookup"><span data-stu-id="69a31-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="69a31-120">对于在 .NET Framework 4.6 或更高版本上运行的应用，你可以将以下开关添加到 [\<AppContextSwitchOverrides>](/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) [\<runtime>](/dotnet/framework/configure-apps/file-schema/runtime/index) 应用配置文件的部分中的元素：</span><span class="sxs-lookup"><span data-stu-id="69a31-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) element in the [\<runtime>](/dotnet/framework/configure-apps/file-schema/runtime/index) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

<span data-ttu-id="69a31-121">如果此开关不存在或者设置为任何其他值，则不会应用优化。</span><span class="sxs-lookup"><span data-stu-id="69a31-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span>

<span data-ttu-id="69a31-122">如果使用 <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> 事件修改打印机设置，则 <xref:System.Windows.Forms.PrintPreviewDialog> 即使设置了优化配置开关，控件的性能也不会提高。</span><span class="sxs-lookup"><span data-stu-id="69a31-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>

## <a name="see-also"></a><span data-ttu-id="69a31-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69a31-123">See also</span></span>

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [<span data-ttu-id="69a31-124">PrintPreviewControl 控件概述</span><span class="sxs-lookup"><span data-stu-id="69a31-124">PrintPreviewControl Control Overview</span></span>](printpreviewcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="69a31-125">PrintPreviewDialog 控件</span><span class="sxs-lookup"><span data-stu-id="69a31-125">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="69a31-126">对话框控件和组件</span><span class="sxs-lookup"><span data-stu-id="69a31-126">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
