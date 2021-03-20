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
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="7dfec-102">WPF 主机 (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="7dfec-102">WPF Host (PresentationHost.exe)</span></span>
<span data-ttu-id="7dfec-103">Windows Presentation Foundation (WPF) 宿主 (PresentationHost.exe) 是一个应用程序，该应用程序允许在兼容的浏览器中承载 WPF 应用程序 (包括 Microsoft Internet Explorer 6 和更高版本) 。</span><span class="sxs-lookup"><span data-stu-id="7dfec-103">Windows Presentation Foundation (WPF) Host (PresentationHost.exe) is the application that enables WPF applications to be hosted in compatible browsers (including Microsoft Internet Explorer 6 and later).</span></span> <span data-ttu-id="7dfec-104">默认情况下，Windows Presentation Foundation (WPF) 主机注册为浏览器承载的 WPF 内容的 shell 和 MIME 处理程序，其中包括：</span><span class="sxs-lookup"><span data-stu-id="7dfec-104">By default, Windows Presentation Foundation (WPF) Host is registered as the shell and MIME handler for browser-hosted WPF content, which includes:</span></span>  
  
- <span data-ttu-id="7dfec-105">松散（未编译）[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 文件 (.xaml)。</span><span class="sxs-lookup"><span data-stu-id="7dfec-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
- <span data-ttu-id="7dfec-106">XAML 浏览器应用程序 (XBAP)  ( xbap) 。</span><span class="sxs-lookup"><span data-stu-id="7dfec-106">XAML browser application (XBAP) (.xbap).</span></span>  
  
 <span data-ttu-id="7dfec-107">对于这些类型的文件，Windows Presentation Foundation (WPF) 主机：</span><span class="sxs-lookup"><span data-stu-id="7dfec-107">For files of these types, Windows Presentation Foundation (WPF) Host:</span></span>  
  
- <span data-ttu-id="7dfec-108">启动已注册的 HTML 处理程序，以承载 Windows Presentation Foundation (WPF) 内容。</span><span class="sxs-lookup"><span data-stu-id="7dfec-108">Launches the registered HTML handler to host the Windows Presentation Foundation (WPF) content.</span></span>  
  
- <span data-ttu-id="7dfec-109"> (CLR) 和 Windows Presentation Foundation (WPF) 程序集加载所需的公共语言运行时的正确版本。</span><span class="sxs-lookup"><span data-stu-id="7dfec-109">Loads the right versions of the required common language runtime (CLR) and Windows Presentation Foundation (WPF) assemblies.</span></span>  
  
- <span data-ttu-id="7dfec-110">确保部署区域具有适当的权限级别。</span><span class="sxs-lookup"><span data-stu-id="7dfec-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="7dfec-111">本主题介绍了可以与 PresentationHost.exe 一起使用的命令行参数。</span><span class="sxs-lookup"><span data-stu-id="7dfec-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="7dfec-112">使用情况</span><span class="sxs-lookup"><span data-stu-id="7dfec-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="7dfec-113">parameters</span><span class="sxs-lookup"><span data-stu-id="7dfec-113">Parameters</span></span>  
  
|<span data-ttu-id="7dfec-114">参数</span><span class="sxs-lookup"><span data-stu-id="7dfec-114">Parameter</span></span>|<span data-ttu-id="7dfec-115">说明</span><span class="sxs-lookup"><span data-stu-id="7dfec-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7dfec-116">filename</span><span class="sxs-lookup"><span data-stu-id="7dfec-116">filename</span></span>|<span data-ttu-id="7dfec-117">要激活的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="7dfec-117">The path of the file to be activated.</span></span> <span data-ttu-id="7dfec-118">也可以是 URI。</span><span class="sxs-lookup"><span data-stu-id="7dfec-118">Can also be a URI.</span></span>|  
|<span data-ttu-id="7dfec-119">-debug</span><span class="sxs-lookup"><span data-stu-id="7dfec-119">-debug</span></span>|<span data-ttu-id="7dfec-120">激活应用程序时，不要从存储中提交或运行它。</span><span class="sxs-lookup"><span data-stu-id="7dfec-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="7dfec-121">此参数仅在激活本地文件时才起作用。</span><span class="sxs-lookup"><span data-stu-id="7dfec-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="7dfec-122">-debugSecurityZoneURL \<url></span><span class="sxs-lookup"><span data-stu-id="7dfec-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="7dfec-123">与 URL 值一起使用，以指示 PresentationHost.exe 应该调试应用程序，就像它是从指定的 URL 部署的一样。</span><span class="sxs-lookup"><span data-stu-id="7dfec-123">Used with a URL value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified URL.</span></span> <span data-ttu-id="7dfec-124">此参数可确定部署区域和源站点。</span><span class="sxs-lookup"><span data-stu-id="7dfec-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="7dfec-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="7dfec-125">-embedding</span></span>|<span data-ttu-id="7dfec-126">OLE 的必需参数。</span><span class="sxs-lookup"><span data-stu-id="7dfec-126">Required by OLE.</span></span> <span data-ttu-id="7dfec-127">如果已指定 `-event` 或 `-debug` 参数，则无需指定 `-embedding` 参数，因为该参数已在内部设置。</span><span class="sxs-lookup"><span data-stu-id="7dfec-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="7dfec-128">-事件 \<eventname></span><span class="sxs-lookup"><span data-stu-id="7dfec-128">-event \<eventname></span></span>|<span data-ttu-id="7dfec-129">用此名称打开事件，并在 PresentationHost.exe 初始化并准备好承载 WPF 内容时发出通知。</span><span class="sxs-lookup"><span data-stu-id="7dfec-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host WPF content.</span></span> <span data-ttu-id="7dfec-130">如果打开事件时发生错误（例如该事件尚未创建），则 PresentationHost.exe 将终止。</span><span class="sxs-lookup"><span data-stu-id="7dfec-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="7dfec-131">-launchApplication \<url></span><span class="sxs-lookup"><span data-stu-id="7dfec-131">-launchApplication \<url></span></span>|<span data-ttu-id="7dfec-132">从指定的 URL 启动独立的 ClickOnce 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7dfec-132">Launches a standalone ClickOnce application from the specified URL.</span></span> <span data-ttu-id="7dfec-133">应用与 .NET 应用程序有关的 Internet Explorer 和 WinINet 安全策略。</span><span class="sxs-lookup"><span data-stu-id="7dfec-133">Internet Explorer and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="7dfec-134">方案</span><span class="sxs-lookup"><span data-stu-id="7dfec-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="7dfec-135">Shell 处理程序</span><span class="sxs-lookup"><span data-stu-id="7dfec-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="7dfec-136">MIME 处理程序</span><span class="sxs-lookup"><span data-stu-id="7dfec-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="7dfec-137">Visual Studio 调试</span><span class="sxs-lookup"><span data-stu-id="7dfec-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="7dfec-138">在区域中进行 Visual Studio 调试</span><span class="sxs-lookup"><span data-stu-id="7dfec-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="7dfec-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="7dfec-139">See also</span></span>

- [<span data-ttu-id="7dfec-140">安全性</span><span class="sxs-lookup"><span data-stu-id="7dfec-140">Security</span></span>](../security-wpf.md)
