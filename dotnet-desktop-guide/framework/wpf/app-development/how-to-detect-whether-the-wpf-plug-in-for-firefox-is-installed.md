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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972704"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a>如何：检测是否已安装 Firefox 的 WPF 插件

适用于 Firefox 的 Windows Presentation Foundation (WPF) 插件使得 XAML 浏览器应用程序 (Xbap) 和松散 XAML 文件在 Mozilla Firefox 浏览器中运行。 本主题提供以 HTML 和 JavaScript 编写的脚本，管理员可以使用该脚本来确定是否安装了 Firefox 的 WPF 插件。

> [!NOTE]
> 有关安装、部署和检测 .NET Framework 的详细信息，请参阅 [为开发人员安装 .NET Framework](/dotnet/framework/install/guide-for-developers)。

## <a name="example"></a>示例

安装 .NET Framework 3.5 后，将使用用于 Firefox 的 WPF 插件配置客户端计算机。 下面的示例脚本检查 Firefox 的 WPF 插件，并显示相应的状态消息。

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

如果 Firefox 的 WPF 插件的检查成功，则会显示以下状态消息：

`The WPF plug-in for Firefox is installed.`

否则，将显示以下状态消息：

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a>请参阅

- [检测是否安装了 .NET Framework 3.0](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [检测是否安装了 .NET Framework 3.5](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [WPF XAML 浏览器应用程序概述](wpf-xaml-browser-applications-overview.md)
