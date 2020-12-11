---
title: 本机浏览器承载支持 Api
ms.date: 03/30/2017
f1_keywords:
- AutoGeneratedOrientationPage
helpviewer_keywords:
- browser hosting support [WPF]
- WPF browser hosting support APIs [WPF]
ms.assetid: 82c133a8-d760-45fb-a2b9-3a997537f1d4
ms.openlocfilehash: c4332f466616cfb2c62c9ab63a841cc004fe518c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972971"
---
# <a name="native-wpf-browser-hosting-support-apis"></a><span data-ttu-id="40ba7-102">承载支持 API 的本机 WPF 浏览器</span><span class="sxs-lookup"><span data-stu-id="40ba7-102">Native WPF Browser Hosting Support APIs</span></span>

<span data-ttu-id="40ba7-103">通过在 Web 浏览器中承载 WPF 应用程序， (也称为从 WPF 宿主注册的 DocObject) 。</span><span class="sxs-lookup"><span data-stu-id="40ba7-103">Hosting of WPF applications in Web browsers is facilitated by an Active Document server (also known as a DocObject) registered out of the WPF Host.</span></span> <span data-ttu-id="40ba7-104">Internet Explorer 可以直接激活并与活动文档集成。</span><span class="sxs-lookup"><span data-stu-id="40ba7-104">Internet Explorer can directly activate and integrate with an Active Document.</span></span> <span data-ttu-id="40ba7-105">为了在 Mozilla 浏览器中承载 Xbap 和松散 XAML 文档，WPF 提供了一个 NPAPI 插件，该插件提供与 Internet Explorer 相同的 WPF 活动文档服务器的宿主环境。</span><span class="sxs-lookup"><span data-stu-id="40ba7-105">For hosting of XBAPs and loose XAML documents in Mozilla browsers, WPF provides an NPAPI plugin, which provides a similar hosting environment to the WPF Active Document server as Internet Explorer does.</span></span> <span data-ttu-id="40ba7-106">但是，在其他浏览器和独立应用程序中托管 Xbap 和 XAML 文档的最简单的方法是通过 Internet Explorer Web 浏览器控件。</span><span class="sxs-lookup"><span data-stu-id="40ba7-106">However, the easiest practical way to host XBAPs and XAML documents in other browsers and standalone applications is via the Internet Explorer Web Browser control.</span></span> <span data-ttu-id="40ba7-107">Web 浏览器控件提供了复杂的活动文档服务器宿主环境，同时它还允许自己的主机自定义和扩展该环境，并直接与当前活动文档对象进行通信。</span><span class="sxs-lookup"><span data-stu-id="40ba7-107">The Web Browser control provides the complex Active Document server hosting environment, yet it enables its own host to customize and extend that environment and communicate directly with the current Active Document object.</span></span>  
  
 <span data-ttu-id="40ba7-108">WPF 活动文档服务器实现了几个常见的宿主接口，包括 [IOleObject](/windows/win32/api/oleidl/nn-oleidl-ioleobject)、 [IOleDocument](/windows/win32/api/docobj/nn-docobj-ioledocument)、 [IOleInPlaceActiveObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceactiveobject)、 [IPersistMoniker](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775042(v=vs.85))、 [IOleCommandTarget](/windows/win32/api/docobj/nn-docobj-iolecommandtarget)。</span><span class="sxs-lookup"><span data-stu-id="40ba7-108">The WPF Active Document server implements several common hosting interfaces, including [IOleObject](/windows/win32/api/oleidl/nn-oleidl-ioleobject), [IOleDocument](/windows/win32/api/docobj/nn-docobj-ioledocument), [IOleInPlaceActiveObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceactiveobject), [IPersistMoniker](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775042(v=vs.85)), [IOleCommandTarget](/windows/win32/api/docobj/nn-docobj-iolecommandtarget).</span></span> <span data-ttu-id="40ba7-109">在 Web 浏览器控件中承载时，可以从 [IWebBrowser2：:D 文档](/previous-versions/aa752116(v=vs.85)) 属性返回的对象查询这些接口。</span><span class="sxs-lookup"><span data-stu-id="40ba7-109">When hosted in the Web Browser control, these interfaces can be queries from the object returned by the [IWebBrowser2::Document](/previous-versions/aa752116(v=vs.85)) property.</span></span>  
  
## <a name="iolecommandtarget"></a><span data-ttu-id="40ba7-110">IOleCommandTarget</span><span class="sxs-lookup"><span data-stu-id="40ba7-110">IOleCommandTarget</span></span>  

 <span data-ttu-id="40ba7-111">WPF 活动文档服务器的 [IOleCommandTarget](/windows/win32/api/docobj/nn-docobj-iolecommandtarget) 实现支持使用 null 命令组 GUID)  (标准 OLE 命令组的大量导航相关的命令和特定于浏览器的命令。</span><span class="sxs-lookup"><span data-stu-id="40ba7-111">WPF Active Document server's implementation of [IOleCommandTarget](/windows/win32/api/docobj/nn-docobj-iolecommandtarget) supports numerous navigation-related and browser-specific commands of the standard OLE command group (with a null command group GUID).</span></span> <span data-ttu-id="40ba7-112">此外，它还识别名为 CGID_PresentationHost 的自定义命令组。</span><span class="sxs-lookup"><span data-stu-id="40ba7-112">In addition, it recognizes a custom command group called CGID_PresentationHost.</span></span> <span data-ttu-id="40ba7-113">目前，此组中仅定义了一个命令。</span><span class="sxs-lookup"><span data-stu-id="40ba7-113">Currently, there is only one command defined within this group.</span></span>  
  
```cpp  
DEFINE_GUID(CGID_PresentationHost, 0xd0288c55, 0xd6, 0x4f5e, 0xa8, 0x51, 0x79, 0xde, 0xc5, 0x1b, 0x10, 0xec);  
enum PresentationHostCommands {
   PHCMDID_TABINTO = 1
};  
```  
  
 <span data-ttu-id="40ba7-114">PHCMDID_TABINTO 指示 Presentationhost.exe 将焦点切换到其内容中的第一个或最后一个可设定焦点的元素，具体取决于 Shift 键的状态。</span><span class="sxs-lookup"><span data-stu-id="40ba7-114">PHCMDID_TABINTO instructs PresentationHost to switch focus to the first or last focusable element in its content, depending on the state of the Shift key.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="40ba7-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="40ba7-115">In This Section</span></span>  

 [<span data-ttu-id="40ba7-116">IEnumRAWINPUTDEVICE</span><span class="sxs-lookup"><span data-stu-id="40ba7-116">IEnumRAWINPUTDEVICE</span></span>](ienumrawinputdevice.md)  
 [<span data-ttu-id="40ba7-117">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="40ba7-117">IWpfHostSupport</span></span>](iwpfhostsupport.md)