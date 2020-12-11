---
title: 帮助系统
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], adding to Windows applications
- Windows applications [Windows Forms], providing Help systems
- What's This? Help
- Help [Windows Forms], Windows Forms
- HelpProvider component [Windows Forms], providing Help in Windows applications
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
ms.openlocfilehash: 07e13ff35de49ae3ec7591544b1c9353ba4bb378
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970806"
---
# <a name="help-systems-in-windows-forms-applications"></a><span data-ttu-id="4aa37-102">Windows 窗体应用程序中的帮助系统</span><span class="sxs-lookup"><span data-stu-id="4aa37-102">Help Systems in Windows Forms Applications</span></span>
<span data-ttu-id="4aa37-103">作为应用程序开发人员，作为应用程序开发人员，最重要的礼节之一就是提供有帮助的帮助系统。</span><span class="sxs-lookup"><span data-stu-id="4aa37-103">One of the most important courtesies you, as a developer of applications, can furnish your users with is a competent Help system.</span></span> <span data-ttu-id="4aa37-104">在这种情况下，它们会在出现混乱或 disoriented 的情况下打开。</span><span class="sxs-lookup"><span data-stu-id="4aa37-104">This is where they will turn when they become confused or disoriented.</span></span> <span data-ttu-id="4aa37-105">使用 [HelpProvider 组件](../controls/helpprovider-component-windows-forms.md)，可以轻松地在基于 Windows 的应用程序中提供帮助系统。</span><span class="sxs-lookup"><span data-stu-id="4aa37-105">Providing a Help system in a Windows-based application is easily done by using the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span>  
  
## <a name="different-types-of-help"></a><span data-ttu-id="4aa37-106">不同类型的帮助</span><span class="sxs-lookup"><span data-stu-id="4aa37-106">Different Types of Help</span></span>  
 <span data-ttu-id="4aa37-107">Windows 窗体 <xref:System.Windows.Forms.HelpProvider> 组件用于将基于 Windows 的应用程序与 HTML Help 1.x 帮助文件（HTML Help Workshop 生成的 .chm 文件，或 .htm 文件）关联。</span><span class="sxs-lookup"><span data-stu-id="4aa37-107">The Windows Forms <xref:System.Windows.Forms.HelpProvider> component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows-based application.</span></span> <span data-ttu-id="4aa37-108"><xref:System.Windows.Forms.HelpProvider>组件可用于为 Windows 窗体或特定控件上的控件提供区分上下文的帮助。</span><span class="sxs-lookup"><span data-stu-id="4aa37-108">The <xref:System.Windows.Forms.HelpProvider> component can be used to provide context-sensitive Help for controls on Windows Forms or specific controls.</span></span> <span data-ttu-id="4aa37-109">此外，该 <xref:System.Windows.Forms.HelpProvider> 组件还可以在特定区域（如目录的主页、索引或搜索功能）打开帮助文件。</span><span class="sxs-lookup"><span data-stu-id="4aa37-109">Additionally, the <xref:System.Windows.Forms.HelpProvider> component can open a Help file to specific areas, such as the main page of a table of contents, an index, or a search function.</span></span> <span data-ttu-id="4aa37-110">有关组件的常规信息 <xref:System.Windows.Forms.HelpProvider> ，请参阅 [HelpProvider 组件概述](../controls/helpprovider-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="4aa37-110">For general information about the <xref:System.Windows.Forms.HelpProvider> component, see [HelpProvider Component Overview](../controls/helpprovider-component-overview-windows-forms.md).</span></span> <span data-ttu-id="4aa37-111">有关如何使用 <xref:System.Windows.Forms.HelpProvider> 组件显示 Windows 窗体上的弹出帮助的信息，请参阅 [如何：显示弹出帮助](how-to-display-pop-up-help.md)。</span><span class="sxs-lookup"><span data-stu-id="4aa37-111">For information on how to use the <xref:System.Windows.Forms.HelpProvider> component to show pop-up Help on Windows Forms, see [How to: Display Pop-up Help](how-to-display-pop-up-help.md).</span></span> <span data-ttu-id="4aa37-112">有关使用 <xref:System.Windows.Forms.ToolTip> 组件显示特定于控件的帮助的信息，请参阅 [使用工具提示的控件帮助](control-help-using-tooltips.md)。</span><span class="sxs-lookup"><span data-stu-id="4aa37-112">For information on using the <xref:System.Windows.Forms.ToolTip> component to show control-specific Help, see [Control Help Using ToolTips](control-help-using-tooltips.md).</span></span>  
  
 <span data-ttu-id="4aa37-113">可以通过 HTML 帮助讨论会生成 HTML Help 1.x 文件。</span><span class="sxs-lookup"><span data-stu-id="4aa37-113">You can generate HTML Help 1.x files with the HTML Help Workshop.</span></span> <span data-ttu-id="4aa37-114">有关 HTML 帮助的详细信息，请参阅 MSDN 中的 "HTML 帮助讨论会" 或其他 "HTML 帮助" 主题。</span><span class="sxs-lookup"><span data-stu-id="4aa37-114">For more information on HTML Help, see the "HTML Help Workshop" or the other "HTML Help" topics in MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aa37-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4aa37-115">See also</span></span>

- [<span data-ttu-id="4aa37-116">在 Windows 窗体中集成用户帮助</span><span class="sxs-lookup"><span data-stu-id="4aa37-116">Integrating User Help in Windows Forms</span></span>](integrating-user-help-in-windows-forms.md)
- [<span data-ttu-id="4aa37-117">HelpProvider 组件</span><span class="sxs-lookup"><span data-stu-id="4aa37-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)
- [<span data-ttu-id="4aa37-118">ToolTip 组件</span><span class="sxs-lookup"><span data-stu-id="4aa37-118">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)
- [<span data-ttu-id="4aa37-119">Windows 窗体概述</span><span class="sxs-lookup"><span data-stu-id="4aa37-119">Windows Forms Overview</span></span>](../windows-forms-overview.md)
- [<span data-ttu-id="4aa37-120">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="4aa37-120">Windows Forms</span></span>](../index.yml)
