---
title: 如何：更改 ToolStrip 项的间距和对齐方式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 550ac1660a077e8d766a01bfa8d102c07f0fbfeb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971884"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="9a4aa-102">如何：在 Windows 窗体中更改 ToolStrip 项的间距和对齐方式</span><span class="sxs-lookup"><span data-stu-id="9a4aa-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="9a4aa-103"><xref:System.Windows.Forms.ToolStrip>控件完全支持布局功能，如调整大小、控件的间距（ <xref:System.Windows.Forms.ToolStripItem> 相对于控件）、上控件的排列方式 <xref:System.Windows.Forms.ToolStrip> 和相对于控件的间距 <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="9a4aa-104">由于属性的默认值 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 为，因此 `true` 控件将自动调整大小，除非将 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 属性设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="9a4aa-105">手动调整 ToolStripItem 的大小</span><span class="sxs-lookup"><span data-stu-id="9a4aa-105">To manually size a ToolStripItem</span></span>  
  
1. <span data-ttu-id="9a4aa-106"><xref:System.Windows.Forms.ToolStripItem.AutoSize%2A>对于关联的控件，将属性设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. <span data-ttu-id="9a4aa-107">按所 <xref:System.Windows.Forms.ToolStripItem.Size%2A> 需方式为关联的设置属性 <xref:System.Windows.Forms.ToolStripItem> 。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="9a4aa-108">设置 ToolStripItem 的间距</span><span class="sxs-lookup"><span data-stu-id="9a4aa-108">To set the spacing of a ToolStripItem</span></span>  
  
1. <span data-ttu-id="9a4aa-109">在关联控件的属性中插入所需的值（以像素为单位） <xref:System.Windows.Forms.ToolStripItem.Margin%2A> 。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="9a4aa-110">此属性的值 <xref:System.Windows.Forms.ToolStripItem.Margin%2A> 按如下顺序指定项与相邻项之间的间距： Left、Top、Right 和底端。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="9a4aa-111">将 ToolStripItem 与 ToolStrip 右端对齐</span><span class="sxs-lookup"><span data-stu-id="9a4aa-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1. <span data-ttu-id="9a4aa-112"><xref:System.Windows.Forms.ToolStripItem.Alignment%2A>对于关联的控件，将属性设置为 <xref:System.Windows.Forms.ToolStripItemAlignment.Right> 。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="9a4aa-113">默认情况下， <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 设置为 <xref:System.Windows.Forms.ToolStripItemAlignment.Left> ，它将控件与的左侧对齐 <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="9a4aa-114">在 ToolStrip 上排列 ToolStrip 项</span><span class="sxs-lookup"><span data-stu-id="9a4aa-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
- <span data-ttu-id="9a4aa-115">将 <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> 属性设置为所需的值 <xref:System.Windows.Forms.ToolStripLayoutStyle> 。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9a4aa-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a4aa-116">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="9a4aa-117">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="9a4aa-117">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="9a4aa-118">ToolStrip 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="9a4aa-118">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="9a4aa-119">ToolStrip 技术摘要</span><span class="sxs-lookup"><span data-stu-id="9a4aa-119">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
