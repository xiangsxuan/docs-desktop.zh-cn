---
title: 如何：配置 IIS 5.0 和 IIS 6.0 以部署 WPF 应用程序
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- MIME types [WPF], registering
- adjusting content expiration setting [WPF]
- registering file extensions [WPF]
- deploying applications [WPF]
- applications [WPF], deploying
- Web servers [WPF], configuring to deploy WPF applications
- configuring Web servers to deploy WPF applications [WPF]
- content expiration setting [WPF], adjusting
- file extensions [WPF], registering
- registering MIME types [WPF]
ms.assetid: c6e8c2cb-9ba2-4e75-a0d5-180ec9639433
ms.openlocfilehash: 2a6aab340993f5f414e5c5943574ccba3676f488
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667871"
---
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a><span data-ttu-id="54ea9-102">如何：配置 IIS 5.0 和 IIS 6.0 以部署 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="54ea9-102">How to: Configure IIS 5.0 and IIS 6.0 to Deploy WPF Applications</span></span>

<span data-ttu-id="54ea9-103">你可以 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 从大多数 Web 服务器部署应用程序，前提是这些服务器使用适当的多用途 Internet 邮件扩展配置 (MIME) 类型。</span><span class="sxs-lookup"><span data-stu-id="54ea9-103">You can deploy a [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] application from most Web servers, as long as they are configured with the appropriate Multipurpose Internet Mail Extensions (MIME) types.</span></span> <span data-ttu-id="54ea9-104">默认情况下，Microsoft Internet Information Services (IIS) 7.0 配置了这些 MIME 类型，但 Microsoft Internet Information Services (iis) 5.0 和 Microsoft Internet Information Services (IIS) 6.0。</span><span class="sxs-lookup"><span data-stu-id="54ea9-104">By default, Microsoft Internet Information Services (IIS) 7.0 is configured with these MIME types, but Microsoft Internet Information Services (IIS) 5.0 and Microsoft Internet Information Services (IIS) 6.0 are not.</span></span>

