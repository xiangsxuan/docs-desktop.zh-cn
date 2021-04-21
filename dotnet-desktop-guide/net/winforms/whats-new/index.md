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
# <a name="whats-new-windows-forms-net"></a>新增功能（Windows 窗体 .NET）

.NET 5.0 的 Windows 窗体添加了以下优于 .NET Framework 的功能和增强功能。

从 .NET Framework 迁移到 .NET 5.0 时，应注意一些重大更改。 有关详细信息，请参阅 [Windows 窗体中的重大更改](/dotnet/core/compatibility/winforms)。

## <a name="enhanced-features"></a>增强功能

- Microsoft UI 自动化模式可更好地与讲述人和 Jaws 等辅助工具协同工作。
- 提高了性能。
- 对于高 DPI 分辨率（如 4k 监视器），VB.NET 项目模板默认使用 DPI SystemAware 设置。
- 默认字体与当前 Windows 设计建议相符。

  > [!CAUTION]
  > 这可能会影响从 .NET Framework 迁移的应用的布局。

## <a name="new-controls"></a>新控件

将 Windows 窗体移植到 .NET Framework 后，添加了以下控件：

- <xref:System.Windows.Forms.TaskDialog?displayProperty=fullName>
  
  任务对话框是可用于显示信息并接收用户的简单输入的文本框。 与消息框类似，其格式由操作系统根据你设置的参数进行设置。 任务对话框具有比消息框更多的功能。 有关详细信息，请参阅[任务对话框示例](https://github.com/dotnet/samples/tree/master/windowsforms/TaskDialogDemo)。

- <xref:Microsoft.Web.WebView2.WinForms.WebView2?displayProperty=fullName>

  具有新式 Web 支持的新 Web 浏览器控件。 基于 Microsoft Edge (Chromium)。 有关详细信息，请参阅 [Windows 窗体中的 WebView2 入门](/microsoft-edge/webview2/gettingstarted/winforms)。

## <a name="enhanced-controls"></a>增强的控件

- <xref:System.Windows.Forms.ListView?displayProperty=fullName>

  - 支持可折叠的组
  - 页脚
  - 组副标题、任务和标题图像

- <xref:System.Windows.Forms.FolderBrowserDialog?displayProperty=fullName>

  此对话框已升级为使用新式 Windows 体验，而不是旧版 Windows 7 体验。

- <xref:System.Windows.Forms.FileDialog?displayProperty=fullName>

  - 增加了对 <xref:System.Windows.Forms.FileDialog.ClientGuid> 的支持。

    `ClientGuid` 支持调用应用程序，以将 GUID 与对话框的持久状态关联。 对话框的状态可能包括最后访问的文件夹以及对话框的位置和大小等因素。 通常，此状态根据可执行文件的名称持久保留。 使用 `ClientGuid`，应用程序可以在同一应用程序中保持对话框的不同状态。

- <xref:System.Windows.Forms.TextRenderer?displayProperty=fullName>

  添加了对 <xref:System.ReadOnlySpan%601> 的支持，以增强呈现文本的性能。

## <a name="see-also"></a>另请参阅

- [Windows 窗体中的中断性变更](/dotnet/core/compatibility/winforms)
- [教程：创建新的 WinForms 应用（Windows 窗体 .NET）](../get-started/create-app-visual-studio.md)
- [如何将 Windows 窗体桌面应用迁移到 .NET 5](../migration/index.md)
