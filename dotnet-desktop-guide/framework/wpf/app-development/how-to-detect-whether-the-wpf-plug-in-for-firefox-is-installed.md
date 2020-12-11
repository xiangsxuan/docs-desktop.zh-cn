---
title: 检测是否已安装 Firefox 的 WPF Plug-In
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: ed16f98b992f4c1a0cea3e13a0ab29d630789a67
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972704"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="82704-102">如何：检测是否已安装 Firefox 的 WPF 插件</span><span class="sxs-lookup"><span data-stu-id="82704-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>

<span data-ttu-id="82704-103">适用于 Firefox 的 Windows Presentation Foundation (WPF) 插件使得 XAML 浏览器应用程序 (Xbap) 和松散 XAML 文件在 Mozilla Firefox 浏览器中运行。</span><span class="sxs-lookup"><span data-stu-id="82704-103">The Windows Presentation Foundation (WPF) plug-in for Firefox enables XAML browser applications (XBAPs) and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="82704-104">本主题提供以 HTML 和 JavaScript 编写的脚本，管理员可以使用该脚本来确定是否安装了 Firefox 的 WPF 插件。</span><span class="sxs-lookup"><span data-stu-id="82704-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>

> [!NOTE]
> <span data-ttu-id="82704-105">有关安装、部署和检测 .NET Framework 的详细信息，请参阅 [为开发人员安装 .NET Framework](/dotnet/framework/install/guide-for-developers)。</span><span class="sxs-lookup"><span data-stu-id="82704-105">For more information about installing, deploying, and detecting the .NET Framework, see [Install the .NET Framework for developers](/dotnet/framework/install/guide-for-developers).</span></span>

## <a name="example"></a><span data-ttu-id="82704-106">示例</span><span class="sxs-lookup"><span data-stu-id="82704-106">Example</span></span>

<span data-ttu-id="82704-107">安装 .NET Framework 3.5 后，将使用用于 Firefox 的 WPF 插件配置客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="82704-107">When the .NET Framework 3.5 is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="82704-108">下面的示例脚本检查 Firefox 的 WPF 插件，并显示相应的状态消息。</span><span class="sxs-lookup"><span data-stu-id="82704-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>

```html
<HTML>

  <HEAD>
    <TITLE>Test for the WPF plug-in for Firefox</TITLE>
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />
    <SCRIPT type="text/javascript">
    <!--
    function OnLoad()
    {

       // Check for the WPF plug-in for Firefox and report
       var msg = "The WPF plug-in for Firefox is ";
       var wpfPlugin = navigator.plugins["Windows Presentation Foundation"];
       if( wpfPlugin != null ) {
          document.writeln(msg + " installed.");
       }
       else {
          document.writeln(msg + " not installed. Please install or reinstall the .NET Framework 3.5.");
       }
    }
    -->
    </SCRIPT>
  </HEAD>

  <BODY onload="OnLoad()" />

</HTML>
```

<span data-ttu-id="82704-109">如果 Firefox 的 WPF 插件的检查成功，则会显示以下状态消息：</span><span class="sxs-lookup"><span data-stu-id="82704-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is installed.`

<span data-ttu-id="82704-110">否则，将显示以下状态消息：</span><span class="sxs-lookup"><span data-stu-id="82704-110">Otherwise, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a><span data-ttu-id="82704-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82704-111">See also</span></span>

- [<span data-ttu-id="82704-112">检测是否安装了 .NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="82704-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [<span data-ttu-id="82704-113">检测是否安装了 .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="82704-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [<span data-ttu-id="82704-114">WPF XAML 浏览器应用程序概述</span><span class="sxs-lookup"><span data-stu-id="82704-114">WPF XAML Browser Applications Overview</span></span>](wpf-xaml-browser-applications-overview.md)
