---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: eb4b6a22a6f2f5de138ff3795dd32058f87cdb7a
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970222"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="6ada6-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="6ada6-102">IWpfHostSupport</span></span>

<span data-ttu-id="6ada6-103">通过 PresentationHost.exe 承载内容的应用程序 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 实现此接口，以提供主机与 PresentationHost.exe 之间的集成点。</span><span class="sxs-lookup"><span data-stu-id="6ada6-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ada6-104">注解</span><span class="sxs-lookup"><span data-stu-id="6ada6-104">Remarks</span></span>  

 <span data-ttu-id="6ada6-105">Win32 应用程序（如 Web 浏览器）可承载 WPF 内容，其中包括 XAML 浏览器应用程序 (Xbap) 和松散 XAML。</span><span class="sxs-lookup"><span data-stu-id="6ada6-105">Win32 applications such as Web browsers can host WPF content, including XAML browser applications (XBAPs) and loose XAML.</span></span> <span data-ttu-id="6ada6-106">为了承载 WPF 内容，Win32 应用程序会创建 [WebBrowser 控件](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))的一个实例。</span><span class="sxs-lookup"><span data-stu-id="6ada6-106">To host WPF content, Win32 applications create an instance of the [WebBrowser control](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span></span> <span data-ttu-id="6ada6-107">若要承载，WPF 将创建 PresentationHost.exe 的实例，该实例向宿主提供承载的 WPF 内容以便在 [WebBrowser 控件](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))中显示。</span><span class="sxs-lookup"><span data-stu-id="6ada6-107">To be hosted, WPF creates an instance of PresentationHost.exe, which provides the hosted WPF content to the host for display in the [WebBrowser control](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span></span>  
  
 <span data-ttu-id="6ada6-108">启用的集成 `IWpfHostSupport` 允许 PresentationHost.exe 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6ada6-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
- <span data-ttu-id="6ada6-109">发现主机应用程序所需的 (人体学接口设备) 并注册到原始输入设备。</span><span class="sxs-lookup"><span data-stu-id="6ada6-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
- <span data-ttu-id="6ada6-110">从已注册的原始输入设备接收输入消息，并将相应的消息转发到主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ada6-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
- <span data-ttu-id="6ada6-111">查询主机应用程序以获取自定义进度和错误用户界面。</span><span class="sxs-lookup"><span data-stu-id="6ada6-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6ada6-112">此 API 预期仅支持在本地客户端计算机上使用</span><span class="sxs-lookup"><span data-stu-id="6ada6-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="6ada6-113">成员</span><span class="sxs-lookup"><span data-stu-id="6ada6-113">Members</span></span>  
  
|<span data-ttu-id="6ada6-114">成员</span><span class="sxs-lookup"><span data-stu-id="6ada6-114">Member</span></span>|<span data-ttu-id="6ada6-115">说明</span><span class="sxs-lookup"><span data-stu-id="6ada6-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ada6-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="6ada6-116">GetRawInputDevices</span></span>](getrawinputdevices.md)|<span data-ttu-id="6ada6-117">允许 PresentationHost.exe 发现主机应用程序感兴趣的原始输入的设备（人机接口设备）。</span><span class="sxs-lookup"><span data-stu-id="6ada6-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="6ada6-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="6ada6-118">FilterInputMessage</span></span>](filterinputmessage.md)|<span data-ttu-id="6ada6-119">除非返回 E_NOTIMP，否则每当收到一条消息时都会由 PresentationHost.exe 调用。</span><span class="sxs-lookup"><span data-stu-id="6ada6-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="6ada6-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="6ada6-120">GetCustomUI</span></span>](getcustomui.md)|<span data-ttu-id="6ada6-121">默认情况下，PresentationHost.exe 提供其自己的部署进度以及部署 WPF 内容时显示的部署错误用户界面。</span><span class="sxs-lookup"><span data-stu-id="6ada6-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
