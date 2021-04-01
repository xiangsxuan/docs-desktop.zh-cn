---
title: 如何：配置 Visual Studio 以调试 XAML 浏览器应用程序来调用 Web 服务
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: d8cfae2fb47876d578c51e5f4acdfe0c31e752fe
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973624"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>如何：配置 Visual Studio 以调试 XAML 浏览器应用程序来调用 Web 服务
XAML 浏览器应用程序 (Xbap) 在仅限于 Internet 区域权限集的部分信任的安全沙盒中运行。 此权限集将 Web 服务调用限制为仅位于 XBAP 应用程序源站点上的 Web 服务。 不过，当从 Visual Studio 2005 调试 XBAP 时，它不会被视为具有与 Web 服务引用的站点相同的源站点。 这会导致 XBAP 尝试调用 Web 服务时引发安全异常。 但是，可以将 Visual Studio 2005 XAML 浏览器应用程序 (WPF) 项目配置为模拟在调试时与它调用的 Web 服务具有相同的源站点。 这样，XBAP 就可以安全地调用 Web 服务，而不会导致安全异常。

## <a name="configuring-visual-studio"></a>配置 Visual Studio
 若要配置 Visual Studio 2005 以调试调用 Web 服务的 XBAP：

1. 在“解决方案资源管理器” 中选择了项目的情况下，在“项目”  菜单上单击“属性” 。

2. 在 **项目设计器** 中，单击 " **调试** " 选项卡。

3. 在 " **启动操作** " 部分中，选择 " **启动外部程序** "，并输入以下内容：

     `C:\WINDOWS\System32\PresentationHost.exe`

4. 在 " **启动选项** " 部分，在 " **命令行参数** " 文本框中输入以下内容：

     `-debug`  *名字*

     **-Debug** 参数的 *filename* 值为 xbap 文件名;例如：

     `-debug c:\example.xbap`

> [!NOTE]
> 这是通过 Visual Studio 2005 XAML 浏览器应用程序 (WPF) 项目模板创建的解决方案的默认配置。

1. 在“解决方案资源管理器” 中选择了项目的情况下，在“项目”  菜单上单击“属性” 。

2. 在 **项目设计器** 中，单击 " **调试** " 选项卡。

3. 在 " **启动选项** " 部分，将以下命令行参数添加到 " **命令行参数** " 文本框中：

     `-debugSecurityZoneURL`  URL

     **-DebugSecurityZoneURL** 参数的 *url* 值是你要模拟为你的应用程序源站点的位置的 url。

 例如，假设 XAML 浏览器应用程序 (XBAP) 使用具有以下 URL 的 Web 服务：

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 此 Web 服务的源网站 URL 为：

 `http://services.msdn.microsoft.com`

 因此， **debugSecurityZoneURL** 命令行参数和值为：

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a>请参阅

- [WPF 主机 (PresentationHost.exe) ](wpf-host-presentationhost-exe.md)
