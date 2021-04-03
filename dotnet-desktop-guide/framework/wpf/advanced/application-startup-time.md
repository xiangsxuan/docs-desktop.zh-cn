---
title: 应用程序启动时间
ms.date: 03/30/2017
helpviewer_keywords:
- splash screen [WPF], startup time
- WPF [WPF], startup time
- startup time [WPF]
- application startup [WPF]
- performance [WPF], startup time
ms.assetid: f0ec58d8-626f-4d8a-9873-c20f95e08b96
ms.openlocfilehash: effcc40800ed12e26c2594a11c210cc926743778
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973154"
---
# <a name="application-startup-time"></a>应用程序启动时间
启动 WPF 应用程序所需的时间可能存在极大差异。 本主题介绍用于减少 Windows Presentation Foundation (WPF) 应用程序假设启动时间和实际启动时间的各种技巧。  
  
## <a name="understanding-cold-startup-and-warm-startup"></a>了解冷启动和热启动  
 冷启动发生在系统重启后第一次启动应用程序时，或启动应用程序、将其关闭，然后在很长一段时间后再次启动应用程序时。 应用程序启动时，如果所需的页面（代码、静态数据、注册表等）不在 Windows 内存管理器的待机列表中，会发生页面错误。 需要磁盘访问权限，以便将这些页面加载到内存中。  
  
 当已将主要公共语言运行时 (CLR) 组件的大多数页面加载到内存中时，则发生热启动，这样可节省宝贵的磁盘访问时间。 这就是为什么再次运行托管的应用程序时，该程序的启动速度更快的原因。  
  
## <a name="implement-a-splash-screen"></a>实现初始屏幕  
 为应对在启动应用程序后到显示第一个 UI 期间出现重大的、不可避免的延迟的情况，请使用“初始屏幕”优化假设的启动时间。 通过此方法，在用户启动应用程序后，几乎可以立即显示图像。 当应用程序准备好显示其第一个 UI 时，初始屏幕将淡化。 从 .NET Framework 3.5 SP1 开始，可以使用 <xref:System.Windows.SplashScreen> 类实现初始屏幕。 有关详细信息，请参阅[将初始屏幕添加到 WPF 应用程序](../app-development/how-to-add-a-splash-screen-to-a-wpf-application.md)。  
  
 还可以通过使用本机 Win32 图形来实现自己的初始屏幕。 在调用方法之前显示你的实现 <xref:System.Windows.Application.Run%2A> 。  
  
## <a name="analyze-the-startup-code"></a>分析启动代码  
 确定冷启动慢的原因。 可能与磁盘 I/O 有关，但这并非唯一的原因。 一般情况下，应将外部资源（例如网络、Web 服务或磁盘）的使用率最小化。  
  
 在测试之前，验证没有其他正在运行的应用程序或服务会使用托管代码或 WPF 代码。  
  
 重新启动后，立即启动 WPF 应用程序，并决定用于显示的时间。 如果应用程序的所有后续启动（热启动）相较之下快很多，则冷启动问题很可能是 I/O 所致。  
  
 如果应用程序的冷启动问题与 I/O 无关，则冷启动慢的原因很可能是应用程序在启动时会执行一些耗时较长的初始化进程或计算、等待某些事件完成或需要大量的 JIT 编译。 以下章节对其中某些情况进行了详细介绍。  
  
## <a name="optimize-module-loading"></a>优化模块加载  
 使用工具（例如进程资源管理器 (Procexp.exe) 和 Tlist.exe）来确定应用程序加载的模块。 命令 `Tlist <pid>` 显示由某一进程加载的所有模块。  
  
 例如，如果没有连接到 Web，并且发现已加载 System.Web.dll，则应用程序中存在引用此程序集的模块。 检查以确定该引用是必要的。  
  
 如果应用程序具有多个模块，则请将其合并为单个模块。 此方法要求较少的 CLR 程序集加载开销。 较少的程序集还意味着 CLR 维护较少的状态。  
  
