---
title: 如何：在 TableLayoutPanel 控件中跨行和跨列
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: a215b2b4e05bab5c81d2779d4b67d5b9d57b6ba5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972649"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a><span data-ttu-id="7d403-102">如何：在 TableLayoutPanel 控件中跨行和跨列</span><span class="sxs-lookup"><span data-stu-id="7d403-102">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>
<span data-ttu-id="7d403-103">控件中的控件 <xref:System.Windows.Forms.TableLayoutPanel> 可以跨越相邻的行和列。</span><span class="sxs-lookup"><span data-stu-id="7d403-103">Controls in a <xref:System.Windows.Forms.TableLayoutPanel> control can span adjacent rows and columns.</span></span>

## <a name="to-span-columns-and-rows"></a><span data-ttu-id="7d403-104">跨列和行</span><span class="sxs-lookup"><span data-stu-id="7d403-104">To span columns and rows</span></span>

1. <span data-ttu-id="7d403-105">从 <xref:System.Windows.Forms.TableLayoutPanel> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="7d403-105">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="7d403-106">将 <xref:System.Windows.Forms.Button> 控件从 " **工具箱** " 拖放到控件的左上角单元格中 <xref:System.Windows.Forms.TableLayoutPanel> 。</span><span class="sxs-lookup"><span data-stu-id="7d403-106">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="7d403-107">将 <xref:System.Windows.Forms.Button> 控件的 **ColumnSpan** 属性设置为 **2**。</span><span class="sxs-lookup"><span data-stu-id="7d403-107">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **2**.</span></span> <span data-ttu-id="7d403-108">请注意，该 <xref:System.Windows.Forms.Button> 控件跨越第一列和第二列。</span><span class="sxs-lookup"><span data-stu-id="7d403-108">Note that the <xref:System.Windows.Forms.Button> control spans the first and second columns.</span></span>

4. <span data-ttu-id="7d403-109">将 <xref:System.Windows.Forms.Button> 控件的 **RowSpan** 属性设置为 **2**。</span><span class="sxs-lookup"><span data-stu-id="7d403-109">Set the <xref:System.Windows.Forms.Button> control's **RowSpan** property to **2**.</span></span> <span data-ttu-id="7d403-110">请注意，该 <xref:System.Windows.Forms.Button> 控件跨越第一行和第二行。</span><span class="sxs-lookup"><span data-stu-id="7d403-110">Note that the <xref:System.Windows.Forms.Button> control spans the first and second rows.</span></span>

5. <span data-ttu-id="7d403-111">将 <xref:System.Windows.Forms.Button> 控件的 **ColumnSpan** 属性设置为 **1**。</span><span class="sxs-lookup"><span data-stu-id="7d403-111">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **1**.</span></span> <span data-ttu-id="7d403-112">请注意， <xref:System.Windows.Forms.Button> 控件将移到第一列中，并跨越第一行和第二行。</span><span class="sxs-lookup"><span data-stu-id="7d403-112">Note that the <xref:System.Windows.Forms.Button> control moves into the first column and spans the first and second rows.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d403-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d403-113">See also</span></span>

- [<span data-ttu-id="7d403-114">TableLayoutPanel 控件</span><span class="sxs-lookup"><span data-stu-id="7d403-114">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
