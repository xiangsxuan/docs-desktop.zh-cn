---
title: 如何：使 Tab 键能够移出 ToolStrip 控件
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: 7fee9f685b9a9b402cbfe9c265669f7905434986
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971177"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a><span data-ttu-id="27606-102">如何：使 Tab 键能够移出 ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="27606-102">How to: Enable the TAB Key to Move Out of a ToolStrip Control</span></span>
<span data-ttu-id="27606-103">使用以下过程，用户可以按 TAB 键，按 tab 键顺序移出 <xref:System.Windows.Forms.ToolStrip> 到下一个控件。</span><span class="sxs-lookup"><span data-stu-id="27606-103">Use the following procedure to enable the user to press the TAB key to move out of a <xref:System.Windows.Forms.ToolStrip> to the next control in the tab order.</span></span>  
  
 <span data-ttu-id="27606-104"><xref:System.Windows.Forms.ToolStrip>接受第一次按 tab 键，并在中选择项 <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="27606-104">The <xref:System.Windows.Forms.ToolStrip> accepts the first press of the TAB key, and the arrow keys select items within the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="27606-105">当用户第二次按 TAB 键时，它会将用户转到 tab 键顺序中的下一个控件。</span><span class="sxs-lookup"><span data-stu-id="27606-105">When the user presses the TAB key a second time, it takes the user to the next control in the tab order.</span></span>  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a><span data-ttu-id="27606-106">使用户可以按 TAB 键移出 ToolStrip 到下一个控件</span><span class="sxs-lookup"><span data-stu-id="27606-106">To enable the user to press the TAB key to move out of a ToolStrip to the next control</span></span>  
  
- <span data-ttu-id="27606-107">将 <xref:System.Windows.Forms.ToolStrip> 的 <xref:System.Windows.Forms.ToolStrip.TabStop%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="27606-107">Set the <xref:System.Windows.Forms.ToolStrip.TabStop%2A> property of the <xref:System.Windows.Forms.ToolStrip> to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27606-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27606-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.TabStop%2A>
- [<span data-ttu-id="27606-109">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="27606-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
