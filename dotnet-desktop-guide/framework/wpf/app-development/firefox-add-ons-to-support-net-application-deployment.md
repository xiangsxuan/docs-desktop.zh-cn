---
title: 支持 .NET 应用程序部署的 Firefox 加载项
ms.date: 03/30/2017
helpviewer_keywords:
- Firefox add-ons for .NET application deployment
- WPF plug-in for Firefox
- .NET application deployment [WPF], deploying with Firefox add-ons
- .NET Framework Assistant for Firefox
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
ms.openlocfilehash: b20471e6ef39171436824c6f88d9f728b4efcd6c
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667858"
---
# <a name="firefox-add-ons-to-support-net-application-deployment"></a>支持 .NET 应用程序部署的 Firefox 加载项
适用于 Firefox 的 Windows Presentation Foundation (WPF) 插件和适用于 Firefox 的 .NET Framework 助手允许 XAML 浏览器应用程序 (Xbap) 、松散 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 和 ClickOnce 应用程序，以便与 Mozilla Firefox 浏览器一起使用。  
  
## <a name="wpf-plug-in-for-firefox"></a>用于 Firefox 的 WPF 插件  
 使用 Firefox 的 WPF 插件，可以在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] firefox 浏览器中导航到顶层或 HTML IFRAME 中的 xbap 和松散文件。 XBAP 是一种 WPF 应用程序，可以将其发布到 Web 服务器并在支持的浏览器中启动该应用程序。 松散 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 是只能在受支持的浏览器中导航并显示的仅限 XAML 的文件，与 XML 文件非常类似。  
  
 适用于 Firefox 的 WPF 插件与 .NET Framework 3.5 一起安装。 窗口7包含 .NET Framework 3.5，但不包括用于 Firefox 的 WPF 插件。 不能在 Windows 7 上安装适用于 Firefox 的 WPF 插件。  
  
 .NET Framework 4 不包含用于 Firefox 的 WPF 插件。 但是，如果同时安装了 .NET Framework 3.5 和 .NET Framework 4，则 Firefox 的 WPF 插件将与 .NET Framework 3.5 一起安装。 因此 .NET Framework 4 应用程序仍将运行，因为 WPF 主机将加载正确的框架版本。 有关详细信息，请参阅 [WPF 主机 (PresentationHost.exe) ](wpf-host-presentationhost-exe.md)。  
  
## <a name="net-framework-assistant-for-firefox"></a>.NET Framework Assistant for Firefox  
 用于 Firefox 的 .NET Framework 助手允许独立的 ClickOnce 应用程序从 Firefox 浏览器运行。 当 firefox 在 Firefox 浏览器之前和之后安装时，Firefox 函数的 .NET Framework 助手就是相同的。 启动 Firefox 浏览器并安装 .NET Framework 3.5 SP1 后，Firefox 将查找并安装适用于 Firefox 的 .NET Framework 助手。 用户可以将 Firefox 的 .NET Framework 助手配置为执行以下操作：  
  
- 运行 ClickOnce 应用程序之前进行提示。  
  
- 报告 .NET Framework 的所有安装版本或仅报告最新版本。  
  
 适用于 Firefox 的 .NET Framework 助手包含在 .NET Framework 3.5 SP1 中。 有关删除 Firefox .NET Framework 助手的信息，请参阅 [如何删除 firefox 的 .NET Framework 助手](https://support.microsoft.com/help/963707/how-to-remove-the-net-framework-assistant-for-firefox)。  
  
## <a name="see-also"></a>请参阅

- [部署 WPF 应用程序](deploying-a-wpf-application-wpf.md)
- [WPF XAML 浏览器应用程序概述](wpf-xaml-browser-applications-overview.md)
- [检测是否安装了适用于 Firefox 的 WPF 插件](how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)
