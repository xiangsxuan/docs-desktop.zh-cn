---
title: 使用设计器将一个按钮指定为 "取消" 按钮
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: 95d1139b6e339055f944ad0b0967a6d91283d49e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970089"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a><span data-ttu-id="33b3e-102">如何：使用设计器将 Windows 窗体按钮指定为“取消”按钮</span><span class="sxs-lookup"><span data-stu-id="33b3e-102">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>
<span data-ttu-id="33b3e-103">在任何 Windows 窗体上，都可以将 <xref:System.Windows.Forms.Button> 控件指定为 "取消" 按钮。</span><span class="sxs-lookup"><span data-stu-id="33b3e-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="33b3e-104">用户按 ESC 键时单击 "取消" 按钮，而不考虑窗体上的其他哪个控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="33b3e-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="33b3e-105">通常对此类按钮进行编程，使用户能够快速退出操作，而无需提交任何操作。</span><span class="sxs-lookup"><span data-stu-id="33b3e-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>

## <a name="to-designate-the-cancel-button"></a><span data-ttu-id="33b3e-106">指定 "取消" 按钮</span><span class="sxs-lookup"><span data-stu-id="33b3e-106">To designate the cancel button</span></span>

1. <span data-ttu-id="33b3e-107">选择该按钮所在的窗体。</span><span class="sxs-lookup"><span data-stu-id="33b3e-107">Select the form on which the button resides.</span></span>

2. <span data-ttu-id="33b3e-108">在 " **属性** " 窗口中，将窗体的 <xref:System.Windows.Forms.Form.CancelButton%2A> 属性设置为 <xref:System.Windows.Forms.Button> 控件的名称。</span><span class="sxs-lookup"><span data-stu-id="33b3e-108">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>

## <a name="see-also"></a><span data-ttu-id="33b3e-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33b3e-109">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="33b3e-110">Button 控件概述</span><span class="sxs-lookup"><span data-stu-id="33b3e-110">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="33b3e-111">选择 Windows 窗体 Button 控件的方法</span><span class="sxs-lookup"><span data-stu-id="33b3e-111">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="33b3e-112">如何：响应 Windows 窗体按钮的单击</span><span class="sxs-lookup"><span data-stu-id="33b3e-112">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="33b3e-113">如何：使用设计器将 Windows 窗体按钮指定为“接受”按钮</span><span class="sxs-lookup"><span data-stu-id="33b3e-113">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [<span data-ttu-id="33b3e-114">Button 控件</span><span class="sxs-lookup"><span data-stu-id="33b3e-114">Button Control</span></span>](button-control-windows-forms.md)
