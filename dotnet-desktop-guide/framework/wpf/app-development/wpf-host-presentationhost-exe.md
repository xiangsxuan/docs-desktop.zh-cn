---
title: WPF 主机 (PresentationHost.exe)
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: 169fbd1a0d985f128b3bd22c0eb8abee99717903
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665362"
---
# <a name="wpf-host-presentationhostexe"></a>WPF 主机 (PresentationHost.exe)
Windows Presentation Foundation (WPF) 宿主 (PresentationHost.exe) 是一个应用程序，该应用程序允许在兼容的浏览器中承载 WPF 应用程序 (包括 Microsoft Internet Explorer 6 和更高版本) 。 默认情况下，Windows Presentation Foundation (WPF) 主机注册为浏览器承载的 WPF 内容的 shell 和 MIME 处理程序，其中包括：  
  
- 松散（未编译）[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 文件 (.xaml)。  
  
- XAML 浏览器应用程序 (XBAP)  ( xbap) 。  
  
 对于这些类型的文件，Windows Presentation Foundation (WPF) 主机：  
  
- 启动已注册的 HTML 处理程序，以承载 Windows Presentation Foundation (WPF) 内容。  
  
-  (CLR) 和 Windows Presentation Foundation (WPF) 程序集加载所需的公共语言运行时的正确版本。  
  
- 确保部署区域具有适当的权限级别。  
  
 本主题介绍了可以与 PresentationHost.exe 一起使用的命令行参数。  
  
## <a name="usage"></a>使用情况  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a>parameters  
  
|参数|说明|  
|---------------|-----------------|  
|filename|要激活的文件的路径。 也可以是 URI。|  
|-debug|激活应用程序时，不要从存储中提交或运行它。 此参数仅在激活本地文件时才起作用。|  
|-debugSecurityZoneURL \<url>|与 URL 值一起使用，以指示 PresentationHost.exe 应该调试应用程序，就像它是从指定的 URL 部署的一样。 此参数可确定部署区域和源站点。|  
|-embedding|OLE 的必需参数。 如果已指定 `-event` 或 `-debug` 参数，则无需指定 `-embedding` 参数，因为该参数已在内部设置。|  
|-事件 \<eventname>|用此名称打开事件，并在 PresentationHost.exe 初始化并准备好承载 WPF 内容时发出通知。 如果打开事件时发生错误（例如该事件尚未创建），则 PresentationHost.exe 将终止。|  
|-launchApplication \<url>|从指定的 URL 启动独立的 ClickOnce 应用程序。 应用与 .NET 应用程序有关的 Internet Explorer 和 WinINet 安全策略。|  
  
## <a name="scenarios"></a>方案  
  
### <a name="shell-handler"></a>Shell 处理程序  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a>MIME 处理程序  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a>Visual Studio 调试  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a>在区域中进行 Visual Studio 调试  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a>请参阅

- [安全性](../security-wpf.md)
