---
title: CheckBox 控件概述
ms.date: 03/30/2017
f1_keywords:
- CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
ms.openlocfilehash: b42816cf1bc0ce1ab6db0a2a436b17b0d4370d59
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970711"
---
# <a name="checkbox-control-overview-windows-forms"></a><span data-ttu-id="93067-102">CheckBox 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="93067-102">CheckBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="93067-103">Windows 窗体 <xref:System.Windows.Forms.CheckBox> 控件指示特定条件处于打开开始关闭状态。</span><span class="sxs-lookup"><span data-stu-id="93067-103">The Windows Forms <xref:System.Windows.Forms.CheckBox> control indicates whether a particular condition is on or off.</span></span> <span data-ttu-id="93067-104">通常用于向用户显示 Yes/No 或 True/False 选项。</span><span class="sxs-lookup"><span data-stu-id="93067-104">It is commonly used to present a Yes/No or True/False selection to the user.</span></span> <span data-ttu-id="93067-105">可以使用组中的复选框控件来显示用户可从中选择一个或多选的多个选项。</span><span class="sxs-lookup"><span data-stu-id="93067-105">You can use check box controls in groups to display multiple choices from which the user can select one or more.</span></span>  
  
 <span data-ttu-id="93067-106">复选框控件类似于单选按钮控件，其中每个控件用于指示用户所做的选择。</span><span class="sxs-lookup"><span data-stu-id="93067-106">The check box control is similar to the radio button control in that each is used to indicate a selection that is made by the user.</span></span> <span data-ttu-id="93067-107">它们的区别在于，一次只能选择一个组中的一个单选按钮。</span><span class="sxs-lookup"><span data-stu-id="93067-107">They differ in that only one radio button in a group can be selected at a time.</span></span> <span data-ttu-id="93067-108">但对于复选框控件，可能会选择任意数量的复选框。</span><span class="sxs-lookup"><span data-stu-id="93067-108">With the check box control, however, any number of check boxes may be selected.</span></span>  
  
 <span data-ttu-id="93067-109">可以使用简单的数据绑定将复选框连接到数据库中的元素。</span><span class="sxs-lookup"><span data-stu-id="93067-109">A check box may be connected to elements in a database using simple data binding.</span></span> <span data-ttu-id="93067-110">可以使用控件对多个复选框进行分组 <xref:System.Windows.Forms.GroupBox> 。</span><span class="sxs-lookup"><span data-stu-id="93067-110">Multiple check boxes may be grouped using the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="93067-111">这对于视觉外观和用户界面设计都很有用，因为可以在窗体设计器上一起移动分组控件。</span><span class="sxs-lookup"><span data-stu-id="93067-111">This is useful for visual appearance and also for user interface design, since grouped controls can be moved around together on the form designer.</span></span> <span data-ttu-id="93067-112">有关详细信息，请参阅 [Windows 窗体数据绑定](../windows-forms-data-binding.md) 和 [分组框控件](groupbox-control-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="93067-112">For more information, see [Windows Forms Data Binding](../windows-forms-data-binding.md) and [GroupBox Control](groupbox-control-windows-forms.md).</span></span>  
  
 <span data-ttu-id="93067-113"><xref:System.Windows.Forms.CheckBox>控件具有两个重要的属性： <xref:System.Windows.Forms.CheckBox.Checked%2A> 和 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 。</span><span class="sxs-lookup"><span data-stu-id="93067-113">The <xref:System.Windows.Forms.CheckBox> control has two important properties, <xref:System.Windows.Forms.CheckBox.Checked%2A> and <xref:System.Windows.Forms.CheckBox.CheckState%2A>.</span></span> <span data-ttu-id="93067-114"><xref:System.Windows.Forms.CheckBox.Checked%2A>属性返回 `true` 或 `false` 。</span><span class="sxs-lookup"><span data-stu-id="93067-114">The <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns either `true` or `false`.</span></span> <span data-ttu-id="93067-115"><xref:System.Windows.Forms.CheckBox.CheckState%2A>属性返回 <xref:System.Windows.Forms.CheckState.Checked> 或 <xref:System.Windows.Forms.CheckState.Unchecked> ; 或者，如果 <xref:System.Windows.Forms.CheckBox.ThreeState%2A> 属性设置为 `true` ，则 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 还可能返回 <xref:System.Windows.Forms.CheckState.Indeterminate> 。</span><span class="sxs-lookup"><span data-stu-id="93067-115">The <xref:System.Windows.Forms.CheckBox.CheckState%2A> property returns either <xref:System.Windows.Forms.CheckState.Checked> or <xref:System.Windows.Forms.CheckState.Unchecked>; or, if the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> may also return <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span> <span data-ttu-id="93067-116">处于不确定状态时，将显示带有一个灰显外观的框，指示该选项不可用。</span><span class="sxs-lookup"><span data-stu-id="93067-116">In the indeterminate state, the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93067-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93067-117">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="93067-118">如何：使用 Windows 窗体 CheckBox 控件设置选项</span><span class="sxs-lookup"><span data-stu-id="93067-118">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="93067-119">如何：响应 Windows 窗体 CheckBox 的单击</span><span class="sxs-lookup"><span data-stu-id="93067-119">How to: Respond to Windows Forms CheckBox Clicks</span></span>](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [<span data-ttu-id="93067-120">CheckBox 控件</span><span class="sxs-lookup"><span data-stu-id="93067-120">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