## <a name="defer-initialization-operations"></a>延迟初始化操作  
 请考虑将初始化代码延迟至主应用程序窗口呈现之后。  
  
 请注意，可能会在类构造函数内执行初始化，如果初始化代码引用其他类，则可能会导致级联效应（执行许多类构造函数）。  
  
## <a name="avoid-application-configuration"></a>避免应用程序配置  
 请考虑避免应用程序配置。 例如，如果某一应用程序具有简单的配置要求，并且具有严格的启动时间目标，则注册表项或简单的 INI 文件可能是更快的启动替代方法。  
  
## <a name="utilize-the-gac"></a>利用 GAC  
 如果未在全局程序集缓存 (GAC) 中安装程序集，则将出现由强命名程序集的哈希验证和 Ngen 映像验证（如果计算机上该程序集的本机映像可用）导致的延迟。 对于安装到 GAC 中的所有程序集，会跳过强命名验证。 有关详细信息，请参阅 [Gacutil.exe（全局程序集缓存工具）](/dotnet/framework/tools/gacutil-exe-gac-tool)。  
  
## <a name="use-ngenexe"></a>使用 Ngen.exe  
 请考虑在应用程序上使用本机映像生成器 (Ngen.exe)。 使用 Ngen.exe 意味着通过减少 CPU 消耗来实现更多的磁盘访问，因为由 Ngen.exe 生成的本机映像可能会比 MSIL 映像要大。  
  
 若要减少热启动时间，则应在应用程序上始终使用 Ngen.exe，因为这可以避免应用程序代码的 JIT 编译的 CPU 成本。  
  
 在某些冷启动方案中，使用 Ngen.exe 也会有所帮助。 这是因为不需要加载 JIT 编译器 (mscorjit.dll)。  
  
 同时具有 Ngen 和 JIT 模块可能会导致最差的效果。 这是因为必须加载 mscorjit.dll，且当 JIT 编译器处理代码时，当编译器读取程序集的元数据时，必须访问 Ngen 映像中的许多页面。  
  
### <a name="ngen-and-clickonce"></a>Ngen 和 ClickOnce  
 计划用于部署应用程序的方法在加载期间也会造成影响。 ClickOnce 应用程序部署不支持 Ngen。 如果决定对应用程序使用 Ngen.exe，则需要使用其他部署机制，如 Windows Installer。  
  
 有关详细信息，请参阅 [Ngen.exe（本机映像生成器）](/dotnet/framework/tools/ngen-exe-native-image-generator)。  
  
### <a name="rebasing-and-dll-address-collisions"></a>基址重置和 DLL 地址冲突  
 如果使用 Ngen.exe，请注意，本机映像加载到内存中时可能会发生基址重置。 如果未在 DLL 首选基址加载该 DLL（由于已分配该地址范围），则 Windows 加载程序将在另一地址加载该 DLL，这可能是一个耗时的操作。  
  
 可以使用虚拟地址转储 (Vadump.exe) 工具来检查是否存在其中所有页面都为私有的模块。 如果是这种情况，则可能已将该模块的基址重置到另一地址。 因此，不能共享其页面。  
  
 有关如何设置基址的详细信息，请参阅 [Ngen.exe（本机映像生成器）](/dotnet/framework/tools/ngen-exe-native-image-generator)。  
  
## <a name="optimize-authenticode"></a>优化验证码  
 验证码验证会增加启动时间。 验证码签名的程序集必须通过证书颁发机构 (CA) 验证。 此验证可能需要较长时间，因为它可能会要求多次连接到网络，以便下载当前证书吊销列表。 它还确保受信任的根路径上存在完整的有效证书链。 在加载程序集时，这可能会导致几秒钟的延迟。  
  
 请考虑在客户端计算机上安装 CA 证书，或尽可能避免使用验证码。 如果知道应用程序不需要发布服务器证据，则无需支付签名验证的费用。  
  
 从 .NET Framework 3.5 开始，有一个配置选项允许绕过 Authenticode 验证。 为执行此操作，将以下设置添加到 app.exe.config 文件：  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>
    </runtime>  
