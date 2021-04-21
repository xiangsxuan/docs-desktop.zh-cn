---
title: Windows 窗体的新增功能
description: 了解.NET 的 Windows 窗体中的新增功能。 Windows 窗体。 .NET 提供优于 .NET Framework 的新功能和增强功能。
ms.date: 11/05/2020
ms.topic: conceptual
ms.openlocfilehash: 5c22fdd2df68cd59b7bc0b93c6aa7223bdf06ec0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96992772"
---
# <a name="whats-new-windows-forms-net"></a><span data-ttu-id="07b82-105">新增功能（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="07b82-105">What's new (Windows Forms .NET)</span></span>

<span data-ttu-id="07b82-106">.NET 5.0 的 Windows 窗体添加了以下优于 .NET Framework 的功能和增强功能。</span><span class="sxs-lookup"><span data-stu-id="07b82-106">Windows Forms for .NET 5.0 adds the following features and enhancements over .NET Framework.</span></span>

<span data-ttu-id="07b82-107">从 .NET Framework 迁移到 .NET 5.0 时，应注意一些重大更改。</span><span class="sxs-lookup"><span data-stu-id="07b82-107">There are a few breaking changes you should be aware of when migrating from .NET Framework to .NET 5.0.</span></span> <span data-ttu-id="07b82-108">有关详细信息，请参阅 [Windows 窗体中的重大更改](/dotnet/core/compatibility/winforms)。</span><span class="sxs-lookup"><span data-stu-id="07b82-108">For more information, see [Breaking changes in Windows Forms](/dotnet/core/compatibility/winforms).</span></span>

## <a name="enhanced-features"></a><span data-ttu-id="07b82-109">增强功能</span><span class="sxs-lookup"><span data-stu-id="07b82-109">Enhanced features</span></span>

- <span data-ttu-id="07b82-110">Microsoft UI 自动化模式可更好地与讲述人和 Jaws 等辅助工具协同工作。</span><span class="sxs-lookup"><span data-stu-id="07b82-110">Microsoft UI Automation patterns work better with accessibility tools like Narrator and Jaws.</span></span>
- <span data-ttu-id="07b82-111">提高了性能。</span><span class="sxs-lookup"><span data-stu-id="07b82-111">Improved performance.</span></span>
- <span data-ttu-id="07b82-112">对于高 DPI 分辨率（如 4k 监视器），VB.NET 项目模板默认使用 DPI SystemAware 设置。</span><span class="sxs-lookup"><span data-stu-id="07b82-112">The VB.NET project template defaults to DPI SystemAware settings for high DPI resolutions such as 4k monitors.</span></span>
- <span data-ttu-id="07b82-113">默认字体与当前 Windows 设计建议相符。</span><span class="sxs-lookup"><span data-stu-id="07b82-113">The default font matches the current Windows design recommendations.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="07b82-114">这可能会影响从 .NET Framework 迁移的应用的布局。</span><span class="sxs-lookup"><span data-stu-id="07b82-114">This may impact the layout of apps migrated from .NET Framework.</span></span>

## <a name="new-controls"></a><span data-ttu-id="07b82-115">新控件</span><span class="sxs-lookup"><span data-stu-id="07b82-115">New controls</span></span>

<span data-ttu-id="07b82-116">将 Windows 窗体移植到 .NET Framework 后，添加了以下控件：</span><span class="sxs-lookup"><span data-stu-id="07b82-116">The following controls have been added since Windows Forms was ported to .NET Framework:</span></span>

- <xref:System.Windows.Forms.TaskDialog?displayProperty=fullName>
  
  <span data-ttu-id="07b82-117">任务对话框是可用于显示信息并接收用户的简单输入的文本框。</span><span class="sxs-lookup"><span data-stu-id="07b82-117">A task dialog is a dialog box that can be used to display information and receive simple input from the user.</span></span> <span data-ttu-id="07b82-118">与消息框类似，其格式由操作系统根据你设置的参数进行设置。</span><span class="sxs-lookup"><span data-stu-id="07b82-118">Like a message box, it's formatted by the operating system according to parameters you set.</span></span> <span data-ttu-id="07b82-119">任务对话框具有比消息框更多的功能。</span><span class="sxs-lookup"><span data-stu-id="07b82-119">Task dialog has more features than a message box.</span></span> <span data-ttu-id="07b82-120">有关详细信息，请参阅[任务对话框示例](https://github.com/dotnet/samples/tree/master/windowsforms/TaskDialogDemo)。</span><span class="sxs-lookup"><span data-stu-id="07b82-120">For more information, see the [Task dialog sample](https://github.com/dotnet/samples/tree/master/windowsforms/TaskDialogDemo).</span></span>

