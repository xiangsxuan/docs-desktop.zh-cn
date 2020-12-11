---
title: DomainUpDown 控件概述
ms.date: 03/30/2017
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
ms.openlocfilehash: 86703a96d4845414d043161e0efa67bfde9278db
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971542"
---
# <a name="domainupdown-control-overview-windows-forms"></a><span data-ttu-id="c51ca-102">DomainUpDown 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="c51ca-102">DomainUpDown Control Overview (Windows Forms)</span></span>
<span data-ttu-id="c51ca-103">Windows 窗体 <xref:System.Windows.Forms.DomainUpDown> 控件本质上是一个文本框和一对按钮的组合，用于在列表中上下移动。</span><span class="sxs-lookup"><span data-stu-id="c51ca-103">The Windows Forms <xref:System.Windows.Forms.DomainUpDown> control is essentially a combination of a text box and a pair of buttons for moving up or down through a list.</span></span> <span data-ttu-id="c51ca-104">控件显示并设置选项列表中的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="c51ca-104">The control displays and sets a text string from a list of choices.</span></span> <span data-ttu-id="c51ca-105">用户可以通过单击 "上移" 和 "下移" 按钮在列表中移动、按向上键和向下键或键入与列表中的项匹配的字符串，来选择字符串。</span><span class="sxs-lookup"><span data-stu-id="c51ca-105">The user can select the string by clicking up and down buttons to move through a list, by pressing the UP and DOWN ARROW keys, or by typing a string that matches an item in the list.</span></span> <span data-ttu-id="c51ca-106">此控件的一种可能用途是从按字母顺序排序的名称列表中选择项。</span><span class="sxs-lookup"><span data-stu-id="c51ca-106">One possible use for this control is for selecting items from an alphabetically sorted list of names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c51ca-107">若要对列表进行排序，请将 <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> 属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="c51ca-107">To sort the list, set the <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="c51ca-108">此控件的功能非常类似于列表框或组合框，但占用的空间非常少。</span><span class="sxs-lookup"><span data-stu-id="c51ca-108">The function of this control is very similar to the list box or combo box, but it takes up very little space.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="c51ca-109">键属性</span><span class="sxs-lookup"><span data-stu-id="c51ca-109">Key Properties</span></span>  
 <span data-ttu-id="c51ca-110">控件的键属性为 <xref:System.Windows.Forms.DomainUpDown.Items%2A> 、 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> 和 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> 。</span><span class="sxs-lookup"><span data-stu-id="c51ca-110">The key properties of the control are <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, and <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span></span> <span data-ttu-id="c51ca-111"><xref:System.Windows.Forms.DomainUpDown.Items%2A>属性包含其文本值显示在控件中的对象的列表。</span><span class="sxs-lookup"><span data-stu-id="c51ca-111">The <xref:System.Windows.Forms.DomainUpDown.Items%2A> property contains the list of objects whose text values are displayed in the control.</span></span> <span data-ttu-id="c51ca-112">如果 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> 设置为 `false` ，则控件会自动完成用户键入的文本，并将其与列表中的值匹配。</span><span class="sxs-lookup"><span data-stu-id="c51ca-112">If <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> is set to `false`, the control automatically completes text that the user types and matches it to a value in the list.</span></span> <span data-ttu-id="c51ca-113">如果 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> 设置为，则在 `true` 最后一项之后滚动将转到列表中的第一项，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="c51ca-113">If <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> is set to `true`, scrolling past the last item will take you to the first item in the list and vice versa.</span></span> <span data-ttu-id="c51ca-114">控件的主要方法是 <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> 和 <xref:System.Windows.Forms.DomainUpDown.DownButton%2A> 。</span><span class="sxs-lookup"><span data-stu-id="c51ca-114">The key methods of the control are <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> and <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span></span>  
  
 <span data-ttu-id="c51ca-115">此控件只显示文本字符串。</span><span class="sxs-lookup"><span data-stu-id="c51ca-115">This control displays only text strings.</span></span> <span data-ttu-id="c51ca-116">如果需要显示数值的控件，请使用 <xref:System.Windows.Forms.NumericUpDown> 控件。</span><span class="sxs-lookup"><span data-stu-id="c51ca-116">If you want a control that displays numeric values, use the <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="c51ca-117">有关详细信息，请参阅 [NumericUpDown 控件概述](numericupdown-control-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="c51ca-117">For more information, see [NumericUpDown Control Overview](numericupdown-control-overview-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c51ca-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c51ca-118">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- [<span data-ttu-id="c51ca-119">DomainUpDown 控件</span><span class="sxs-lookup"><span data-stu-id="c51ca-119">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
