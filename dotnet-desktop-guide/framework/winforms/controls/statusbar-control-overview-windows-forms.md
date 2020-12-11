---
title: StatusBar 控件概述
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: b0b97bc3cb0291871e1fd113d82d0b480b53cdba
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973010"
---
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="3625f-102">StatusBar 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="3625f-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="3625f-103"><xref:System.Windows.Forms.StatusStrip>和 <xref:System.Windows.Forms.ToolStripStatusLabel> 控件替换和添加了 <xref:System.Windows.Forms.StatusBar> 和控件的功能 <xref:System.Windows.Forms.StatusBarPanel> ; 但是， <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> 如果你选择，和控件将保留以实现向后兼容性和将来使用。</span><span class="sxs-lookup"><span data-stu-id="3625f-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="3625f-104">Windows 窗体 [状态栏控件](statusbar-control-windows-forms.md) 在窗体上用作区域，通常显示在窗口底部，应用程序可在窗口中显示各种类型的状态信息。</span><span class="sxs-lookup"><span data-stu-id="3625f-104">The Windows Forms [StatusBar Control](statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="3625f-105"><xref:System.Windows.Forms.StatusBar> 控件可在其上具有状态栏面板，这些面板显示用于指示状态的文本或图标，或动画中指示进程工作的一系列图标。例如，Microsoft Word 表明文档正在保存。</span><span class="sxs-lookup"><span data-stu-id="3625f-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="3625f-106">使用 "状态栏" 控件</span><span class="sxs-lookup"><span data-stu-id="3625f-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="3625f-107">当鼠标滚动到超链接上时，Internet Explorer 将使用状态栏来指示页面的 URL;Microsoft Word 提供了有关页面位置、分区位置和编辑模式（如改写和修订跟踪）的信息;Visual Studio 使用状态栏为上下文相关的信息，如告诉您如何操作停靠或浮动的窗口。</span><span class="sxs-lookup"><span data-stu-id="3625f-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; Microsoft Word gives you information on page location, section location, and editing modes such as overtype and revision tracking; and Visual Studio uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="3625f-108">您可以通过将 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 属性设置为 `false` (默认) 并将 <xref:System.Windows.Forms.StatusBar.Text%2A> 状态栏的属性设置为要在状态栏中显示的文本，在状态栏上显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="3625f-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="3625f-109">您可以通过将 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 属性设置为 `true` 并使用的方法，将状态栏划分为多个面板以显示多种类型的信息 <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> 。</span><span class="sxs-lookup"><span data-stu-id="3625f-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3625f-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3625f-110">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="3625f-111">如何：确定 Windows 窗体 StatusBar 控件中被单击的面板</span><span class="sxs-lookup"><span data-stu-id="3625f-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