<span data-ttu-id="54ea9-105">本主题介绍如何配置 Microsoft Internet Information Services (IIS) 5.0 和 Microsoft Internet Information Services (IIS) 6.0 来部署 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 应用程序。</span><span class="sxs-lookup"><span data-stu-id="54ea9-105">This topic describes how to configure Microsoft Internet Information Services (IIS) 5.0 and Microsoft Internet Information Services (IIS) 6.0 to deploy [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span>

> [!NOTE]
> <span data-ttu-id="54ea9-106">你可以在注册表中检查 *UserAgent* 字符串，以确定系统是否安装了 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="54ea9-106">You can check the *UserAgent* string in the registry to determine whether a system has .NET Framework installed.</span></span> <span data-ttu-id="54ea9-107">有关详细信息和检查 *UserAgent* 字符串以确定系统是否安装了 .NET Framework 的脚本，请参阅 [检测是否安装了 .NET Framework 3.0](how-to-detect-whether-the-net-framework-3-0-is-installed.md)。</span><span class="sxs-lookup"><span data-stu-id="54ea9-107">For details and a script that examines the *UserAgent* string to determine whether .NET Framework is installed on a system, see [Detect Whether the .NET Framework 3.0 Is Installed](how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span></span>

<a name="content_expiration"></a>

## <a name="adjust-the-content-expiration-setting"></a><span data-ttu-id="54ea9-108">调整内容过期设置</span><span class="sxs-lookup"><span data-stu-id="54ea9-108">Adjust the Content Expiration Setting</span></span>

<span data-ttu-id="54ea9-109">应将内容过期设置调整为 1 分钟。</span><span class="sxs-lookup"><span data-stu-id="54ea9-109">You should adjust the content expiration setting to 1 minute.</span></span> <span data-ttu-id="54ea9-110">下面的过程概述了如何通过 IIS 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="54ea9-110">The following procedure outlines how to do this with IIS.</span></span>

1. <span data-ttu-id="54ea9-111">单击“开始”菜单，指向“管理工具”，然后单击“Internet Information Services (IIS) 管理器”。</span><span class="sxs-lookup"><span data-stu-id="54ea9-111">Click the **Start** menu, point to **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="54ea9-112">还可以使用“%systemroot%\system32\inetsrv\iis.msc”从命令行启动此应用程序。</span><span class="sxs-lookup"><span data-stu-id="54ea9-112">You can also launch this application from the command line with "%SystemRoot%\system32\inetsrv\iis.msc".</span></span>

2. <span data-ttu-id="54ea9-113">展开 IIS 树，直到找到 " **默认** 网站" 节点。</span><span class="sxs-lookup"><span data-stu-id="54ea9-113">Expand the IIS tree until you find the **Default Web site** node.</span></span>

3. <span data-ttu-id="54ea9-114">右键单击“默认网站”，然后从上下文菜单中选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="54ea9-114">Right-click **Default Web site** and select **Properties** from the context menu.</span></span>

4. <span data-ttu-id="54ea9-115">选择“HTTP 头”选项卡，然后单击“启用内容过期”。</span><span class="sxs-lookup"><span data-stu-id="54ea9-115">Select the **HTTP Headers** tab and click "Enable Content Expiration".</span></span>

5. <span data-ttu-id="54ea9-116">将内容设置为在 1 分钟后过期。</span><span class="sxs-lookup"><span data-stu-id="54ea9-116">Set the content to expire after 1 minute.</span></span>

<a name="register_mime_types"></a>

## <a name="register-mime-types-and-file-extensions"></a><span data-ttu-id="54ea9-117">注册 MIME 类型和文件扩展名</span><span class="sxs-lookup"><span data-stu-id="54ea9-117">Register MIME Types and File Extensions</span></span>

<span data-ttu-id="54ea9-118">必须注册多个 MIME 类型和文件扩展名，以便客户端系统上的浏览器可以加载正确的处理程序。</span><span class="sxs-lookup"><span data-stu-id="54ea9-118">You must register several MIME types and file extensions so that the browser on the client's system can load the correct handler.</span></span> <span data-ttu-id="54ea9-119">需要添加以下类型：</span><span class="sxs-lookup"><span data-stu-id="54ea9-119">You need to add the following types:</span></span>

|<span data-ttu-id="54ea9-120">分机</span><span class="sxs-lookup"><span data-stu-id="54ea9-120">Extension</span></span>|<span data-ttu-id="54ea9-121">MIME 类型</span><span class="sxs-lookup"><span data-stu-id="54ea9-121">MIME Type</span></span>|
|---------------|---------------|
|<span data-ttu-id="54ea9-122">.manifest</span><span class="sxs-lookup"><span data-stu-id="54ea9-122">.manifest</span></span>|<span data-ttu-id="54ea9-123">application/manifest</span><span class="sxs-lookup"><span data-stu-id="54ea9-123">application/manifest</span></span>|
|<span data-ttu-id="54ea9-124">.xaml</span><span class="sxs-lookup"><span data-stu-id="54ea9-124">.xaml</span></span>|<span data-ttu-id="54ea9-125">application/xaml+xml</span><span class="sxs-lookup"><span data-stu-id="54ea9-125">application/xaml+xml</span></span>|
|<span data-ttu-id="54ea9-126">.application</span><span class="sxs-lookup"><span data-stu-id="54ea9-126">.application</span></span>|<span data-ttu-id="54ea9-127">application/x-ms-application</span><span class="sxs-lookup"><span data-stu-id="54ea9-127">application/x-ms-application</span></span>|
|<span data-ttu-id="54ea9-128">.xbap</span><span class="sxs-lookup"><span data-stu-id="54ea9-128">.xbap</span></span>|<span data-ttu-id="54ea9-129">application/x-ms-xbap</span><span class="sxs-lookup"><span data-stu-id="54ea9-129">application/x-ms-xbap</span></span>|
|<span data-ttu-id="54ea9-130">.deploy</span><span class="sxs-lookup"><span data-stu-id="54ea9-130">.deploy</span></span>|<span data-ttu-id="54ea9-131">application/octet-stream</span><span class="sxs-lookup"><span data-stu-id="54ea9-131">application/octet-stream</span></span>|
|<span data-ttu-id="54ea9-132">.xps</span><span class="sxs-lookup"><span data-stu-id="54ea9-132">.xps</span></span>|<span data-ttu-id="54ea9-133">application/vnd.ms-xpsdocument</span><span class="sxs-lookup"><span data-stu-id="54ea9-133">application/vnd.ms-xpsdocument</span></span>|

> [!NOTE]
> <span data-ttu-id="54ea9-134">无需在客户端系统上注册 MIME 类型或文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="54ea9-134">You do not need to register MIME types or file extensions on client systems.</span></span> <span data-ttu-id="54ea9-135">当你安装 Microsoft .NET Framework 时，它们会自动注册。</span><span class="sxs-lookup"><span data-stu-id="54ea9-135">They are registered automatically when you install Microsoft .NET Framework.</span></span>

<span data-ttu-id="54ea9-136">以下 Microsoft Visual Basic Scripting Edition (VBScript) 示例自动将所需的 MIME 类型添加到 IIS。</span><span class="sxs-lookup"><span data-stu-id="54ea9-136">The following Microsoft Visual Basic Scripting Edition (VBScript) sample automatically adds the necessary MIME types to IIS.</span></span> <span data-ttu-id="54ea9-137">若要使用该脚本，请将代码复制到服务器上的 .vbs 文件。</span><span class="sxs-lookup"><span data-stu-id="54ea9-137">To use the script, copy the code to a .vbs file on your server.</span></span> <span data-ttu-id="54ea9-138">然后，通过从命令行运行该文件或在 Microsoft Windows 资源管理器中双击该文件来运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="54ea9-138">Then, run the script by running the file from the command line or double-clicking the file in Microsoft Windows Explorer.</span></span>

```vb
' This script adds the necessary Windows Presentation Foundation MIME types
' to an IIS Server.
' To use this script, just double-click or execute it from a command line.
' Running this script multiple times results in multiple entries in the IIS MimeMap.

Dim MimeMapObj, MimeMapArray, MimeTypesToAddArray, WshShell, oExec
Const ADS_PROPERTY_UPDATE = 2

' Set the MIME types to be added
MimeTypesToAddArray = Array(".manifest", "application/manifest", ".xaml", _
    "application/xaml+xml", ".application", "application/x-ms-application", _
    ".deploy", "application/octet-stream", ".xbap", "application/x-ms-xbap", _
    ".xps", "application/vnd.ms-xpsdocument")

' Get the MimeMap object
Set MimeMapObj = GetObject("IIS://LocalHost/MimeMap")

' Call AddMimeType for every pair of extension/MIME type
For counter = 0 to UBound(MimeTypesToAddArray) Step 2
    AddMimeType MimeTypesToAddArray(counter), MimeTypesToAddArray(counter+1)
Next

' Create a Shell object
Set WshShell = CreateObject("WScript.Shell")

' Stop and Start the IIS Service
Set oExec = WshShell.Exec("net stop w3svc")
Do While oExec.Status = 0
    WScript.Sleep 100
Loop

Set oExec = WshShell.Exec("net start w3svc")
Do While oExec.Status = 0
    WScript.Sleep 100
Loop

Set oExec = Nothing

' Report status to user
WScript.Echo "Windows Presentation Foundation MIME types have been registered."

' AddMimeType Sub
Sub AddMimeType (Ext, MType)

    ' Get the mappings from the MimeMap property.
    MimeMapArray = MimeMapObj.GetEx("MimeMap")

    ' Add a new mapping.
    i = UBound(MimeMapArray) + 1
    ReDim Preserve MimeMapArray(i)
    Set MimeMapArray(i) = CreateObject("MimeMap")
    MimeMapArray(i).Extension = Ext
    MimeMapArray(i).MimeType = MType
    MimeMapObj.PutEx ADS_PROPERTY_UPDATE, "MimeMap", MimeMapArray
    MimeMapObj.SetInfo

End Sub
```

> [!NOTE]
> <span data-ttu-id="54ea9-139">多次运行此脚本时，将会在 Microsoft Internet Information Services (IIS) 5.0 或 Microsoft Internet Information Services () 6.0 IIS 元数据库中创建多个 MIME 映射条目。</span><span class="sxs-lookup"><span data-stu-id="54ea9-139">Running this script multiple times creates multiple MIME map entries in the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 metabase.</span></span>

<span data-ttu-id="54ea9-140">运行此脚本后，你可能看不到 Microsoft Internet Information Services 中的其他 MIME 类型 (IIS) 5.0 或 Microsoft Internet Information Services (6.0) 的 () MMC。</span><span class="sxs-lookup"><span data-stu-id="54ea9-140">After you have run this script, you may not see additional MIME types from the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 Microsoft Management Console (MMC).</span></span> <span data-ttu-id="54ea9-141">不过，这些 MIME 类型已添加到 Microsoft Internet Information Services (IIS) 5.0 或 Microsoft Internet Information Services () 6.0 IIS 元数据库。</span><span class="sxs-lookup"><span data-stu-id="54ea9-141">However, these MIME types have been added to the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 metabase.</span></span> <span data-ttu-id="54ea9-142">下面的脚本将在 Microsoft Internet Information Services 中显示 (IIS) 5.0 或 Microsoft Internet Information Services (IIS) 6.0 元数据库中的所有 MIME 类型。</span><span class="sxs-lookup"><span data-stu-id="54ea9-142">The following script will display all the MIME types in the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 metabase.</span></span>

```vb
' This script lists the MIME types for an IIS Server.
' To use this script, just double-click or execute it from a command line
' by calling cscript.exe

dim mimeMapEntry, allMimeMaps

' Get the MimeMap object.
Set mimeMapEntry = GetObject("IIS://localhost/MimeMap")
allMimeMaps = mimeMapEntry.GetEx("MimeMap")

' Display the mappings in the table.
For Each mimeMap In allMimeMaps
    WScript.Echo(mimeMap.MimeType & " (" & mimeMap.Extension + ")")
Next
```

<span data-ttu-id="54ea9-143">将脚本另存为 `.vbs` 文件（例如，`DiscoverIISMimeTypes.vbs`），并使用以下命令从命令提示符运行它：</span><span class="sxs-lookup"><span data-stu-id="54ea9-143">Save the script as a `.vbs` file (for example, `DiscoverIISMimeTypes.vbs`) and run it from the command prompt using the following command:</span></span>

```console
cscript DiscoverIISMimeTypes.vbs
```
