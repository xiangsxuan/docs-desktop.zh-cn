---
title: NotifyIcon 组件概述
ms.date: 03/30/2017
f1_keywords:
- NotifyIcon
helpviewer_keywords:
- NotifyIcon component [Windows Forms], about NotifyIcon component
- system tray icons [Windows Forms], about system tray icons
- system tray icons [Windows Forms], using in Windows Forms
ms.assetid: 5b9189fa-d4ae-41a6-9b97-eb1f44bb1a69
ms.openlocfilehash: 587bf514db853f1122ed16abc05a195985c5ce8d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972605"
---
# <a name="notifyicon-component-overview-windows-forms"></a><span data-ttu-id="da7f7-102">NotifyIcon 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="da7f7-102">NotifyIcon Component Overview (Windows Forms)</span></span>

<span data-ttu-id="da7f7-103">Windows 窗体 <xref:System.Windows.Forms.NotifyIcon> 组件通常用于显示在后台运行且大部分时间不显示用户界面的进程的图标。</span><span class="sxs-lookup"><span data-stu-id="da7f7-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component is typically used to display icons for processes that run in the background and do not show a user interface much of the time.</span></span> <span data-ttu-id="da7f7-104">例如，可通过单击任务栏的状态通知区域中的图标访问的病毒防护程序。</span><span class="sxs-lookup"><span data-stu-id="da7f7-104">An example would be a virus protection program that can be accessed by clicking an icon in the status notification area of the taskbar.</span></span>

## <a name="key-properties-of-notifyicons"></a><span data-ttu-id="da7f7-105">NotifyIcons 的键属性</span><span class="sxs-lookup"><span data-stu-id="da7f7-105">Key Properties of NotifyIcons</span></span>

<span data-ttu-id="da7f7-106">每个 <xref:System.Windows.Forms.NotifyIcon> 组件均显示状态区域中的一个图标。</span><span class="sxs-lookup"><span data-stu-id="da7f7-106">Each <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status area.</span></span> <span data-ttu-id="da7f7-107">如果你有三个后台进程，并希望为每个进程显示一个图标，则必须添加三个 <xref:System.Windows.Forms.NotifyIcon> 组件到窗体。</span><span class="sxs-lookup"><span data-stu-id="da7f7-107">If you have three background processes and wish to display an icon for each, you must add three <xref:System.Windows.Forms.NotifyIcon> components to the form.</span></span> <span data-ttu-id="da7f7-108"><xref:System.Windows.Forms.NotifyIcon> 组件的键属性为 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 和 <xref:System.Windows.Forms.NotifyIcon.Visible%2A>。</span><span class="sxs-lookup"><span data-stu-id="da7f7-108">The key properties of the <xref:System.Windows.Forms.NotifyIcon> component are <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.</span></span> <span data-ttu-id="da7f7-109"><xref:System.Windows.Forms.NotifyIcon.Icon%2A> 属性设置状态区域中显示的图标。</span><span class="sxs-lookup"><span data-stu-id="da7f7-109">The <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property sets the icon that appears in the status area.</span></span> <span data-ttu-id="da7f7-110">为了显示图标，必须将 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="da7f7-110">In order for the icon to appear, the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property must be set to `true`.</span></span>

## <a name="notifyicons-options"></a><span data-ttu-id="da7f7-111">NotifyIcons 选项</span><span class="sxs-lookup"><span data-stu-id="da7f7-111">NotifyIcons Options</span></span>

<span data-ttu-id="da7f7-112">你可以将气球提示、快捷菜单和工具提示与 <xref:System.Windows.Forms.NotifyIcon> 进行关联，以辅助用户。</span><span class="sxs-lookup"><span data-stu-id="da7f7-112">You can associate balloon tips, shortcut menus, and ToolTips with a <xref:System.Windows.Forms.NotifyIcon> to assist the user.</span></span>

<span data-ttu-id="da7f7-113">你可以通过调用 <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> 方法来指定需要气球提示显示的时间跨度，从而显示 <xref:System.Windows.Forms.NotifyIcon> 的气球提示。</span><span class="sxs-lookup"><span data-stu-id="da7f7-113">You can display balloon tips for a <xref:System.Windows.Forms.NotifyIcon> by calling the <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> method specifying the time span you wish the balloon tip to display.</span></span> <span data-ttu-id="da7f7-114">还可以为气球提示的文本、图标和标题分别指定 <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>、<xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> 和 <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A>。</span><span class="sxs-lookup"><span data-stu-id="da7f7-114">You can also specify the text, icon and title of the balloon tip with the <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> and <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A>, respectively.</span></span> <span data-ttu-id="da7f7-115"><xref:System.Windows.Forms.NotifyIcon> 组件还可以具有相关联的工具提示和快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="da7f7-115"><xref:System.Windows.Forms.NotifyIcon> components can also have associated ToolTips and shortcut menus.</span></span> <span data-ttu-id="da7f7-116">有关详细信息，请参阅 [ToolTip 组件概述](tooltip-component-overview-windows-forms.md) 和 [ContextMenu 组件概述](contextmenu-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="da7f7-116">For more information, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md) and [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="da7f7-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da7f7-117">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- [<span data-ttu-id="da7f7-118">NotifyIcon 组件</span><span class="sxs-lookup"><span data-stu-id="da7f7-118">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
