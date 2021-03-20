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
# <a name="firefox-add-ons-to-support-net-application-deployment"></a><span data-ttu-id="c41d7-102">支持 .NET 应用程序部署的 Firefox 加载项</span><span class="sxs-lookup"><span data-stu-id="c41d7-102">Firefox Add-ons to Support .NET Application Deployment</span></span>
<span data-ttu-id="c41d7-103">适用于 Firefox 的 Windows Presentation Foundation (WPF) 插件和适用于 Firefox 的 .NET Framework 助手允许 XAML 浏览器应用程序 (Xbap) 、松散 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 和 ClickOnce 应用程序，以便与 Mozilla Firefox 浏览器一起使用。</span><span class="sxs-lookup"><span data-stu-id="c41d7-103">The Windows Presentation Foundation (WPF) plug-in for Firefox and the .NET Framework Assistant for Firefox enable XAML browser applications (XBAPs), loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)], and ClickOnce applications to work with the Mozilla Firefox browser.</span></span>  
  
## <a name="wpf-plug-in-for-firefox"></a><span data-ttu-id="c41d7-104">用于 Firefox 的 WPF 插件</span><span class="sxs-lookup"><span data-stu-id="c41d7-104">WPF Plug-in for Firefox</span></span>  
 <span data-ttu-id="c41d7-105">使用 Firefox 的 WPF 插件，可以在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] firefox 浏览器中导航到顶层或 HTML IFRAME 中的 xbap 和松散文件。</span><span class="sxs-lookup"><span data-stu-id="c41d7-105">The WPF plug-in for Firefox enables XBAPs and loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] files to be navigated to and run at the top-level or in an HTML IFRAME in the Firefox browser.</span></span> <span data-ttu-id="c41d7-106">XBAP 是一种 WPF 应用程序，可以将其发布到 Web 服务器并在支持的浏览器中启动该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c41d7-106">An XBAP is a WPF application that can be published to a Web server and launched within supported browsers.</span></span> <span data-ttu-id="c41d7-107">松散 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 是只能在受支持的浏览器中导航并显示的仅限 XAML 的文件，与 XML 文件非常类似。</span><span class="sxs-lookup"><span data-stu-id="c41d7-107">Loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] is a XAML-only file that can be navigated to and displayed in supported browsers, much like an XML file.</span></span>  
  
 <span data-ttu-id="c41d7-108">适用于 Firefox 的 WPF 插件与 .NET Framework 3.5 一起安装。</span><span class="sxs-lookup"><span data-stu-id="c41d7-108">The WPF plug-in for Firefox is installed with the .NET Framework 3.5.</span></span> <span data-ttu-id="c41d7-109">窗口7包含 .NET Framework 3.5，但不包括用于 Firefox 的 WPF 插件。</span><span class="sxs-lookup"><span data-stu-id="c41d7-109">Window 7 includes the .NET Framework 3.5, but does not include the WPF plug-in for Firefox.</span></span> <span data-ttu-id="c41d7-110">不能在 Windows 7 上安装适用于 Firefox 的 WPF 插件。</span><span class="sxs-lookup"><span data-stu-id="c41d7-110">You cannot install the WPF plug-in for Firefox on Windows 7.</span></span>  
  
 <span data-ttu-id="c41d7-111">.NET Framework 4 不包含用于 Firefox 的 WPF 插件。</span><span class="sxs-lookup"><span data-stu-id="c41d7-111">The .NET Framework 4 does not include the WPF plug-in for Firefox.</span></span> <span data-ttu-id="c41d7-112">但是，如果同时安装了 .NET Framework 3.5 和 .NET Framework 4，则 Firefox 的 WPF 插件将与 .NET Framework 3.5 一起安装。</span><span class="sxs-lookup"><span data-stu-id="c41d7-112">However, if both the .NET Framework 3.5 and .NET Framework 4 are installed, the WPF plug-in for Firefox is installed with the .NET Framework 3.5.</span></span> <span data-ttu-id="c41d7-113">因此 .NET Framework 4 应用程序仍将运行，因为 WPF 主机将加载正确的框架版本。</span><span class="sxs-lookup"><span data-stu-id="c41d7-113">Therefore .NET Framework 4 applications will still run because the WPF Host will load the correct version of the framework.</span></span> <span data-ttu-id="c41d7-114">有关详细信息，请参阅 [WPF 主机 (PresentationHost.exe) ](wpf-host-presentationhost-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="c41d7-114">For more information, see [WPF Host (PresentationHost.exe)](wpf-host-presentationhost-exe.md).</span></span>  
  
## <a name="net-framework-assistant-for-firefox"></a><span data-ttu-id="c41d7-115">.NET Framework Assistant for Firefox</span><span class="sxs-lookup"><span data-stu-id="c41d7-115">.NET Framework Assistant for Firefox</span></span>  
 <span data-ttu-id="c41d7-116">用于 Firefox 的 .NET Framework 助手允许独立的 ClickOnce 应用程序从 Firefox 浏览器运行。</span><span class="sxs-lookup"><span data-stu-id="c41d7-116">The .NET Framework Assistant for Firefox enables stand-alone ClickOnce applications to run from the Firefox browser.</span></span> <span data-ttu-id="c41d7-117">当 firefox 在 Firefox 浏览器之前和之后安装时，Firefox 函数的 .NET Framework 助手就是相同的。</span><span class="sxs-lookup"><span data-stu-id="c41d7-117">The .NET Framework Assistant for Firefox functions identically when it is installed before and after the Firefox browser.</span></span> <span data-ttu-id="c41d7-118">启动 Firefox 浏览器并安装 .NET Framework 3.5 SP1 后，Firefox 将查找并安装适用于 Firefox 的 .NET Framework 助手。</span><span class="sxs-lookup"><span data-stu-id="c41d7-118">When the Firefox browser is launched and the .NET Framework 3.5 SP1 is installed, Firefox finds and installs the .NET Framework Assistant for Firefox.</span></span> <span data-ttu-id="c41d7-119">用户可以将 Firefox 的 .NET Framework 助手配置为执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c41d7-119">Users can configure the .NET Framework Assistant for Firefox to do the following:</span></span>  
  
- <span data-ttu-id="c41d7-120">运行 ClickOnce 应用程序之前进行提示。</span><span class="sxs-lookup"><span data-stu-id="c41d7-120">Prompt before running the ClickOnce application.</span></span>  
  
- <span data-ttu-id="c41d7-121">报告 .NET Framework 的所有安装版本或仅报告最新版本。</span><span class="sxs-lookup"><span data-stu-id="c41d7-121">Report all installed versions of the .NET Framework or just the latest version.</span></span>  
  
 <span data-ttu-id="c41d7-122">适用于 Firefox 的 .NET Framework 助手包含在 .NET Framework 3.5 SP1 中。</span><span class="sxs-lookup"><span data-stu-id="c41d7-122">The .NET Framework Assistant for Firefox is included with the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="c41d7-123">有关删除 Firefox .NET Framework 助手的信息，请参阅 [如何删除 firefox 的 .NET Framework 助手](https://support.microsoft.com/help/963707/how-to-remove-the-net-framework-assistant-for-firefox)。</span><span class="sxs-lookup"><span data-stu-id="c41d7-123">For information about removing the .NET Framework Assistant for Firefox, see [How to remove the .NET Framework Assistant for Firefox](https://support.microsoft.com/help/963707/how-to-remove-the-net-framework-assistant-for-firefox).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c41d7-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="c41d7-124">See also</span></span>

- [<span data-ttu-id="c41d7-125">部署 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="c41d7-125">Deploying a WPF Application</span></span>](deploying-a-wpf-application-wpf.md)
- [<span data-ttu-id="c41d7-126">WPF XAML 浏览器应用程序概述</span><span class="sxs-lookup"><span data-stu-id="c41d7-126">WPF XAML Browser Applications Overview</span></span>](wpf-xaml-browser-applications-overview.md)
- [<span data-ttu-id="c41d7-127">检测是否安装了适用于 Firefox 的 WPF 插件</span><span class="sxs-lookup"><span data-stu-id="c41d7-127">Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>](how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)
