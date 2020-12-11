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
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973624"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="12a84-102">如何：配置 Visual Studio 以调试 XAML 浏览器应用程序来调用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="12a84-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
<span data-ttu-id="12a84-103">XAML 浏览器应用程序 (Xbap) 在仅限于 Internet 区域权限集的部分信任的安全沙盒中运行。</span><span class="sxs-lookup"><span data-stu-id="12a84-103">XAML browser applications (XBAPs) run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="12a84-104">此权限集将 Web 服务调用限制为仅位于 XBAP 应用程序源站点上的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="12a84-104">This permission set restricts Web service calls to only Web services that are located at the XBAP application's site of origin.</span></span> <span data-ttu-id="12a84-105">不过，当从 Visual Studio 2005 调试 XBAP 时，它不会被视为具有与 Web 服务引用的站点相同的源站点。</span><span class="sxs-lookup"><span data-stu-id="12a84-105">When an XBAP is debugged from Visual Studio 2005, though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="12a84-106">这会导致 XBAP 尝试调用 Web 服务时引发安全异常。</span><span class="sxs-lookup"><span data-stu-id="12a84-106">This causes security exceptions to be raised when the XBAP attempts to call the Web service.</span></span> <span data-ttu-id="12a84-107">但是，可以将 Visual Studio 2005 XAML 浏览器应用程序 (WPF) 项目配置为模拟在调试时与它调用的 Web 服务具有相同的源站点。</span><span class="sxs-lookup"><span data-stu-id="12a84-107">However, a Visual Studio 2005 XAML Browser Application (WPF) project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="12a84-108">这样，XBAP 就可以安全地调用 Web 服务，而不会导致安全异常。</span><span class="sxs-lookup"><span data-stu-id="12a84-108">This allows the XBAP to safely call the Web service without causing security exceptions.</span></span>

## <a name="configuring-visual-studio"></a><span data-ttu-id="12a84-109">配置 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="12a84-109">Configuring Visual Studio</span></span>
 <span data-ttu-id="12a84-110">若要配置 Visual Studio 2005 以调试调用 Web 服务的 XBAP：</span><span class="sxs-lookup"><span data-stu-id="12a84-110">To configure Visual Studio 2005 to debug an XBAP that calls a Web service:</span></span>

1. <span data-ttu-id="12a84-111">在“解决方案资源管理器” 中选择了项目的情况下，在“项目”  菜单上单击“属性” 。</span><span class="sxs-lookup"><span data-stu-id="12a84-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="12a84-112">在 **项目设计器** 中，单击 " **调试** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="12a84-112">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="12a84-113">在 " **启动操作** " 部分中，选择 " **启动外部程序** "，并输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="12a84-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>

     `C:\WINDOWS\System32\PresentationHost.exe`

4. <span data-ttu-id="12a84-114">在 " **启动选项** " 部分，在 " **命令行参数** " 文本框中输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="12a84-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>

     <span data-ttu-id="12a84-115">`-debug`  *名字*</span><span class="sxs-lookup"><span data-stu-id="12a84-115">`-debug`  *filename*</span></span>

     <span data-ttu-id="12a84-116">**-Debug** 参数的 *filename* 值为 xbap 文件名;例如：</span><span class="sxs-lookup"><span data-stu-id="12a84-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>

     `-debug c:\example.xbap`

> [!NOTE]
> <span data-ttu-id="12a84-117">这是通过 Visual Studio 2005 XAML 浏览器应用程序 (WPF) 项目模板创建的解决方案的默认配置。</span><span class="sxs-lookup"><span data-stu-id="12a84-117">This is the default configuration for solutions that are created with the Visual Studio 2005 XAML Browser Application (WPF) project template.</span></span>

1. <span data-ttu-id="12a84-118">在“解决方案资源管理器” 中选择了项目的情况下，在“项目”  菜单上单击“属性” 。</span><span class="sxs-lookup"><span data-stu-id="12a84-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="12a84-119">在 **项目设计器** 中，单击 " **调试** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="12a84-119">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="12a84-120">在 " **启动选项** " 部分，将以下命令行参数添加到 " **命令行参数** " 文本框中：</span><span class="sxs-lookup"><span data-stu-id="12a84-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>

     <span data-ttu-id="12a84-121">`-debugSecurityZoneURL`  URL</span><span class="sxs-lookup"><span data-stu-id="12a84-121">`-debugSecurityZoneURL`  *URL*</span></span>

     <span data-ttu-id="12a84-122">**-DebugSecurityZoneURL** 参数的 *url* 值是你要模拟为你的应用程序源站点的位置的 url。</span><span class="sxs-lookup"><span data-stu-id="12a84-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the URL for the location that you want to simulate as being the site of origin of your application.</span></span>

 <span data-ttu-id="12a84-123">例如，假设 XAML 浏览器应用程序 (XBAP) 使用具有以下 URL 的 Web 服务：</span><span class="sxs-lookup"><span data-stu-id="12a84-123">As an example, consider a XAML browser application (XBAP) that uses a Web service with the following URL:</span></span>

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 <span data-ttu-id="12a84-124">此 Web 服务的源网站 URL 为：</span><span class="sxs-lookup"><span data-stu-id="12a84-124">The site of origin URL for this Web service is:</span></span>

 `http://services.msdn.microsoft.com`

 <span data-ttu-id="12a84-125">因此， **debugSecurityZoneURL** 命令行参数和值为：</span><span class="sxs-lookup"><span data-stu-id="12a84-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a><span data-ttu-id="12a84-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12a84-126">See also</span></span>

- [<span data-ttu-id="12a84-127">WPF 主机 ( # A0) </span><span class="sxs-lookup"><span data-stu-id="12a84-127">WPF Host (PresentationHost.exe)</span></span>](wpf-host-presentationhost-exe.md)
