---
title: ToolTip 组件概述
ms.date: 03/30/2017
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
ms.openlocfilehash: 731f7ad0ce6670000d8c3d3e901e1506f7ef470a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973049"
---
# <a name="tooltip-component-overview-windows-forms"></a><span data-ttu-id="636c5-102">ToolTip 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="636c5-102">ToolTip Component Overview (Windows Forms)</span></span>
<span data-ttu-id="636c5-103">Windows 窗体 <xref:System.Windows.Forms.ToolTip> 组件在用户指向控件时显示文本。</span><span class="sxs-lookup"><span data-stu-id="636c5-103">The Windows Forms <xref:System.Windows.Forms.ToolTip> component displays text when the user points at controls.</span></span> <span data-ttu-id="636c5-104">ToolTip 可与任何控件关联。</span><span class="sxs-lookup"><span data-stu-id="636c5-104">A ToolTip can be associated with any control.</span></span> <span data-ttu-id="636c5-105">此组件的示例用法：若要在窗体上节省空间，可以在按钮上显示小图标，并使用工具提示来解释该按钮的功能。</span><span class="sxs-lookup"><span data-stu-id="636c5-105">An example use of this component: to save space on a form, you can display a small icon on a button and use a ToolTip to explain the button's function.</span></span>  
  
## <a name="working-with-the-tooltip-component"></a><span data-ttu-id="636c5-106">使用 ToolTip 组件</span><span class="sxs-lookup"><span data-stu-id="636c5-106">Working with the ToolTip Component</span></span>  
 <span data-ttu-id="636c5-107"><xref:System.Windows.Forms.ToolTip>组件 `ToolTip` 为 Windows 窗体或其他容器上的多个控件提供了一个属性。</span><span class="sxs-lookup"><span data-stu-id="636c5-107">A <xref:System.Windows.Forms.ToolTip> component provides a `ToolTip` property to multiple controls on a Windows Form or other container.</span></span> <span data-ttu-id="636c5-108">例如，如果将一个组件放 <xref:System.Windows.Forms.ToolTip> 在窗体上，则可以在控件上显示 "在此处键入你的名称" <xref:System.Windows.Forms.TextBox> 和 "单击此处保存更改" <xref:System.Windows.Forms.Button> 。</span><span class="sxs-lookup"><span data-stu-id="636c5-108">For example, if you place one <xref:System.Windows.Forms.ToolTip> component on a form, you can display "Type your name here" for a <xref:System.Windows.Forms.TextBox> control and "Click here to save changes" for a <xref:System.Windows.Forms.Button> control.</span></span>  
  
 <span data-ttu-id="636c5-109">组件的关键方法 <xref:System.Windows.Forms.ToolTip> 是 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 和 <xref:System.Windows.Forms.ToolTip.GetToolTip%2A> 。</span><span class="sxs-lookup"><span data-stu-id="636c5-109">The key methods of the <xref:System.Windows.Forms.ToolTip> component are <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> and <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>.</span></span> <span data-ttu-id="636c5-110">您可以使用 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 方法来设置为控件显示的工具提示。</span><span class="sxs-lookup"><span data-stu-id="636c5-110">You can use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method to set the ToolTips displayed for controls.</span></span> <span data-ttu-id="636c5-111">有关详细信息，请参阅 [如何：在设计时在 Windows 窗体上设置控件的工具提示](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="636c5-111">For more information, see [How to: Set ToolTips for Controls on a Windows Form at Design Time](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md).</span></span> <span data-ttu-id="636c5-112">键属性为 <xref:System.Windows.Forms.ToolTip.Active%2A> ，它必须设置为以 `true` 显示工具提示，并 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 设置显示工具提示字符串的时间长度、用户必须指向控件以显示工具提示的时间，以及显示后续工具提示窗口所需的时间。</span><span class="sxs-lookup"><span data-stu-id="636c5-112">The key properties are <xref:System.Windows.Forms.ToolTip.Active%2A>, which must be set to `true` for the ToolTip to appear, and <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, which sets the length of time that the ToolTip string is shown, how long the user must point at the control for the ToolTip to appear, and how long it takes for subsequent ToolTip windows to appear.</span></span> <span data-ttu-id="636c5-113">有关详细信息，请参阅 [如何：更改 Windows 窗体 ToolTip 组件的延迟](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)。</span><span class="sxs-lookup"><span data-stu-id="636c5-113">For more information, see [How to: Change the Delay of the Windows Forms ToolTip Component](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="636c5-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="636c5-114">See also</span></span>

- <xref:System.Windows.Forms.ToolTip>
- [<span data-ttu-id="636c5-115">如何：在设计时为 Windows 窗体上的控件设置 ToolTip</span><span class="sxs-lookup"><span data-stu-id="636c5-115">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [<span data-ttu-id="636c5-116">如何：更改 Windows 窗体 ToolTip 组件的延迟</span><span class="sxs-lookup"><span data-stu-id="636c5-116">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
