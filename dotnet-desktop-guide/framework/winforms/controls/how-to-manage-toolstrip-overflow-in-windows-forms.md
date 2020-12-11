---
title: 如何：管理 ToolStrip 溢出
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
ms.openlocfilehash: 52cc02e626bee2d2457355028ecddc17e462d8fa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970560"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a><span data-ttu-id="91119-102">如何：在 Windows 窗体中管理 ToolStrip 溢出</span><span class="sxs-lookup"><span data-stu-id="91119-102">How to: Manage ToolStrip Overflow in Windows Forms</span></span>

<span data-ttu-id="91119-103">如果控件中的所有项都 <xref:System.Windows.Forms.ToolStrip> 不适合于分配的空间，则可以在上启用溢出功能， <xref:System.Windows.Forms.ToolStrip> 并确定特定的溢出行为 <xref:System.Windows.Forms.ToolStripItem> 。</span><span class="sxs-lookup"><span data-stu-id="91119-103">When all the items on a <xref:System.Windows.Forms.ToolStrip> control do not fit in the allotted space, you can enable overflow functionality on the <xref:System.Windows.Forms.ToolStrip> and determine the overflow behavior of specific <xref:System.Windows.Forms.ToolStripItem>s.</span></span>

<span data-ttu-id="91119-104">当你添加 <xref:System.Windows.Forms.ToolStripItem> 的需要的空间超过了给定窗体的当前大小所分配的空间时 <xref:System.Windows.Forms.ToolStrip> ，将 <xref:System.Windows.Forms.ToolStripOverflowButton> 自动在上显示 <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="91119-104">When you add <xref:System.Windows.Forms.ToolStripItem>s that require more space than is allotted to the <xref:System.Windows.Forms.ToolStrip> given the form's current size, a <xref:System.Windows.Forms.ToolStripOverflowButton> automatically appears on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="91119-105"><xref:System.Windows.Forms.ToolStripOverflowButton>随即出现，启用溢出的项将移至下拉溢出菜单中。</span><span class="sxs-lookup"><span data-stu-id="91119-105">The <xref:System.Windows.Forms.ToolStripOverflowButton> appears, and overflow-enabled items are moved into the drop-down overflow menu.</span></span> <span data-ttu-id="91119-106">这使您可以自定义项的正确调整，并为其设置优先级 <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="91119-106">This allows you to customize and prioritize how your <xref:System.Windows.Forms.ToolStrip> items properly adjust to different form sizes.</span></span> <span data-ttu-id="91119-107">还可以通过使用 <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 和 <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> 属性和事件更改项在溢出时的外观 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 。</span><span class="sxs-lookup"><span data-stu-id="91119-107">You can also change the appearance of your items when they fall into the overflow by using the <xref:System.Windows.Forms.ToolStripItem.Placement%2A> and <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> properties and the <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> event.</span></span> <span data-ttu-id="91119-108">如果您在设计时或运行时放大窗体，则在 <xref:System.Windows.Forms.ToolStripItem> 主窗体上可以显示更多的， <xref:System.Windows.Forms.ToolStrip> 在 <xref:System.Windows.Forms.ToolStripOverflowButton> 您减小窗体大小时，甚至可能会消失。</span><span class="sxs-lookup"><span data-stu-id="91119-108">If you enlarge the form at either design time or run time, more <xref:System.Windows.Forms.ToolStripItem>s can be displayed on the main <xref:System.Windows.Forms.ToolStrip> and the <xref:System.Windows.Forms.ToolStripOverflowButton> might even disappear until you decrease the size of the form.</span></span>

## <a name="to-enable-overflow-on-a-toolstrip-control"></a><span data-ttu-id="91119-109">对 ToolStrip 控件启用溢出</span><span class="sxs-lookup"><span data-stu-id="91119-109">To enable overflow on a ToolStrip control</span></span>

- <span data-ttu-id="91119-110">确保的 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> 属性未设置为 `false` <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="91119-110">Ensure that the <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> property is not set to `false` for the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="91119-111">默认值为 `True`。</span><span class="sxs-lookup"><span data-stu-id="91119-111">The default is `True`.</span></span>

     <span data-ttu-id="91119-112">当 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> `True` (默认的) 时， <xref:System.Windows.Forms.ToolStripItem> 当的内容 <xref:System.Windows.Forms.ToolStripItem> 超出水平的宽度或高度时，将发送到下拉溢出菜单 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="91119-112">When <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> is `True` (the default), a <xref:System.Windows.Forms.ToolStripItem> is sent to the drop-down overflow menu when the content of the <xref:System.Windows.Forms.ToolStripItem> exceeds the width of a horizontal <xref:System.Windows.Forms.ToolStrip> or the height of a vertical <xref:System.Windows.Forms.ToolStrip>.</span></span>

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a><span data-ttu-id="91119-113">指定特定 ToolStripItem 的溢出行为</span><span class="sxs-lookup"><span data-stu-id="91119-113">To specify overflow behavior of a specific ToolStripItem</span></span>

- <span data-ttu-id="91119-114">将 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 的属性设置 <xref:System.Windows.Forms.ToolStripItem> 为所需的值。</span><span class="sxs-lookup"><span data-stu-id="91119-114">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the <xref:System.Windows.Forms.ToolStripItem> to the desired value.</span></span> <span data-ttu-id="91119-115">可能的为 `Always` 、 `Never` 和 `AsNeeded` 。</span><span class="sxs-lookup"><span data-stu-id="91119-115">The possibilities are `Always`, `Never`, and `AsNeeded`.</span></span> <span data-ttu-id="91119-116">默认值为 `AsNeeded`。</span><span class="sxs-lookup"><span data-stu-id="91119-116">The default is `AsNeeded`.</span></span>

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a><span data-ttu-id="91119-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91119-117">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="91119-118">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="91119-118">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="91119-119">ToolStrip 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="91119-119">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="91119-120">ToolStrip 技术摘要</span><span class="sxs-lookup"><span data-stu-id="91119-120">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
