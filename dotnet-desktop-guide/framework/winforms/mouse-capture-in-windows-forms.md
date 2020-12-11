---
title: 鼠标捕获
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: 10583f074831b16dce3c713b4ac9a76c7005c9f5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972730"
---
# <a name="mouse-capture-in-windows-forms"></a><span data-ttu-id="f5298-102">Windows 窗体中的鼠标捕获</span><span class="sxs-lookup"><span data-stu-id="f5298-102">Mouse Capture in Windows Forms</span></span>
<span data-ttu-id="f5298-103">*鼠标捕获* 指的是控件使用所有鼠标输入的命令。</span><span class="sxs-lookup"><span data-stu-id="f5298-103">*Mouse capture* refers to when a control takes command of all mouse input.</span></span> <span data-ttu-id="f5298-104">当控件已捕获鼠标时，它将接收鼠标输入，无论指针是否在其边框内。</span><span class="sxs-lookup"><span data-stu-id="f5298-104">When a control has captured the mouse, it receives mouse input whether or not the pointer is within its borders.</span></span>  
  
## <a name="setting-mouse-capture"></a><span data-ttu-id="f5298-105">设置鼠标捕获</span><span class="sxs-lookup"><span data-stu-id="f5298-105">Setting Mouse Capture</span></span>  
 <span data-ttu-id="f5298-106">在 Windows 窗体当用户在控件上按下鼠标按钮时，由控件捕获鼠标，而当用户释放鼠标按钮时，鼠标由控件释放。</span><span class="sxs-lookup"><span data-stu-id="f5298-106">In Windows Forms the mouse is captured by the control when the user presses a mouse button on a control, and the mouse is released by the control when the user releases the mouse button.</span></span>  
  
 <span data-ttu-id="f5298-107"><xref:System.Windows.Forms.Control.Capture%2A>类的属性 <xref:System.Windows.Forms.Control> 指定控件是否已捕获鼠标。</span><span class="sxs-lookup"><span data-stu-id="f5298-107">The <xref:System.Windows.Forms.Control.Capture%2A> property of the <xref:System.Windows.Forms.Control> class specifies whether a control has captured the mouse.</span></span> <span data-ttu-id="f5298-108">若要确定控件何时失去了鼠标捕获，请处理 <xref:System.Windows.Forms.Control.MouseCaptureChanged> 事件。</span><span class="sxs-lookup"><span data-stu-id="f5298-108">To determine when a control loses mouse capture, handle the <xref:System.Windows.Forms.Control.MouseCaptureChanged> event.</span></span>  
  
 <span data-ttu-id="f5298-109">只有前景窗口才能捕获鼠标。</span><span class="sxs-lookup"><span data-stu-id="f5298-109">Only the foreground window can capture the mouse.</span></span> <span data-ttu-id="f5298-110">当后台窗口尝试捕获鼠标时，窗口仅接收鼠标指针位于窗口可见部分内时发生的鼠标事件的消息。</span><span class="sxs-lookup"><span data-stu-id="f5298-110">When a background window attempts to capture the mouse, the window receives messages only for mouse events that occur when the mouse pointer is within the visible portion of the window.</span></span> <span data-ttu-id="f5298-111">此外，即使前景窗口已捕获鼠标，用户仍可以单击其他窗口，使其成为前台。</span><span class="sxs-lookup"><span data-stu-id="f5298-111">Also, even if the foreground window has captured the mouse, the user can still click another window, bringing it to the foreground.</span></span> <span data-ttu-id="f5298-112">捕获鼠标时，快捷键不起作用。</span><span class="sxs-lookup"><span data-stu-id="f5298-112">When the mouse is captured, shortcut keys do not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5298-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5298-113">See also</span></span>

- [<span data-ttu-id="f5298-114">Windows 窗体应用程序中的鼠标输入</span><span class="sxs-lookup"><span data-stu-id="f5298-114">Mouse Input in a Windows Forms Application</span></span>](mouse-input-in-a-windows-forms-application.md)