- <xref:Microsoft.Web.WebView2.WinForms.WebView2?displayProperty=fullName>

  <span data-ttu-id="07b82-121">具有新式 Web 支持的新 Web 浏览器控件。</span><span class="sxs-lookup"><span data-stu-id="07b82-121">A new web browser control with modern web support.</span></span> <span data-ttu-id="07b82-122">基于 Microsoft Edge (Chromium)。</span><span class="sxs-lookup"><span data-stu-id="07b82-122">Based on Edge (Chromium).</span></span> <span data-ttu-id="07b82-123">有关详细信息，请参阅 [Windows 窗体中的 WebView2 入门](/microsoft-edge/webview2/gettingstarted/winforms)。</span><span class="sxs-lookup"><span data-stu-id="07b82-123">For more information, see [Getting started with WebView2 in Windows Forms](/microsoft-edge/webview2/gettingstarted/winforms).</span></span>

## <a name="enhanced-controls"></a><span data-ttu-id="07b82-124">增强的控件</span><span class="sxs-lookup"><span data-stu-id="07b82-124">Enhanced controls</span></span>

- <xref:System.Windows.Forms.ListView?displayProperty=fullName>

  - <span data-ttu-id="07b82-125">支持可折叠的组</span><span class="sxs-lookup"><span data-stu-id="07b82-125">Supports collapsible groups</span></span>
  - <span data-ttu-id="07b82-126">页脚</span><span class="sxs-lookup"><span data-stu-id="07b82-126">Footers</span></span>
  - <span data-ttu-id="07b82-127">组副标题、任务和标题图像</span><span class="sxs-lookup"><span data-stu-id="07b82-127">Group subtitle, task, and title images</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog?displayProperty=fullName>

  <span data-ttu-id="07b82-128">此对话框已升级为使用新式 Windows 体验，而不是旧版 Windows 7 体验。</span><span class="sxs-lookup"><span data-stu-id="07b82-128">This dialog has been upgraded to use the modern Windows experience instead of the old Windows 7 experience.</span></span>

- <xref:System.Windows.Forms.FileDialog?displayProperty=fullName>

  - <span data-ttu-id="07b82-129">增加了对 <xref:System.Windows.Forms.FileDialog.ClientGuid> 的支持。</span><span class="sxs-lookup"><span data-stu-id="07b82-129">Added support for <xref:System.Windows.Forms.FileDialog.ClientGuid>.</span></span>

    <span data-ttu-id="07b82-130">`ClientGuid` 支持调用应用程序，以将 GUID 与对话框的持久状态关联。</span><span class="sxs-lookup"><span data-stu-id="07b82-130">`ClientGuid` enables a calling application to associate a GUID with a dialog's persisted state.</span></span> <span data-ttu-id="07b82-131">对话框的状态可能包括最后访问的文件夹以及对话框的位置和大小等因素。</span><span class="sxs-lookup"><span data-stu-id="07b82-131">A dialog's state can include factors such as the last visited folder and the position and size of the dialog.</span></span> <span data-ttu-id="07b82-132">通常，此状态根据可执行文件的名称持久保留。</span><span class="sxs-lookup"><span data-stu-id="07b82-132">Typically, this state is persisted based on the name of the executable file.</span></span> <span data-ttu-id="07b82-133">使用 `ClientGuid`，应用程序可以在同一应用程序中保持对话框的不同状态。</span><span class="sxs-lookup"><span data-stu-id="07b82-133">With `ClientGuid`, an application can persist  different states of the dialog within the same application.</span></span>

- <xref:System.Windows.Forms.TextRenderer?displayProperty=fullName>

  <span data-ttu-id="07b82-134">添加了对 <xref:System.ReadOnlySpan%601> 的支持，以增强呈现文本的性能。</span><span class="sxs-lookup"><span data-stu-id="07b82-134">Support added for <xref:System.ReadOnlySpan%601> to enhance performance of rendering text.</span></span>

## <a name="see-also"></a><span data-ttu-id="07b82-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07b82-135">See also</span></span>

- [<span data-ttu-id="07b82-136">Windows 窗体中的中断性变更</span><span class="sxs-lookup"><span data-stu-id="07b82-136">Breaking changes in Windows Forms</span></span>](/dotnet/core/compatibility/winforms)
- [<span data-ttu-id="07b82-137">教程：创建新的 WinForms 应用（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="07b82-137">Tutorial: Create a new WinForms app (Windows Forms .NET)</span></span>](../get-started/create-app-visual-studio.md)
- [<span data-ttu-id="07b82-138">如何将 Windows 窗体桌面应用迁移到 .NET 5</span><span class="sxs-lookup"><span data-stu-id="07b82-138">How to migrate a Windows Forms desktop app to .NET 5</span></span>](../migration/index.md)
