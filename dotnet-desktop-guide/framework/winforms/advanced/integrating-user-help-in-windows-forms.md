---
title: 集成用户帮助
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows Forms (using designer)
- Windows Forms, Help (using designer)
- HTML Help [Windows Forms], Windows Forms (using designer)
- Help [Windows Forms], Windows applications (using designer)
- forms. Help (using designer)
- Windows applications [Windows Forms], Help (using designer)
ms.assetid: a8563d25-8a75-4bc7-a024-f1870591b50f
ms.openlocfilehash: e1d9921b01c1fafe690a2727f2a45443d6f42728
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971625"
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="c8cf0-102">在 Windows 窗体中集成用户帮助</span><span class="sxs-lookup"><span data-stu-id="c8cf0-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="c8cf0-103">构建基于 Windows 的应用程序的一个重要而又经常被忽略的方面是帮助系统，因为用户在这种情况下会在混乱时提供帮助。</span><span class="sxs-lookup"><span data-stu-id="c8cf0-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="c8cf0-104">Windows 窗体支持两种不同类型的帮助，每种类型都由 [HelpProvider 组件](../controls/helpprovider-component-windows-forms.md)提供。</span><span class="sxs-lookup"><span data-stu-id="c8cf0-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="c8cf0-105">第一种方法是将用户指向 HTML 或 HTML 帮助1的帮助文件。*x* 或更高格式。</span><span class="sxs-lookup"><span data-stu-id="c8cf0-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="c8cf0-106">第二个可以显示简短的 "这是什么"-每个控件的类型帮助;这对于对话框特别有用。</span><span class="sxs-lookup"><span data-stu-id="c8cf0-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="c8cf0-107">这两种类型的帮助可以在同一窗体上使用。</span><span class="sxs-lookup"><span data-stu-id="c8cf0-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="c8cf0-108">此外， [ToolTip 组件](../controls/tooltip-component-windows-forms.md) 可用于为 Windows 窗体上的控件提供单独的帮助。</span><span class="sxs-lookup"><span data-stu-id="c8cf0-108">Additionally, the [ToolTip Component](../controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c8cf0-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="c8cf0-109">In This Section</span></span>  
 [<span data-ttu-id="c8cf0-110">如何：在 Windows 应用程序中提供帮助</span><span class="sxs-lookup"><span data-stu-id="c8cf0-110">How to: Provide Help in a Windows Application</span></span>](how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="c8cf0-111">介绍如何使用组件将 `HelpProvider` 控件链接到帮助系统中的文件。</span><span class="sxs-lookup"><span data-stu-id="c8cf0-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="c8cf0-112">如何：显示弹出帮助</span><span class="sxs-lookup"><span data-stu-id="c8cf0-112">How to: Display Pop-up Help</span></span>](how-to-display-pop-up-help.md)  
 <span data-ttu-id="c8cf0-113">说明如何使用 `HelpProvider` 组件显示有关 Windows 窗体的弹出帮助。</span><span class="sxs-lookup"><span data-stu-id="c8cf0-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="c8cf0-114">使用工具提示的控件帮助</span><span class="sxs-lookup"><span data-stu-id="c8cf0-114">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)  
 <span data-ttu-id="c8cf0-115">介绍如何使用 `ToolTip` 组件显示特定于控件的帮助。</span><span class="sxs-lookup"><span data-stu-id="c8cf0-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c8cf0-116">相关章节</span><span class="sxs-lookup"><span data-stu-id="c8cf0-116">Related Sections</span></span>  
 [<span data-ttu-id="c8cf0-117">HelpProvider 组件</span><span class="sxs-lookup"><span data-stu-id="c8cf0-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="c8cf0-118">介绍组件的基础知识 `HelpProvider` 。</span><span class="sxs-lookup"><span data-stu-id="c8cf0-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="c8cf0-119">ToolTip 组件</span><span class="sxs-lookup"><span data-stu-id="c8cf0-119">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="c8cf0-120">介绍组件的基础知识 `ToolTip` 。</span><span class="sxs-lookup"><span data-stu-id="c8cf0-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="c8cf0-121">Windows 窗体概述</span><span class="sxs-lookup"><span data-stu-id="c8cf0-121">Windows Forms Overview</span></span>](../windows-forms-overview.md)  
 <span data-ttu-id="c8cf0-122">介绍 Windows 窗体的基础知识。</span><span class="sxs-lookup"><span data-stu-id="c8cf0-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="c8cf0-123">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="c8cf0-123">Windows Forms</span></span>](../index.yml)  
 <span data-ttu-id="c8cf0-124">提供 Windows 窗体的概述。</span><span class="sxs-lookup"><span data-stu-id="c8cf0-124">Provides an overview of Windows Forms.</span></span>
