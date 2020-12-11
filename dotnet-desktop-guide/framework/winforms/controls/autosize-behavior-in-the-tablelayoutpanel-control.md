---
title: TableLayoutPanel 控件中的自动调整大小行为
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- localizing forms
- layout [Windows Forms], AutoSize
- sizing [Windows Forms], automatic
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- automatic sizing
- AutoSizeMode property
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
ms.openlocfilehash: daeca48c4fcfaf83d6506ba07d60ec2dcfdcace7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971324"
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a><span data-ttu-id="d8303-102">TableLayoutPanel 控件中的自动调整大小行为</span><span class="sxs-lookup"><span data-stu-id="d8303-102">AutoSize Behavior in the TableLayoutPanel Control</span></span>
## <a name="distinct-autosize-behaviors"></a><span data-ttu-id="d8303-103">不同的 AutoSize 行为</span><span class="sxs-lookup"><span data-stu-id="d8303-103">Distinct AutoSize Behaviors</span></span>  
 <span data-ttu-id="d8303-104"><xref:System.Windows.Forms.TableLayoutPanel>控件支持通过以下方式自动调整大小行为：</span><span class="sxs-lookup"><span data-stu-id="d8303-104">The <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior in the following ways:</span></span>  
  
- <span data-ttu-id="d8303-105">通过 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性;</span><span class="sxs-lookup"><span data-stu-id="d8303-105">Through the <xref:System.Windows.Forms.Control.AutoSize%2A> property;</span></span>  
  
- <span data-ttu-id="d8303-106">通过 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> <xref:System.Windows.Forms.TableLayoutPanel> 控件的列和行样式的属性。</span><span class="sxs-lookup"><span data-stu-id="d8303-106">Through the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property on the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a><span data-ttu-id="d8303-107">具有行和列样式的 AutoSize 属性</span><span class="sxs-lookup"><span data-stu-id="d8303-107">The AutoSize Property with Row and Column Styles</span></span>  
 <span data-ttu-id="d8303-108">下表描述了 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性和 <xref:System.Windows.Forms.TableLayoutPanel> 控件的列和行样式之间的交互。</span><span class="sxs-lookup"><span data-stu-id="d8303-108">The following table describes the interaction between the <xref:System.Windows.Forms.Control.AutoSize%2A> property and the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
|<span data-ttu-id="d8303-109">自动调整大小</span><span class="sxs-lookup"><span data-stu-id="d8303-109">AutoSize setting</span></span>|<span data-ttu-id="d8303-110">样式交互</span><span class="sxs-lookup"><span data-stu-id="d8303-110">Style interaction</span></span>|  
|----------------------|-----------------------|  
|`false`|<span data-ttu-id="d8303-111"><xref:System.Windows.Forms.TableLayoutPanel>控件从左到右前进，并按以下顺序为列或行分配空间。</span><span class="sxs-lookup"><span data-stu-id="d8303-111">The <xref:System.Windows.Forms.TableLayoutPanel> control proceeds from left to right, and allocates space for the column or row or in the following order.</span></span><br /><br /> <span data-ttu-id="d8303-112">1. 如果 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 属性设置为，则 <xref:System.Windows.Forms.SizeType.Absolute> 分配或指定的像素数 <xref:System.Windows.Forms.ColumnStyle.Width%2A> <xref:System.Windows.Forms.RowStyle.Height%2A> 。</span><span class="sxs-lookup"><span data-stu-id="d8303-112">1.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.Absolute>, the number of pixels specified by <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> is allocated.</span></span><br /><span data-ttu-id="d8303-113">2. 如果将 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 属性设置为 <xref:System.Windows.Forms.SizeType.AutoSize> ，则会分配子控件的方法返回的像素数 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> 。</span><span class="sxs-lookup"><span data-stu-id="d8303-113">2.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.AutoSize>, the number of pixels returned by the child control’s <xref:System.Windows.Forms.Control.GetPreferredSize%2A> method is allocated.</span></span><br /><span data-ttu-id="d8303-114">3. 在 <xref:System.Windows.Forms.SizeType.Absolute> 分配所有和 <xref:System.Windows.Forms.SizeType.AutoSize> 列或行的空间后，任何设置为的列或行 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> <xref:System.Windows.Forms.SizeType.Percent> 均用于按比例分配剩余可用空间</span><span class="sxs-lookup"><span data-stu-id="d8303-114">3.  After space for all <xref:System.Windows.Forms.SizeType.Absolute> and <xref:System.Windows.Forms.SizeType.AutoSize> columns or rows is allocated, any columns or rows with <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> set to <xref:System.Windows.Forms.SizeType.Percent> are used to proportionally allocate the remaining free space</span></span>|  
|`true`|<span data-ttu-id="d8303-115">与以前的交互类似，但 <xref:System.Windows.Forms.SizeType.Percent> 列或行的自动调整大小方面除外。</span><span class="sxs-lookup"><span data-stu-id="d8303-115">Similar to the previous interaction, with the exception that <xref:System.Windows.Forms.SizeType.Percent> columns or rows acquire an automatic sizing aspect.</span></span><br /><br /> <span data-ttu-id="d8303-116"><xref:System.Windows.Forms.TableLayoutPanel>控件扩展列或行以创建足够的可用空间，因此没有样式的列或行可 <xref:System.Windows.Forms.SizeType.Percent> 剪辑其内容。</span><span class="sxs-lookup"><span data-stu-id="d8303-116">The <xref:System.Windows.Forms.TableLayoutPanel> control expands the column or row to create adequate free space, so that no column or row with <xref:System.Windows.Forms.SizeType.Percent> styling clips its contents.</span></span> <span data-ttu-id="d8303-117"><xref:System.Windows.Forms.TableLayoutPanel>控件根据或属性，按比例分配新的 <xref:System.Windows.Forms.ColumnStyle.Width%2A> 空间 <xref:System.Windows.Forms.RowStyle.Height%2A> 。</span><span class="sxs-lookup"><span data-stu-id="d8303-117">The <xref:System.Windows.Forms.TableLayoutPanel> control allocates the new space proportionally according to the <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8303-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8303-118">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="d8303-119">TableLayoutPanel 控件概述</span><span class="sxs-lookup"><span data-stu-id="d8303-119">TableLayoutPanel Control Overview</span></span>](tablelayoutpanel-control-overview.md)
