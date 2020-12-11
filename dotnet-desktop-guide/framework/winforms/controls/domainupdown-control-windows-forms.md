---
title: DomainUpDown 控件
ms.date: 03/30/2017
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
ms.openlocfilehash: b538350a84e341d6b2759a7db28f8799f3777a86
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971539"
---
# <a name="domainupdown-control-windows-forms"></a><span data-ttu-id="ab69d-102">DomainUpDown 控件（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="ab69d-102">DomainUpDown Control (Windows Forms)</span></span>
<span data-ttu-id="ab69d-103">Windows 窗体 <xref:System.Windows.Forms.DomainUpDown> 控件看起来像是一个文本框和一对按钮的组合，用于在列表中向上或向下移动。</span><span class="sxs-lookup"><span data-stu-id="ab69d-103">The Windows Forms <xref:System.Windows.Forms.DomainUpDown> control looks like a combination of a text box and a pair of buttons for moving up or down through a list.</span></span> <span data-ttu-id="ab69d-104">控件显示并设置选项列表中的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="ab69d-104">The control displays and sets a text string from a list of choices.</span></span> <span data-ttu-id="ab69d-105">用户可以通过单击 "上移" 和 "下移" 按钮在列表中移动、按向上键和向下键或键入与列表中的项匹配的字符串，来选择字符串。</span><span class="sxs-lookup"><span data-stu-id="ab69d-105">The user can select the string by clicking up and down buttons to move through a list, by pressing the UP and DOWN ARROW keys, or by typing a string that matches an item in the list.</span></span> <span data-ttu-id="ab69d-106">此控件的一种可能用途是从按字母顺序排序的名称列表中选择项。</span><span class="sxs-lookup"><span data-stu-id="ab69d-106">One possible use for this control is for selecting items from an alphabetically sorted list of names.</span></span> <span data-ttu-id="ab69d-107"> (若要对列表进行排序，请将 <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> 属性设置为 `true` 。 ) 此控件的功能非常类似于列表框或组合框，但占用的空间非常少。</span><span class="sxs-lookup"><span data-stu-id="ab69d-107">(To sort the list, set the <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> property to `true`.) The function of this control is very similar to the list box or combo box, but it takes up very little space.</span></span>  
  
 <span data-ttu-id="ab69d-108">控件的键属性为 <xref:System.Windows.Forms.DomainUpDown.Items%2A> 、 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> 和 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> 。</span><span class="sxs-lookup"><span data-stu-id="ab69d-108">The key properties of the control are <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, and <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span></span> <span data-ttu-id="ab69d-109"><xref:System.Windows.Forms.DomainUpDown.Items%2A>属性包含其文本值显示在控件中的对象的列表。</span><span class="sxs-lookup"><span data-stu-id="ab69d-109">The <xref:System.Windows.Forms.DomainUpDown.Items%2A> property contains the list of objects whose text values are displayed in the control.</span></span> <span data-ttu-id="ab69d-110">如果 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> 设置为 `false` ，则控件会自动完成用户键入的文本，并将其与列表中的值匹配。</span><span class="sxs-lookup"><span data-stu-id="ab69d-110">If <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> is set to `false`, the control automatically completes text that the user types and matches it to a value in the list.</span></span> <span data-ttu-id="ab69d-111">如果 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> 设置为，则在 `true` 最后一项之后滚动将转到列表中的第一项，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="ab69d-111">If <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> is set to `true`, scrolling past the last item will take you to the first item in the list and vice versa.</span></span> <span data-ttu-id="ab69d-112">控件的主要方法是 <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> 和 <xref:System.Windows.Forms.DomainUpDown.DownButton%2A> 。</span><span class="sxs-lookup"><span data-stu-id="ab69d-112">The key methods of the control are <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> and <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span></span>  
  
 <span data-ttu-id="ab69d-113">此控件只显示文本字符串。</span><span class="sxs-lookup"><span data-stu-id="ab69d-113">This control displays only text strings.</span></span> <span data-ttu-id="ab69d-114">如果需要显示数值的控件，请使用 <xref:System.Windows.Forms.NumericUpDown> 控件。</span><span class="sxs-lookup"><span data-stu-id="ab69d-114">If you want a control that displays numeric values, use the <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="ab69d-115">有关详细信息，请参阅 [NumericUpDown 控件](numericupdown-control-windows-forms.md) 。</span><span class="sxs-lookup"><span data-stu-id="ab69d-115">For more information, see [NumericUpDown Control](numericupdown-control-windows-forms.md) .</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ab69d-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="ab69d-116">In This Section</span></span>  
 [<span data-ttu-id="ab69d-117">DomainUpDown 控件概述</span><span class="sxs-lookup"><span data-stu-id="ab69d-117">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)  
 <span data-ttu-id="ab69d-118">介绍控件的一般概念 <xref:System.Windows.Forms.DomainUpDown> ，该控件允许用户浏览文本字符串列表并从中进行选择。</span><span class="sxs-lookup"><span data-stu-id="ab69d-118">Introduces the general concepts of the <xref:System.Windows.Forms.DomainUpDown> control, which allows users to browse through and select from a list of text strings.</span></span>  
  
 [<span data-ttu-id="ab69d-119">如何：以编程方式向 Windows 窗体 DomainUpDown 控件添加项</span><span class="sxs-lookup"><span data-stu-id="ab69d-119">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>](how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 <span data-ttu-id="ab69d-120">描述如何指定 <xref:System.Windows.Forms.DomainUpDown> 控件应显示的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="ab69d-120">Describes how to specify the text strings the <xref:System.Windows.Forms.DomainUpDown> control should display.</span></span>  
  
 [<span data-ttu-id="ab69d-121">如何：从 Windows 窗体 DomainUpDown 控件移除项</span><span class="sxs-lookup"><span data-stu-id="ab69d-121">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>](how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 <span data-ttu-id="ab69d-122">介绍如何 <xref:System.Windows.Forms.DomainUpDown> 在代码中删除控件中的项。</span><span class="sxs-lookup"><span data-stu-id="ab69d-122">Describes how to delete items from the <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ab69d-123">参考</span><span class="sxs-lookup"><span data-stu-id="ab69d-123">Reference</span></span>  
 <xref:System.Windows.Forms.DomainUpDown>  
 <span data-ttu-id="ab69d-124">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="ab69d-124">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 <span data-ttu-id="ab69d-125">描述此类，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="ab69d-125">Describes this class and has links to all its members..</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ab69d-126">相关章节</span><span class="sxs-lookup"><span data-stu-id="ab69d-126">Related Sections</span></span>  
 [<span data-ttu-id="ab69d-127">可在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="ab69d-127">Controls You Can Use On Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="ab69d-128">提供 Windows 窗体控件的完整列表，附带其使用情况相关信息的链接。</span><span class="sxs-lookup"><span data-stu-id="ab69d-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
