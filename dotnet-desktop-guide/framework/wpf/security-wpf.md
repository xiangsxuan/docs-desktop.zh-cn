---
title: 安全性
ms.date: 03/30/2017
helpviewer_keywords:
- XAML files [WPF], sandbox behavior
- browser-hosted application security [WPF]
- application security [WPF]
- navigation security [WPF]
- loose XAML files [WPF], sandbox behavior
- WPF security [WPF]
- WebBrowser control [WPF], security
- feature controls [WPF], security
- XBAP security [WPF]
- Internet Explorer security settings [WPF]
ms.assetid: ee1baea0-3611-4e36-9ad6-fcd5205376fb
ms.openlocfilehash: 5ad00043954e88238bcb29ecc725612b94eb2d04
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667925"
---
# <a name="security-wpf"></a>安全性 (WPF)

<a name="introduction"></a> 在开发 Windows Presentation Foundation (WPF) 独立应用程序和浏览器托管的应用程序时，必须考虑安全模型。 WPF 独立应用程序使用无限制权限执行 ( CA **FullTrust** 权限集) ，无论是使用 Windows Installer ( .msi) 、XCopy 还是 ClickOnce 部署的。 不支持使用 ClickOnce 部署部分信任的独立 WPF 应用程序。 但是，完全信任的主机应用程序可以 <xref:System.AppDomain> 使用 .NET Framework 外接程序模型创建部分信任。 有关详细信息，请参阅 [WPF Add-Ins 概述](./app-development/wpf-add-ins-overview.md)。  
  
 WPF 浏览器承载的应用程序由 Windows Internet Explorer 或 Firefox 承载，可以是 XAML 浏览器应用程序 (Xbap) 或松散 [!INCLUDE[TLA#tla_xaml](../../includes/tlasharptla-xaml-md.md)] 文档有关详细信息，请参阅 [WPF XAML 浏览器应用程序概述](./app-development/wpf-xaml-browser-applications-overview.md)。  
  
 WPF 浏览器承载的应用程序在默认情况下在部分信任的安全沙盒中执行，该沙箱仅限默认的 CAS **Internet** 区域权限集。 这会有效地将 WPF 浏览器承载的应用程序与客户端计算机隔离开来，就像需要隔离典型 Web 应用程序一样。 XBAP 最高可以将权限提升到“完全信任”，具体取决于部署 URL 的安全区域和客户端的安全配置。 有关详细信息，请参阅 [WPF 部分信任安全性](wpf-partial-trust-security.md)。  
  
 本主题讨论 Windows Presentation Foundation (WPF) 独立应用程序和浏览器托管应用程序的安全模型。  
  
 本主题包含以下各节：  
  
- [安全导航](#SafeTopLevelNavigation)  
  
- [Web 浏览软件安全设置](#InternetExplorerSecuritySettings)  
  
- [WebBrowser 控件和功能控件](#webbrowser_control_and_feature_controls)  
  
- [对部分受信任的客户端应用程序禁用 APTCA 程序集](#APTCA)  
  
- [宽松 XAML 文件的沙盒行为](#LooseContentSandboxing)  
  
- [用于开发可提高安全性的 WPF 应用程序的资源](#BestPractices)  
  
<a name="SafeTopLevelNavigation"></a>

## <a name="safe-navigation"></a>安全导航  

 对于 Xbap，WPF 区分两种类型的导航：应用程序和浏览器。  
  
 应用程序导航是指在浏览器托管的应用程序内的内容项之间进行导航。 浏览器导航是指可更改浏览器自身的内容和位置 URL 的导航。 应用程序导航 (通常是 XAML) 和浏览器导航 (通常是 HTML) ，如下图所示：
  
 ![应用程序导航与浏览器导航之间的关系。](./media/security-wpf/application-browser-navigation-relationship.png)  
  
 对于 XBAP 要导航到的内容的类型，主要取决于是否使用应用程序导航或浏览器导航。  
  
<a name="Application_Navigation_Security"></a>

### <a name="application-navigation-security"></a>应用程序导航安全性  

 如果应用程序导航可以使用 pack URI 来标识，并且它支持四种类型的内容，则将其视为安全：  
  
|内容类型|说明|URI 示例|  
|------------------|-----------------|-----------------|  
|资源|添加到具有 **资源** 生成类型的项目中的文件。|`pack://application:,,,/MyResourceFile.xaml`|  
|内容|使用 " **内容**" 生成类型添加到项目中的文件。|`pack://application:,,,/MyContentFile.xaml`|  
|源站点|添加到生成类型为 **None** 的项目中的文件。|`pack://siteoforigin:,,,/MySiteOfOriginFile.xaml`|  
|应用程序代码|具有已编译代码隐藏的 XAML 资源。<br /><br /> -或-<br /><br /> 添加到具有 **页** 的生成类型的项目中的 XAML 文件。|`pack://application:,,,/MyResourceFile` `.xaml`|  
  
> [!NOTE]
> 有关应用程序数据文件和包 Uri 的详细信息，请参阅 [WPF 应用程序资源、内容和数据文件](./app-development/wpf-application-resource-content-and-data-files.md)。  
  
 可以由用户导航到这些内容类型的文件，也可以通过编程方式导航到这些内容类型的文件：  
  
- **用户导航**。 用户通过单击 <xref:System.Windows.Documents.Hyperlink> 元素导航。  
  
- **编程导航**。 应用程序在不涉及用户的情况下进行导航，例如通过设置 <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType> 属性。  
  
<a name="Browser_Navigation_Security"></a>

### <a name="browser-navigation-security"></a>浏览器导航安全性  

 浏览器导航仅在以下条件下被视为安全：  
  
- **用户导航**。 用户通过单击 <xref:System.Windows.Documents.Hyperlink> main 内的元素 <xref:System.Windows.Navigation.NavigationWindow> ，而不是嵌套中的元素进行导航 <xref:System.Windows.Controls.Frame> 。  
  
- **区域**。 要导航到的内容位于 Internet 或本地 Intranet 上。  
  
- **协议**。 使用的协议是 **http**、 **https**、 **文件** 或 **mailto**。  
  
 如果 XBAP 尝试以不符合这些条件的方式导航到内容， <xref:System.Security.SecurityException> 则会引发。  
  
<a name="InternetExplorerSecuritySettings"></a>

## <a name="web-browsing-software-security-settings"></a>Web 浏览软件安全设置  

 计算机上的安全设置决定了任何 Web 浏览软件被授予的访问权限。 Web 浏览软件包含任何应用[程序或组件](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa767916(v=vs.85))，这些应用程序或组件使用[WinINet](/windows/win32/wininet/portal) Api，包括 Internet Explorer 和 PresentationHost.exe。  
  
 Internet Explorer 提供一种机制，通过该机制可以配置允许通过 Internet Explorer 执行的功能，包括以下内容：  
  
- .NET Framework 相关组件  
  
- ActiveX 控件和插件  
  
- 下载  
  
- 脚本编写  
  
- 用户身份验证  
  
 对于 **Internet**、 **Intranet**、 **受信任的站点** 和 **受限制的站点** 区域，可通过这种方式进行保护的功能集合以每个区域为基础进行配置。 以下步骤描述如何配置安全设置：  
  
1. 打开“控制面板”  
  
2. 单击 " **网络和 internet** "，然后单击 " **internet 选项**"。  
  
     将显示“Internet 选项”对话框。  
  
3. 在 " **安全** " 选项卡上，选择要为其配置安全设置的区域。  
  
4. 单击 " **自定义级别** " 按钮。  
  
     此时将显示 " **安全设置** " 对话框，你可以为所选区域配置安全设置。  
  
     ![显示 "安全设置" 对话框的屏幕截图。](./media/security-wpf/windows-presentation-foundation-security-settings.png)  
  
> [!NOTE]
> 也可以从 Internet Explorer 中进入“Internet 选项”对话框。 单击 " **工具** "，然后单击 " **Internet 选项**"。  
  
 从 Windows Internet Explorer 7 开始，包含了专门针对 .NET Framework 的以下安全设置：  
  
- **宽松 XAML**。 控制 Internet Explorer 是否可以导航到和松散 [!INCLUDE[TLA2#tla_xaml](../../includes/tla2sharptla-xaml-md.md)] 文件。 （“启用”、“禁用”和“提示”选项）。  
  
- **XAML 浏览器应用程序**。 控制 Internet Explorer 是否可以导航到并运行 Xbap。 （“启用”、“禁用”和“提示”选项）。  
  
 默认情况下，将为 " **Internet**"、" **本地 intranet**" 和 " **受信任站点** " 区域启用所有这些设置，并为 "受 **限制的站点** " 区域禁用这些设置。  
  
<a name="Security_Settings_for_IE6_and_Below"></a>

### <a name="security-related-wpf-registry-settings"></a>与安全相关的 WPF 注册表设置  

 除了可通过“Internet 选项”设置的安全设置之外，还可以通过设置以下注册表值有选择地阻止许多安全敏感 WPF 功能。 这些值在以下注册表项下定义：  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\Windows Presentation Foundation\Features`  
  
 下表列出了可以设置的值。  
  
|值名称|值类型|值数据|  
|----------------|----------------|----------------|  
|XBAPDisallow|REG_DWORD|1 为禁止；0 为允许。|  
|LooseXamlDisallow|REG_DWORD|1 为禁止；0 为允许。|  
|WebBrowserDisallow|REG_DWORD|1 为禁止；0 为允许。|  
|MediaAudioDisallow|REG_DWORD|1 为禁止；0 为允许。|  
|MediaImageDisallow|REG_DWORD|1 为禁止；0 为允许。|  
|MediaVideoDisallow|REG_DWORD|1 为禁止；0 为允许。|  
|ScriptInteropDisallow|REG_DWORD|1 为禁止；0 为允许。|  
  
<a name="webbrowser_control_and_feature_controls"></a>

## <a name="webbrowser-control-and-feature-controls"></a>WebBrowser 控件和功能控件  

 WPF <xref:System.Windows.Controls.WebBrowser> 控件可用于承载 Web 内容。 WPF <xref:System.Windows.Controls.WebBrowser> 控件包装基础 WebBrowser ActiveX 控件。 当你使用 WPF <xref:System.Windows.Controls.WebBrowser> 控件来承载不受信任的 Web 内容时，WPF 提供了一些对保护应用程序的支持。 但是，某些安全功能必须由使用控件的应用程序直接应用 <xref:System.Windows.Controls.WebBrowser> 。 有关 WebBrowser ActiveX 控件的详细信息，请参阅 [Webbrowser 控件概述和教程](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752041(v=vs.85))。  
  
> [!NOTE]
> 本节还适用于控件， <xref:System.Windows.Controls.Frame> 因为它使用 <xref:System.Windows.Controls.WebBrowser> 导航到 HTML 内容。  
  
 如果使用 WPF <xref:System.Windows.Controls.WebBrowser> 控件来承载不受信任的 Web 内容，你的应用程序应使用部分信任， <xref:System.AppDomain> 以帮助你将应用程序代码与可能的恶意 HTML 脚本代码隔离。 如果你的应用程序通过使用方法和属性与托管脚本进行交互，则更是如此 <xref:System.Windows.Controls.WebBrowser.InvokeScript%2A> <xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A> 。 有关详细信息，请参阅 [WPF Add-Ins 概述](./app-development/wpf-add-ins-overview.md)。  
  
 如果你的应用程序使用 WPF <xref:System.Windows.Controls.WebBrowser> 控件，提高安全性并缓解攻击的另一种方法是启用 Internet Explorer 功能控件。 功能控件是 Internet Explorer 的新增功能，允许管理员和开发人员配置 Internet Explorer 的功能，以及 WPF 控件包装的 WebBrowser ActiveX 控件的应用程序 <xref:System.Windows.Controls.WebBrowser> 。 功能控件可以通过使用 [CoInternetSetFeatureEnabled](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537168(v=vs.85)) 函数来配置，也可以通过更改注册表中的值来配置。 有关功能控件的详细信息，请参阅 [功能控件简介](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537184(v=vs.85)) 和 [Internet 功能控件](/previous-versions/windows/internet-explorer/ie-developer/general-info/ee330720(v=vs.85))。  
  
 如果要开发使用 WPF 控件的独立 WPF 应用程序 <xref:System.Windows.Controls.WebBrowser> ，WPF 会自动为应用程序启用以下功能控件。  
  
|功能控件|  
|---------------------|  
|FEATURE_MIME_HANDLING|  
|FEATURE_MIME_SNIFFING|  
|FEATURE_OBJECT_CACHING|  
|FEATURE_SAFE_BINDTOOBJECT|  
|FEATURE_WINDOW_RESTRICTIONS|  
|FEATURE_ZONE_ELEVATION|  
|FEATURE_RESTRICT_FILEDOWNLOAD|  
|FEATURE_RESTRICT_ACTIVEXINSTALL|  
|FEATURE_ADDON_MANAGEMENT|  
|FEATURE_HTTP_USERNAME_PASSWORD_DISABLE|  
|FEATURE_SECURITYBAND|  
|FEATURE_UNC_SAVEDFILECHECK|  
|FEATURE_VALIDATE_NAVIGATE_URL|  
|FEATURE_DISABLE_TELNET_PROTOCOL|  
|FEATURE_WEBOC_POPUPMANAGEMENT|  
|FEATURE_DISABLE_LEGACY_COMPRESSION|  
|FEATURE_SSLUX|  
  
 由于这些功能控件是无条件启用的，因此它们可能会对完全信任的应用程序造成损害。 在这种情况下，如果特定应用程序及其承载的内容没有安全风险，则可以禁用相应的功能控件。  
  
 功能控件由实例化 WebBrowser ActiveX 对象的过程应用。 因此，如果要创建可导航到不受信任的内容的独立应用程序，则应该认真考虑启用附加功能控件。  
  
> [!NOTE]
> 此建议是根据 MSHTML 和 SHDOCVW 主机安全性的一般性建议提出的。 有关详细信息，请参阅 [MSHTML 主机安全性常见问题：第 I 部分](https://msrc-blog.microsoft.com/2009/04/02/the-mshtml-host-security-faq-part-i-of-ii/) 和 [MSHTML 主机安全性常见问题：第 ii 部分（共 ii 部分](https://msrc-blog.microsoft.com/2009/04/03/the-mshtml-host-security-faq-part-ii-of-ii/)）。  
  
 对于可执行文件，请考虑通过将注册表值设置为 1 来启用以下功能控件。  
  
|功能控件|  
|---------------------|  
|FEATURE_ACTIVEX_REPURPOSEDETECTION|  
|FEATURE_BLOCK_LMZ_IMG|  
|FEATURE_BLOCK_LMZ_OBJECT|  
|FEATURE_BLOCK_LMZ_SCRIPT|  
|FEATURE_RESTRICT_RES_TO_LMZ|  
|FEATURE_RESTRICT_ABOUT_PROTOCOL_IE7|  
|FEATURE_SHOW_APP_PROTOCOL_WARN_DIALOG|  
|FEATURE_LOCALMACHINE_LOCKDOWN|  
|FEATURE_FORCE_ADDR_AND_STATUS|  
|FEATURE_RESTRICTED_ZONE_WHEN_FILE_NOT_FOUND|  
  
 对于可执行文件，请考虑通过将注册表值设置为 0 来禁用以下功能控件。  
  
|功能控件|  
|---------------------|  
|FEATURE_ENABLE_SCRIPT_PASTE_URLACTION_IF_PROMPT|  
  
 如果在 Windows Internet Explorer 中运行 (XBAP) 包含 WPF 控件的部分信任 XAML 浏览器应用程序 <xref:System.Windows.Controls.WebBrowser> ，则 WPF 会在 Internet explorer 进程的地址空间中承载 WebBrowser ActiveX 控件。 由于 WebBrowser ActiveX 控件承载于 Internet Explorer 进程中，因此还为 WebBrowser ActiveX 控件启用了 Internet Explorer 的所有功能控件。  
  
 与普通的独立应用程序相比，运行于 Internet Explorer 中的 XBAP 还将另外获得一层安全保护。 这种附加安全性是因为 Internet Explorer 和 WebBrowser ActiveX 控件默认在 Windows Vista 和 Windows 7 上以受保护模式运行。 有关保护模式的详细信息，请参阅 [了解和使用受保护模式的 Internet Explorer](/previous-versions/windows/internet-explorer/ie-developer/)。  
  
> [!NOTE]
> 如果尝试在 Firefox 中运行包含 WPF 控件的 XBAP <xref:System.Windows.Controls.WebBrowser> ，则在 Internet 区域中， <xref:System.Security.SecurityException> 将会引发。 这是由于 WPF 安全策略造成的。  
  
<a name="APTCA"></a>

## <a name="disabling-aptca-assemblies-for-partially-trusted-client-applications"></a>对部分受信任的客户端应用程序禁用 APTCA 程序集  

 将托管程序集安装到全局程序集缓存 (GAC) 时，它们将被完全信任，因为用户必须提供显式权限才能安装它们。 因为这些程序集是完全受信任的，所以只有完全受信任的托管客户端应用程序才可以使用它们。 若要允许部分受信任的应用程序使用它们，必须使用 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) 进行标记。 仅当程序集经过测试，可在部分信任的情况下安全执行时，才应该为其标记此特性。  
  
 但是，APTCA 程序集在安装到 GAC 后可能会出现安全漏洞。 一旦发现安全漏洞，程序集发布者可以生成安全更新来修复现有安装上的问题，还可以阻止问题发现后进行的安装操作。 其中一个更新选项是卸载程序集，即使这可能中断使用该程序集的其他完全受信任的客户端应用程序。  
  
 WPF 提供了一种机制，通过该机制，无需卸载 APTCA 程序集即可为部分受信任的 Xbap 禁用 APTCA 程序集。  
  
 若要禁用 APTCA 程序集，必须创建一个特殊的注册表项：  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\<AssemblyFullName>, FileVersion=<AssemblyFileVersion>`  
  
 示例如下：  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\aptcagac, Version=1.0.0.0, Culture=neutral, PublicKeyToken=215e3ac809a0fea7, FileVersion=1.0.0.0`  
  
 此项建立 APTCA 程序集的条目。 还必须在此项中创建值来启用或禁用程序集。 下面是该值的详细信息：  
  
- 值名称： **APTCA_FLAG**。  
  
- 值类型： **REG_DWORD**。  
  
- 值数据： **1** 到禁用; **0** ，则启用。  
  
 如果必须为部分受信任的客户端应用程序禁用某程序集，可以编写一个用于创建注册表项和值的更新。  
  
> [!NOTE]
> 核心 .NET Framework 程序集不受以这种方式的影响，因为运行托管应用程序时需要这些程序集。 对禁用 APTCA 程序集的支持主要面向第三方应用程序。  
  
<a name="LooseContentSandboxing"></a>

## <a name="sandbox-behavior-for-loose-xaml-files"></a>宽松 XAML 文件的沙盒行为  

 松散 [!INCLUDE[TLA2#tla_xaml](../../includes/tla2sharptla-xaml-md.md)] 文件是仅标记的 XAML 文件，不依赖于任何代码隐藏、事件处理程序或应用程序特定的程序集。 [!INCLUDE[TLA2#tla_xaml](../../includes/tla2sharptla-xaml-md.md)]直接从浏览器导航到松散文件时，这些文件将基于默认 Internet 区域权限集加载到安全沙箱中。  
  
 但是，当 [!INCLUDE[TLA2#tla_xaml](../../includes/tla2sharptla-xaml-md.md)] 从 <xref:System.Windows.Navigation.NavigationWindow> 或独立的应用程序导航到松散文件时，安全行为是不同的 <xref:System.Windows.Controls.Frame> 。  
  
 在这两种情况下， [!INCLUDE[TLA2#tla_xaml](../../includes/tla2sharptla-xaml-md.md)] 导航到的松散文件继承其主机应用程序的权限。 但是，这种行为可能会从安全角度来看，特别是当 [!INCLUDE[TLA2#tla_xaml](../../includes/tla2sharptla-xaml-md.md)] 不受信任或未知的实体生成松散文件时。 此类型的内容称为 *外部内容*， <xref:System.Windows.Controls.Frame> 并且 <xref:System.Windows.Navigation.NavigationWindow> 可以配置为在导航到时将其隔离。 可以通过将 **SandboxExternalContent** 属性设置为 true 来实现隔离，如和的以下示例所 <xref:System.Windows.Controls.Frame> 示 <xref:System.Windows.Navigation.NavigationWindow> ：  
  
 [!code-xaml[SecurityOverviewSnippets#FrameMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window2.xaml#framemarkup)]  
  
 [!code-xaml[SecurityOverviewSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window1.xaml#navigationwindowmarkup)]  
  
 使用此设置，外部内容将加载到不同于承载应用程序的进程的进程中。 此进程被限制在默认 Internet 区域权限集中，从而有效地将其与承载应用程序和客户端计算机隔离。  
  
> [!NOTE]
> 即使 [!INCLUDE[TLA2#tla_xaml](../../includes/tla2sharptla-xaml-md.md)] 从 <xref:System.Windows.Navigation.NavigationWindow> 或独立应用程序中的松散文件导航到 <xref:System.Windows.Controls.Frame> 基于 WPF 浏览器宿主基础结构（涉及 presentationhost.exe 过程），安全级别也略小于直接在 Windows Vista 和 windows 7 上的 Internet Explorer 中加载内容 (这仍通过 presentationhost.exe) 。 这是因为使用 Web 浏览器的独立 WPF 应用程序不提供 Internet Explorer 的额外“保护模式”安全功能。  
  
<a name="BestPractices"></a>

## <a name="resources-for-developing-wpf-applications-that-promote-security"></a>用于开发可提高安全性的 WPF 应用程序的资源  

 下面是一些其他资源，可帮助开发可提高安全性的 WPF 应用程序：  
  
|区域|资源|  
|----------|--------------|  
|托管代码|[应用程序的模式和实践安全指南](/previous-versions/msp-n-p/ff650760(v=pandp.10))|  
|CAS|[代码访问安全性](/dotnet/framework/misc/code-access-security)|  
|ClickOnce|[ClickOnce 安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)|  
|WPF|[WPF 部分信任安全](wpf-partial-trust-security.md)|  
  
## <a name="see-also"></a>请参阅

- [WPF 部分信任安全](wpf-partial-trust-security.md)
- [WPF 安全策略 - 平台安全性](wpf-security-strategy-platform-security.md)
- [WPF 安全策略 - 安全工程](wpf-security-strategy-security-engineering.md)
- [应用程序的模式和实践安全指南](/previous-versions/msp-n-p/ff650760(v=pandp.10))
- [代码访问安全性](/dotnet/framework/misc/code-access-security)
- [ClickOnce 安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)
- [XAML 概述 (WPF)](/dotnet/desktop-wpf/fundamentals/xaml)
