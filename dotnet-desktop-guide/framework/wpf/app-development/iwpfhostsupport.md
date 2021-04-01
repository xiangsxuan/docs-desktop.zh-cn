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
# <a name="iwpfhostsupport"></a>IWpfHostSupport

通过 PresentationHost.exe 承载内容的应用程序 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 实现此接口，以提供主机与 PresentationHost.exe 之间的集成点。  
  
## <a name="remarks"></a>备注  

 Win32 应用程序（如 Web 浏览器）可承载 WPF 内容，其中包括 XAML 浏览器应用程序 (Xbap) 和松散 XAML。 为了承载 WPF 内容，Win32 应用程序会创建 [WebBrowser 控件](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))的一个实例。 若要承载，WPF 将创建 PresentationHost.exe 的实例，该实例向宿主提供承载的 WPF 内容以便在 [WebBrowser 控件](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))中显示。  
  
 启用的集成 `IWpfHostSupport` 允许 PresentationHost.exe 执行以下操作：  
  
- 发现主机应用程序所需的 (人体学接口设备) 并注册到原始输入设备。  
  
- 从已注册的原始输入设备接收输入消息，并将相应的消息转发到主机应用程序。  
  
- 查询主机应用程序以获取自定义进度和错误用户界面。  
  
> [!NOTE]
> 此 API 预期仅支持在本地客户端计算机上使用  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|[GetRawInputDevices](getrawinputdevices.md)|允许 PresentationHost.exe 发现主机应用程序感兴趣的原始输入的设备（人机接口设备）。|  
|[FilterInputMessage](filterinputmessage.md)|除非返回 E_NOTIMP，否则每当收到一条消息时都会由 PresentationHost.exe 调用。|  
|[GetCustomUI](getcustomui.md)|默认情况下，PresentationHost.exe 提供其自己的部署进度以及部署 WPF 内容时显示的部署错误用户界面。|