</configuration>  
```  
  
 有关详细信息，请参阅 [\<generatePublisherEvidence> 元素](/dotnet/framework/configure-apps/file-schema/runtime/generatepublisherevidence-element)。  
  
## <a name="compare-performance-on-windows-vista"></a>在 Windows Vista 上比较性能  
 Windows Vista 中的内存管理器具有一种名为 SuperFetch 的技术。 SuperFetch 可随时间推移分析内存使用情况模式，从而确定特定用户的最优内存内容。 它会持续工作，不间断地维护此内容。  
  
 这种方法不同于 Windows XP 中使用的预提取技术，后者将数据预先加载到内存，而不分析使用情况模式。 随着时间的推移，如果用户在 Windows Vista 上频繁使用 WPF 应用程序，则可能改善应用程序的冷启动时间。  
  
## <a name="use-appdomains-efficiently"></a>有效使用 AppDomains  
 如果可能，将程序集加载到非特定于域的代码区域，以确保本机映像（如果存在）会在应用程序中创建的所有 AppDomain 中使用。  
  
 为获得最佳性能，通过减少跨域调用强制实施高效跨域通信。 如果可能，请使用不带参数或具有基元类型参数的调用。  
  
## <a name="use-the-neutralresourceslanguage-attribute"></a>使用 NeutralResourcesLanguage 特性  
 使用 <xref:System.Resources.NeutralResourcesLanguageAttribute> 指定的非特定区域性 <xref:System.Resources.ResourceManager> 。 此方法可避免程序集查找失败。  
  
## <a name="use-the-binaryformatter-class-for-serialization"></a>将 BinaryFormatter 类用于序列化  
 如果必须使用序列化，请使用 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 类，而不是 <xref:System.Xml.Serialization.XmlSerializer> 类。 在 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 基类库中实现类 (mscorlib.dll 程序集中的 BCL) 。 <xref:System.Xml.Serialization.XmlSerializer>是在 System.Xml.dll 程序集中实现的，该程序集可能是要加载的其他 DLL。  
  
 如果你必须使用 <xref:System.Xml.Serialization.XmlSerializer> 类，则在预生成序列化程序集时，可以获得更好的性能。  
  
## <a name="configure-clickonce-to-check-for-updates-after-startup"></a>将 ClickOnce 配置为在启动后检查更新  
 如果你的应用程序使用 ClickOnce，请在启动时配置 ClickOnce 以检查部署站点是否有更新，以避免在启动时进行网络访问。  
  
 如果使用 XAML 浏览器应用程序 (XBAP) 模型，请记住，即使 XBAP 已在 ClickOnce 缓存中，ClickOnce 也会检查部署站点是否有更新。 有关详细信息，请参阅 [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment)。  
  
## <a name="configure-the-presentationfontcache-service-to-start-automatically"></a>将 PresentationFontCache 服务配置为自动启动  
 在重新启动后，要运行的第一个 WPF 应用程序是 PresentationFontCache 服务。 该服务会缓存系统字体、改进字体访问，并提高整体性能。 在启动服务时会产生开销，某些受控环境中也存在开销，请考虑将服务配置为在系统重启时自动启动。  
  
## <a name="set-data-binding-programmatically"></a>以编程方式设置数据绑定  
 <xref:System.Windows.FrameworkElement.DataContext%2A>请考虑在方法中以编程方式设置主窗口，而不是使用 XAML 以声明方式设置 <xref:System.Windows.Application.OnActivated%2A> 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.SplashScreen>
- <xref:System.AppDomain>
- <xref:System.Resources.NeutralResourcesLanguageAttribute>
- <xref:System.Resources.ResourceManager>
- [向 WPF 应用程序添加初始屏幕](../app-development/how-to-add-a-splash-screen-to-a-wpf-application.md)
- [Ngen.exe（本机映像生成器）](/dotnet/framework/tools/ngen-exe-native-image-generator)
- [\<generatePublisherEvidence> 元素](/dotnet/framework/configure-apps/file-schema/runtime/generatepublisherevidence-element)
