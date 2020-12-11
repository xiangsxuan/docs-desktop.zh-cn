---
title: WebBrowser 安全
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: 3412a775cd62723bb1d7ab8548b8a89ea05ad7f6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972485"
---
# <a name="webbrowser-security"></a><span data-ttu-id="e3650-102">WebBrowser 安全</span><span class="sxs-lookup"><span data-stu-id="e3650-102">WebBrowser Security</span></span>

<span data-ttu-id="e3650-103"><xref:System.Windows.Forms.WebBrowser>控件设计为仅在完全信任环境中运行。</span><span class="sxs-lookup"><span data-stu-id="e3650-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="e3650-104">控件中显示的 HTML 内容可以来自外部 Web 服务器，并且可能包含脚本或 Web 控件形式的非托管代码。</span><span class="sxs-lookup"><span data-stu-id="e3650-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="e3650-105">如果 <xref:System.Windows.Forms.WebBrowser> 在这种情况下使用控件，则该控件的安全性不如 Internet Explorer，而托管控件不会 <xref:System.Windows.Forms.WebBrowser> 阻止此类非托管代码运行。</span><span class="sxs-lookup"><span data-stu-id="e3650-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="e3650-106">有关与基础 ActiveX 控件相关的安全问题的详细信息 `WebBrowser` ，请参阅 [WebBrowser 控件](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))。</span><span class="sxs-lookup"><span data-stu-id="e3650-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3650-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3650-107">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="e3650-108">WebBrowser 控件概述</span><span class="sxs-lookup"><span data-stu-id="e3650-108">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- <span data-ttu-id="e3650-109">[WebBrowser 控件](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="e3650-109">[WebBrowser Control](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))</span></span>
