---
title: 更改 ToolTip 组件的延迟
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
ms.openlocfilehash: 8ab0b0760e8c82d752eaada19f14cae57fa63fdc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971887"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a><span data-ttu-id="a1af5-102">如何：更改 Windows 窗体 ToolTip 组件的延迟</span><span class="sxs-lookup"><span data-stu-id="a1af5-102">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>
<span data-ttu-id="a1af5-103">可以为 Windows 窗体组件设置多个延迟值 <xref:System.Windows.Forms.ToolTip> 。</span><span class="sxs-lookup"><span data-stu-id="a1af5-103">There are multiple delay values that you can set for a Windows Forms <xref:System.Windows.Forms.ToolTip> component.</span></span> <span data-ttu-id="a1af5-104">所有这些属性的度量单位是毫秒。</span><span class="sxs-lookup"><span data-stu-id="a1af5-104">The unit of measure for all these properties is milliseconds.</span></span> <span data-ttu-id="a1af5-105"><xref:System.Windows.Forms.ToolTip.InitialDelay%2A>属性确定用户必须指向关联控件才能显示 ToolTip 字符串的时间长度。</span><span class="sxs-lookup"><span data-stu-id="a1af5-105">The <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> property determines how long the user must point at the associated control for the ToolTip string to appear.</span></span> <span data-ttu-id="a1af5-106"><xref:System.Windows.Forms.ToolTip.ReshowDelay%2A>属性设置当鼠标从工具提示关联的控件移到另一控件时，后续工具提示字符串显示的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="a1af5-106">The <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> property sets the number of milliseconds it takes for subsequent ToolTip strings to appear as the mouse moves from one ToolTip-associated control to another.</span></span> <span data-ttu-id="a1af5-107"><xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A>属性确定显示工具提示字符串的时间长度。</span><span class="sxs-lookup"><span data-stu-id="a1af5-107">The <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> property determines the length of time the ToolTip string is shown.</span></span> <span data-ttu-id="a1af5-108">您可以单独设置这些值，也可以通过设置属性的值来设置这些值 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> ; 其他延迟属性根据分配给该属性的值设置 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 。</span><span class="sxs-lookup"><span data-stu-id="a1af5-108">You can set these values individually, or by setting the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property; the other delay properties are set based on the value assigned to the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property.</span></span> <span data-ttu-id="a1af5-109">例如，将设置为值 N 时，将设置为 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> n，并将 <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> 设置为 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 除以 5 (或 N/5) 的值，并 <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> 将设置为该属性的值为5倍的值 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> (或 5N) 。</span><span class="sxs-lookup"><span data-stu-id="a1af5-109">For example, when <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> is set to a value N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> is set to N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> is set to the value of <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> divided by five (or N/5), and <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> is set to a value that is five times the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property (or 5N).</span></span>  
  
### <a name="to-set-the-delay"></a><span data-ttu-id="a1af5-110">设置延迟</span><span class="sxs-lookup"><span data-stu-id="a1af5-110">To set the delay</span></span>  
  
1. <span data-ttu-id="a1af5-111">设置以下属性，如本示例中所示。</span><span class="sxs-lookup"><span data-stu-id="a1af5-111">Set the following properties as shown in this example.</span></span>  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a1af5-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1af5-112">See also</span></span>

- [<span data-ttu-id="a1af5-113">ToolTip 组件概述</span><span class="sxs-lookup"><span data-stu-id="a1af5-113">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="a1af5-114">如何：在设计时为 Windows 窗体上的控件设置 ToolTip</span><span class="sxs-lookup"><span data-stu-id="a1af5-114">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [<span data-ttu-id="a1af5-115">ToolTip 组件</span><span class="sxs-lookup"><span data-stu-id="a1af5-115">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
