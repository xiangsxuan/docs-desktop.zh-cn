---
title: 带有分组框控件的组控件
description: 了解如何使用 Windows 窗体分组框控件对控件进行分组，以便可以创建相关元素的可视分组。
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: f84c495a18f4ae5e04367f024a1e2849f1ed59f9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971842"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="e8778-103">如何：使用 Windows 窗体 GroupBox 控件对控件分组</span><span class="sxs-lookup"><span data-stu-id="e8778-103">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="e8778-104">Windows 窗体 <xref:System.Windows.Forms.GroupBox> 控件用于对其他控件进行分组。</span><span class="sxs-lookup"><span data-stu-id="e8778-104">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="e8778-105">分组控件有三个原因：</span><span class="sxs-lookup"><span data-stu-id="e8778-105">There are three reasons to group controls:</span></span>  
  
- <span data-ttu-id="e8778-106">为清晰的用户界面创建相关窗体元素的可视分组。</span><span class="sxs-lookup"><span data-stu-id="e8778-106">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
- <span data-ttu-id="e8778-107">若要创建按编程分组 (单选按钮，例如) 。</span><span class="sxs-lookup"><span data-stu-id="e8778-107">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
- <span data-ttu-id="e8778-108">用于在设计时将控件作为一个单元移动。</span><span class="sxs-lookup"><span data-stu-id="e8778-108">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="e8778-109">创建一组控件</span><span class="sxs-lookup"><span data-stu-id="e8778-109">To create a group of controls</span></span>  
  
1. <span data-ttu-id="e8778-110"><xref:System.Windows.Forms.GroupBox>在窗体上绘制控件。</span><span class="sxs-lookup"><span data-stu-id="e8778-110">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2. <span data-ttu-id="e8778-111">将其他控件添加到分组框，并在组框中绘制每个控件。</span><span class="sxs-lookup"><span data-stu-id="e8778-111">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="e8778-112">如果要将现有控件置于分组框中，则可以选择所有控件，将它们剪切到剪贴板，选择 <xref:System.Windows.Forms.GroupBox> 控件，然后将其粘贴到分组框中。</span><span class="sxs-lookup"><span data-stu-id="e8778-112">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="e8778-113">您还可以将其拖动到分组框中。</span><span class="sxs-lookup"><span data-stu-id="e8778-113">You can also drag them into the group box.</span></span>  
  
3. <span data-ttu-id="e8778-114">将 <xref:System.Windows.Forms.GroupBox.Text%2A> "分组框" 的属性设置为相应的标题。</span><span class="sxs-lookup"><span data-stu-id="e8778-114">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8778-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8778-115">See also</span></span>

- <xref:System.Windows.Forms.GroupBox>
- [<span data-ttu-id="e8778-116">GroupBox 控件</span><span class="sxs-lookup"><span data-stu-id="e8778-116">GroupBox Control</span></span>](groupbox-control-windows-forms.md)
